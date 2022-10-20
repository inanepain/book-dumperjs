---
description: >-
  An independent Dumper with its own options and filters that is unaffected by
  other Dumpers.
---

# Single Dumper

## Overview

Single dumpers&#x20;

A Single Dumper is created using the new key words on the Dumper class

Single Dumpers are independant of Global and Linked dumpers including any Linked dumpers created from them. This excludes them from any Global changes to the LogLevel. Only calling setLevel on them directly changes their level.
