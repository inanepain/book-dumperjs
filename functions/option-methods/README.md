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

Dumpers bubble level changes keeping their children's level the same as their own. Bubbling has two options with which you stop the propagation down a branch or just have it skip specific Dumpers leaving their level unaffected yet still changing it's children.

### optionBubbleFromParent

This option set if a Dumper will accept level changes bubbled up from it's parent.

Option: [`options.bubbling.listen`](../../components/options.md#listen)``

default: **true**

### optionBubbleToChildren

This option tells Dumper to bubble level changes to it's children.

Option: [`options.bubbling.trigger`](../../components/options.md#trigger)``

default: **true**

### optionBubble (shortcut method)

This sets both bubble options at once. As long as both options match this will return that value otherwise it will return `null`.

default: **true**
