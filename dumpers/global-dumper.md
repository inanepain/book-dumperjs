---
description: >-
  Using the Dumper class as is to get started quickly with the same methods from
  console.
---

# Dumper

## Overview

This is also referred to as the Global Dumper since it sits in the Global Scope.

## Usage

Dumper and `console` use the same syntax, it can't be easier to use.

```javascript
Dumper.getLevel(); // WARN: checking current level
Dumper.setLevel(Dumper.TRACE); // Now all logs will show

Dumper.trace('Extreme detail, usually overkill.', someObject); //
Dumper.debug('This works yay!'); //
Dumper.info('Hey, this is easy.'); //
Dumper.warn('What out, this aint right.'); // What out, this aint right.
Dumper.error('Matrix unplugged!'); // Matrix unplugged!
```

{% hint style="info" %}
Not evey log showed? Dumper's default LogLevel is `WARN`.
{% endhint %}

### LogLevel

Let's try that again only this let's change Dumper's default level from `WARN` to `TRACE` using the `Dumper.setLevel` method.

```javascript
Dumper.getLevel(); // WARN: checking current level
Dumper.setLevel(Dumper.TRACE); // Now all logs will show

Dumper.trace('Extreme detail, usually overkill.', someObject); // Extreme det...
Dumper.debug('This works yay!'); // This...
Dumper.info('Hey, this is easy.'); // Hey...
Dumper.warn('What out, this aint right.'); // What...
Dumper.error('Matrix unplugged!'); // Matrix...
```

Easy, right? Dumper handles most of the other console methods as well.

#### LogLevel.OFF

A special mention should be made about `Dumper.setLevel('off')`. This effects **ALL** dumpers and **STOPS** any log messages from being written to console regardless of custom settings or later level changes to instance dumpers.

{% content-ref url="../components/loglevel.md" %}
[loglevel.md](../components/loglevel.md)
{% endcontent-ref %}

{% hint style="danger" %}
Global Dumper has a special effect when set to LogLevel.OFF which prevents any instance dumpers from logging messages.
{% endhint %}
