---
sidebar_class_name: github
---

# Github

This guide shows you how to integrate Merlinn with Github.

## Overview

Merlinn utilizes your Github repos in order to shed light on real-time issues in production. It can access commits, pull-requests, branches, releases and more. Merlinn uses the standard OAuth flow to connect to Github.

**For more information, go to [Github's documentation](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/authorizing-oauth-apps).**

## Prerequisites

- Working environment with an organization. If you don't have one, head over to the [setup](../02-Getting%20started/01-Setup%20Merlinn.md) page.
- Github PAT token. Visit [this](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) page to learn how to create one. Note: if you want to read private/org repos, make sure your token has the necessary permissions.

## Setup

Follow these steps to connect Merlinn to Github:

1. Inside your organization settings, go to "Integrations".
2. Locate the "Github" integration and click "Add".
3. Inside the input field, put your PAT key.
4. In the "Repositories to sync" input, you need to mention the repositories you wish to index in the knowledge base. If you'll leave this field empty, all of your repositories (the ones you can see for yourself) will be indexed.
5. Click "Connect".
