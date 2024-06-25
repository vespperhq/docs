---
sidebar_class_name: jira
---

# Jira

This guide shows you how to integrate Merlinn with Jira.

## Overview

Merlinn uses Jira knowledge base in order to shed light on real-time issues in production. It can access tickets, boards, comments and other information that might be relevant to a real production incident.

On the technical side, Merlinn uses the standard Atlassian OAuth flow in order to authenticate with Jira.

**For more information, go to [Atlassian's documentation](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/).**

## Prerequisites

- Working environment with an organization. If you don't have one, head over to the [setup](../02-Getting%20started/01-Setup%20Merlinn.md) page.
- Atlassian API key. Visit [this](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/) page to learn how to create one.

## Setup

Follow these steps to connect Merlinn to Jira:

1. Inside your organization settings, go to "Integrations".
2. Locate the "Jira" integration and click "Add".
3. Insert your user email inside the "Atlassian User Email" field.
4. Insert your Atlassian API key inside the "API token" field.
5. Insert your site URL inside the "Site URL" field. This should look something like this: `merlinn-co-jira.atlassian.net`, without `https://` and trailing slash `/`.
6. Click "Connect"

That's it! You can go back to Merlinn's dashboard.
