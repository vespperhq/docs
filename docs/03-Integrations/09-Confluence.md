---
sidebar_class_name: confluence
---

# Confluence

This guide shows you how to integrate Vespper with Confluence. It is very similar to the [Jira](./08-Jira.md) guide.

## Overview

Vespper uses Confluence knowledge base in order to access important knowledge that might be relevant for a production issue. It can access your pages, comments, attachments and more.
On the technical side, Vespper uses the standard Atlassian OAuth flow in order to authenticate with Confluence.

**For more information, go to [Atlassian's documentation](https://developer.atlassian.com/cloud/Confluence/platform/oauth-2-3lo-apps/).**

## Prerequisites

- Working environment with an organization. If you don't have one, head over to the [setup](../02-Getting%20started/01-Setup%20Vespper.md) page.
- Atlassian API key. Visit [this](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/) page to learn how to create one.

## Setup

Follow these steps to connect Vespper to Confluence:

1. Inside your organization settings, go to "Integrations".
2. Locate the "Confluence" integration and click "Add".
3. Insert your Atlassian API key inside the "API key" field.
4. Select your region in the "Region" field.
5. Click "Connect"

That's it! You can go back to Vespper's dashboard.
