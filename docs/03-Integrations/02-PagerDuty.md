---
sidebar_class_name: pagerduty
---

# PagerDuty

This guide shows you how to integrate Vespper with PagerDuty.

## Overview

Vespper uses PagerDuty in order to obtain information about live incidents and alerts.

On the techical side, Vespper uses the standard OAuth flow to connect to PagerDuty. For more information, check the [PagerDuty documentation](https://developer.pagerduty.com/docs/f59fdbd94ceab-o-auth-functionality).

## Prerequisites

- Working environment with an organization. If you don't have one, head over to the [setup](../02-Getting%20started/01-Setup%20Vespper.md) page.
- PagerDuty API token. You can learn how to generate one in this [guide](https://support.pagerduty.com/docs/api-access-keys).

## Setup

Follow these steps to connect Vespper to PagerDuty:

1. Inside your organization settings, go to "Integrations".
2. Locate the "PagerDuty" integration and click "Add".
3. Inside the input field, put your PagerDuty API key.
