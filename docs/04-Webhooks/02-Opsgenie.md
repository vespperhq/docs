---
sidebar_class_name: opsgenie
---

# Opsgenie

This guide shows you how to create a webhook to Vespper in your Opsgenie account.

## Overview

Vespper uses Opsgenie Webhooks Integration in order to be notified when incidents/alerts happen. Once an incident happens, Opsgenie will send a webhook to your Vespper account, kicking off the investigation.

For more information about Opsgenie webhooks, checkout the official [documentation](https://support.atlassian.com/opsgenie/docs/integrate-opsgenie-with-webhook/).

## Prerequisites

- Working environment with an organization. If you don't have one, head over to the [setup](../02-Getting%20started/01-Setup%20Vespper.md) page.
- A configured Opsgenie integration. To learn how to create one, check the [Opsgenie integration guide](../03-Integrations/04-Opsgenie.md).
- ngrok tunnel that forwards traffic to your local Vespper API. Install [ngrok](https://ngrok.com/docs/getting-started/), start a tunnel at port 3000 (`ngrok http 3000`) and copy the tunnel URL.

## Setup

Follow these steps to connect Vespper to Opsgenie:

1. Inside your organization settings, go to "Webhooks".
2. Locate the "Opsgenie" integration and click "Add".
3. In the modal, click "Generate" to generate a new secret and copy it.

Once you've obtained your secret, go to your Opsgenie account dashboard and follow these steps:

1. Go to Settings > Integrations > Add new integration.
2. Search **Webhook** and click it
3. Give it a name and click "Create".
4. Go to the integration settings and choose “Authenticate with a Webhook account”
5. In the Webhook URL, insert your ngrok tunnel URL followed by `/webhooks/opsgenie`, e.g `https://1234abcd.ngrok.io/webhooks/opsgenie`.
6. Add a custom header called **x-vespper-secret** and put your secret.
7. Mark the **Add Alert Description to Payload** and **Add Alert Details to Payload** options.
8. Click **Save**
9. In the Alert Actions section, choose only **Alert is created**

That's it! Now Vespper will be notified when an incident happens.
