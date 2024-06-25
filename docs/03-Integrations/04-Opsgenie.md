---
sidebar_class_name: opsgenie
---

# Opsgenie

This guide shows you how to integrate Merlinn with Opsgenie.

## Overview

Merlinn uses Opsgenie to obtain information about real time production alerts & incidents.

Merlinn is connected to Opsgenie via Opsgenie's API integration. Namely, you generate an API key
in your Opsgenie account and you associate it with your Merlinn's organization.

**To learn how to create an API key, go to Opsgenie's official [docs](https://support.atlassian.com/opsgenie/docs/create-a-default-api-integration/).**

## Prerequisites

- Working environment with an organization. If you don't have one, head over to the [setup](../02-Getting%20started/01-Setup%20Merlinn.md) page.

## Setup

Follow these steps to connect Merlinn to Opsgenie:

1. Inside your organization settings, go to "Integrations".
2. Locate the "Opsgenie" integration and click "Add".
3. In the modal, insert your API key. **See [here](https://support.atlassian.com/opsgenie/docs/create-a-default-api-integration/) on how to create it.**
4. Choose your region (can either be US or EU).
5. Click "Connect".
