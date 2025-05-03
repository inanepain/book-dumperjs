---
description: Changing dumper options
---

# Option Methods

### optionAssertTime

### optionAssertLimit

## Level Bubbling

{% hint style="info" %}
Since [v2.3.0](../../history/changelog.md#2-3-0-2021-sep-30)
{% endhint %}

### optionBubbleFromParent

Sets if a Dumper accepts level changes from it's parent.

default: **true**

### optionBubbleToChildren

This option tells Dumper to bubble level changes to it's children.

default: **true**

### optionBubble (shortcut method)

This sets both bubble options at once. As long as both options match this will return that value otherwise it will return `null`.

default: **true**
