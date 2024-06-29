# Setup Merlinn

This guide walks you through on how to setup Merlinn on your machien.

## Prerequisites 📜

Ensure you have the following installed:

- **Docker & Docker Compose** - The app works with Docker containers. To run it, you need to have [Docker Desktop](https://docs.docker.com/desktop/), which comes with Docker CLI, Docker Engine and Docker Compose.
<!-- - **Ngrok** - Ngrok allows you to open HTTPS tunnel to your local machine. This is needed in order to get events from PagerDuty/Opsgenie. Install ngrok cli and create an account (see [here](https://ngrok.com/)). -->

## Setup 🏎️

You can find the installation video [here](https://www.loom.com/share/1f562cb067364517b1c1e7bf7f789db7?sid=8ea35183-893e-4e74-b450-c3e2e1cc1f11).

1. Clone the repository:

   ```bash
   git clone git@github.com:merlinn-co/merlinn.git && cd merlinn
   ```

2. Copy the .env.example file:

   ```bash
   cp .env.example .env
   ```

3. Launch vault and obtain vault tokens:

   We use Hashicorp Vault to manage secrets such as API tokens, OAuth credentials, etc.

   1. Launch the vault instance:

      ```bash
      docker compose up vault -d
      ```

   2. Go to Vault UI: http://localhost:8202
   3. Insert 1 in "Key shares" and "Key threshold" and click "Initialize".
   4. Click "Download keys".
   5. In the JSON file you've downloaded, copy the first value in "keys_base64" and the "root_token" value. These values are going to be used in the next step as `HASHICORP_VAULT_UNSEAL_TOKEN` and `HASHICORP_VAULT_ROOT_TOKEN` respectively.

4. Configure LiteLLM Proxy Server:

   We use [LiteLLM Proxy Server](https://docs.litellm.ai/docs/simple_proxy) to interact with 100+ of models in a unified interface (OpenAI interface).

   1. Copy the example files:

      ```bash
      cp config/litellm/.env.example config/litellm/.env
      cp config/litellm/config.example.yaml config/litellm/config.yaml
      ```

   2. Define your OpenAI key and place it inside `config/litellm/.env` as `OPENAI_API_KEY`. You can get your API key [here](https://platform.openai.com/api-keys). Rest assured, you won't be charged unless you use the API. For more details on pricing, check [here](https://openai.com/pricing).

   3. **(Optional)** Define custom endpoints. If you want to use other vendors (AWS Bedrock, Azure OpenAI, Anthropic, Hugging Face models, etc), checkout LiteLLM Proxy documentation. You simply need to change `config/litellm/.env` & `config/litellm/config.yaml`. Checkout the comments there & LiteLLM's documentation. **Note** You have to use a vendor that supports function calling.

5. Open `.env` in your favorite editor (vim, vscode, emacs, etc):

   ```bash
   vim .env # or emacs or vscode or nano
   ```

6. Update these variables:

   - `SLACK_BOT_TOKEN`, `SLACK_APP_TOKEN` and `SLACK_SIGNING_SECRET` - These variables are needed in order to talk to Merlinn on Slack. Please follow [this guide](https://github.com/merlinn-co/merlinn/tree/main/config/slack/README.md) to create a new Slack app in your organization.

   - `HASHICORP_VAULT_ROOT_TOKEN` and `HASHICORP_VAULT_UNSEAL_TOKEN` - These variables are used to manage your secrets. You should obtain them from the JSON you've downloaded at step 3. `root_token`=`HASHICORP_VAULT_ROOT_TOKEN`, `keys_base64`=`HASHICORP_VAULT_UNSEAL_TOKEN`

   - (Optional) `SMTP_CONNECTION_URL` - This variable is needed in order to invite new members to your Merlinn organization via email and allow them to use the bot. It's not mandatory if you just want to test Merlinn and play with it. If you do want to send invites to your team members, you can use a service like SendGrid/Mailgun. Should follow this pattern: `smtp://username:password@domain:port`.

7. Launch the project:
   ```bash
   docker compose up -d
   ```

That's it. You should be able to visit Merlinn's dashboard in http://localhost:5173.
Simply create a user **(with the same e-mail as the one in your Slack user)** and start to configure your organization.

The next steps are to configure your organization a bit more (connect incident management tools, build a knowledge base, etc). Head over to the [Configure & connect](../02-Getting%20started/02-Configure%20&%20connect.md) section.

### Updating Merlinn 🧙‍♂️

1. Pull the latest changes:

   ```bash
   git pull
   ```

2. Rebuild images:

   ```bash
   docker-compose up --build -d
   ```

### Visualize Knowledge Base 🗺️

We use ChromaDB as our vector DB. Moreover, we use [vector admin](https://vectoradmin.com/) in order to see the ingested documents. To use vector admin, simply run this command:

```bash
docker compose up vector-admin -d
```

This command starts vector-admin at port 3001. Head over to http://localhost:3001 and configure your local ChromaDB. **Note:** Since vector-admin runs inside a docker container, in the "host" field make sure to insert `http://host.docker.internal:8000` instead of `http://localhost:8000`. This is because "localhost" doesn't refer to the host inside the container itself.

Moreover, in the "API Header & Key", you'd need to put "X-Chroma-Token" as the header and the value you have inside .env `CHROMA_SERVER_AUTHN_CREDENTIALS` as the value.

To learn how to use VectorAdmin, visit the [docs](https://github.com/Mintplex-Labs/vector-admin).

## Next steps

Now that you have a working environment, go ahead and configure your organization a bit more (connect incident management tools, build a knowledge base, etc). Head over to the [Configure & connect](./02-Configure%20&%20connect.md) section.
