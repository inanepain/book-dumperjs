---
description: Dumper's inherit their options not specified at instantiation.
---

# Options

## Default Options

What Dumper's defaults look like.

```javascript
{
        clear: false,
        level: LogLevel.WARN,
        bubbling: {
            listen: true,
            trigger: true    
        },
        trickle: 1000,
        assert: {
            time: false,
            hhmmss: false,
            limit: 0
        }
}
```

{% hint style="info" %}
The defaults are not fixed or singular. Rather each Dumper imparts it's options to any Dumper created from itself.
{% endhint %}

## The Options

### clear

Default: **false**

When set to **true**, Dumper clears the console when creating new Dumpers.

### level

Default: **WARN**

The LogLevel of the new Dumper.

### bubbling

LogLevel change propagation.

#### - listen

Default: **true**

Accept level changes bubbled up from parent.

#### - trigger

Default: **true**

Forward level changes on to children.

{% hint style="info" %}
@see [Bubbling.Option.Methods](../functions/option-methods/#level-bubbling) for more in depth documentation.
{% endhint %}

### trickle

Default: **1000**

The minimum time in **ms** between output.

If you are dumping a process that runs 100 times a second, you would be swamped. Trickle lets you throttle this so that only 1 (default) message is dumped per second.

### assert

#### - assert time

#### - assert hhmmss

#### - assert limit
