---
description: Dumper method documentation
---

# Methods

## Overview

Methods have been broken up into Log, Level, Option and Advanced method groups for simplicity. The rest of the methods will be detailed here Initially the differences between methods based on Dumper types will be documented here.

## Method Groups

* Log: dump, info, etc...
* Level: setting LogLevel and what they effect
* Option: changing settings
* Advanced: group, time, etc...

### children()

This returns an object where it's properties are the names of it's children and their values are the actual Dumpers themselves.

{% hint style="info" %}
As of [v2.5.0](../history/changelog.md#id-2.5.0-2025-may-03) you can also use the [`kids`](properties.md#kids) property.
{% endhint %}
