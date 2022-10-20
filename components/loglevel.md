---
description: >-
  Log Levels are used to filter message allowing only this will a higher or
  equal level to pass
---

# LogLevel

## The Levels

Each log method has an equivalent LogLevel which is also it's lowest cut off level. Any level higher will prevent that method logging its messages.&#x20;

* TRACE
* DEBUG
* INFO
* TIME
* WARN
* ERROR
* OFF

### TRACE

The lowest level, enabling all logging.

### OFF

The highest level, disabling all logging.

## Dumper Level

A dumper only logs messages of an equal or higher level then the method used. Thus trace logs only if its dumpers level is TRACE.

{% hint style="warning" %}
The log & assert methods are only effect by the OFF LogLevel
{% endhint %}
