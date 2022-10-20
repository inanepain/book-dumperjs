---
description: The two Dumper instances and how they differ.
---

# Dumper Instances

## Overview

You can instantiate two types of Dumper instances that differ in their relation to other instances and the Global Dumper.

### Single Dumper

A stand alone dumper created using the **`new`** keyword that is unaffected by scope and Global changes to LogLevels.

{% content-ref url="single-dumper.md" %}
[single-dumper.md](single-dumper.md)
{% endcontent-ref %}

### Linked Dumper

A dumper linked to the Linked dumper that created it or the Global Dumper if created by a Single dumper. These dumpers are created using the **`get`** method on a dumper and supplying a **name**.

{% content-ref url="linked-dumper.md" %}
[linked-dumper.md](linked-dumper.md)
{% endcontent-ref %}

### Children

The new Dumper is a child of the original Dumper.

{% content-ref url="children.md" %}
[children.md](children.md)
{% endcontent-ref %}
