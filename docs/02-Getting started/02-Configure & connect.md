# Configure & connect

Learn how to configure Merlinn and connect it to your organization's tools.

At the end, you should be able to interact with Merlinn on Slack about your production issues and in general ask it for advice about technical issues.

## Prerequisites

Make sure you have a working environment. If you don't have one yet, go to the [setup](01-Setup%20Merlinn.md) section.

## Configure

Once you have a working environment, follow these sections.

### Create an organization

Merlinn works in the context of an organization. To get started, you need to create an organization:

1. Go to the dashboard and click "Organization" in the side drawer.
2. Click "Create a new organization".
3. Insert a meaningful name for your organization.
4. Click "Create".

Once created, you should see the organization overview screen:
<img src="../img/doc-imgs/organization-overview.png" />
:::tip
To allow other team members to interact with Merlinn, you need to invite them to your organization. For this, you need to configure an `SMTP_CONNECTION_URL` in your environment variables. Use a service like [SendGrid](https://sendgrid.com/) or [Mailgun](https://www.mailgun.com/).

After you have a working SMTP server, go to "Members" and click "Invite members".
:::

### Connect integrations

Merlinn supports several integrations that allows it to fetch data during incidents & follow-up questions. To connect integrations, go to your "Integrations" page.

:::info
To learn which integrations are available, check the [Integrations](../03-Integrations/01-Slack.md) section.
:::

### Configure webhooks

Merlinn listens to production incidents and starts investigating them automatically. We currently support **PagerDuty**, **Opsgenie** and **Alert Manager** as the sources of incidents/alerts. More specifically, we use a webhook endpoint that is triggered by these different vendors that sets off the investigation process.

To configure these webhooks, go to the "Webhooks" page inside your organization settings page. There, you can find instructions for each vendor.

The steps usually involve:

1. Generating a secret from your organization's dashboard.
2. Adding the secret to the webhook HTTP headers in the corresponding source.

:::info
To learn more about webhooks, check the [Webhooks](../04-Webhooks/01-PagerDuty.md) section.
:::

### Create a knowledge graph

Creating a knowledge graph is a crucial step in the setup process. It allows Merlinn to search contextual
information that might be relevant for the investigation.

Here is a short video that demonstrates how to create a knowledge graph. It usually takes 5-30 minutes (depending on the amount of data) to create a knowledge graph, so we skipped the waiting to show the final result:

<div style={{ position: 'relative', paddingBottom: '57.50798722044729%', height: 0 }}>
    <iframe
    src="https://www.loom.com/embed/8e11837657df42f5b7d6892ac3b80522?sid=90bd74b7-ef38-4fa7-b429-d37b440670a3"
    title="Embedded Video"
    frameBorder="0"
    allowFullScreen
    style={{ position: 'absolute', top: 0, left: 0, width: '100%', height: '100%' }}
    ></iframe>
</div>

## Usage

Once everything is set up, you can start using Merlinn. It'd have access to your tools and knowledge graph.

There are several ways to interact with the assistant.

### Incident investigation

Merlinn can now start investigating incidents automatically and give some contextual findings. For example:
<img src="../img/doc-imgs/usage-incident-investigation.png" style={{width: "50%"}} />

### Private chat

You can send direct messages to Merlinn and have a conversation with it. For example:
<img src="../img/doc-imgs/usage-direct-message.png" style={{width: "50%"}} />

### Incident thread

You can interact with Merlinn in your incidents threads by simply mentioning it with **@Merlinn**. For example:
<img src="../img/doc-imgs/usage-incident-thread.png" style={{width: "50%"}} />
