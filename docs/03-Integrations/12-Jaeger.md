---
sidebar_class_name: jaeger
---

# Jaeger

This guide shows you how to integrate Merlinn with Jaeger.

## Overview

Merlinn can access your Jaeger instance and query traces that are related to alerts and incidents. Merlinn is connected to Jaeger via the Jaeger Query Service API.

## Prerequisites

- Working environment with an organization. If you don't have one, head over to the [setup](../02-Getting%20started/01-Setup%20Merlinn.md) page.

## Setup

Follow these steps to connect Merlinn to Jaeger:

1. Inside your organization settings, go to "Integrations".
2. Locate the "Jaeger" integration and click "Add".
3. In the modal, insert your Jaeger instance URL. This should be the URL which points to your Jaeger UI. Behind the scenes, the system adds the "/api" suffix to your URL.
4. Click "Connect"

That's it! 🤖 Now Merlinn can access your traces in real time, when an alert occurs, and tries to find insights there.
