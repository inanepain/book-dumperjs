---
description: Setting the Level and its effect
---

# Level Methods

## LogLevel

Filters any log message with a level lower than the set level.

## getLevel

This returns the current LogLevel of the Dumper

{% hint style="info" %}
Since [v2.1.0](../history/changelog.md#2-1-0-2021-jun-04): You can use the level property. e.g.: Dumper.level
{% endhint %}

## setLevel(LogLevel)

Sets the current Dumper's LogLevel. Level changes bubble along child chains updating them as well. The stop&#x20;

{% hint style="info" %}
Since [v2.1.0](../history/changelog.md#2-1-0-2021-jun-04): You can use the level property. e.g.: Dumper.level=\`info\`
{% endhint %}

### LogLevel

This can be either:

* A LogLevel object: Dumper.INFO
* The LogLevel name: "INFO"
* LogLevel number: 3

{% hint style="info" %}
LogLevel changes bubble. What this means is that setting a Dumpers level will also set the level for all of it's dependents to match.\
&#xNAN;**@see** [Options.Bubbling](option-methods/#level-bubbling): Easy adjust the if/how/when of bubbling.
{% endhint %}

## Example

```javascript
dumper.getLevel() // Object LogLevel: WARN
ulog = dumper.get('Users'); // New Named. NB: Not linked to dumper (Standard) but does inherit its LogLevel
ulog.getLevel() // Object LogLevel: WARN
ulog.setLevel('DEBUG');
Dumper.level = 'InFo'; // Only Dumper has the level property. same as set/getLevel

dumper.getLevel(); // WARN
ulog.getLevel(); // INFO
Dumper.getLevel(); // INFO
```
