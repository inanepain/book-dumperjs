---
description: Console logging methods
---

# Advanced Log Methods

## assert

{% hint style="success" %}
@since **2.4.3** assert available on Dumper class not only instances.
{% endhint %}

Only logs the messages if condition is \`false\` and level allows.

Returns true if message logged.

`assert(boolean condition, mixed messages...): boolean logged`

{% content-ref url="examples-assert.md" %}
[examples-assert.md](examples-assert.md)
{% endcontent-ref %}

## count

Log the number of times this line has been called with the given label.

`count(string label = 'default')`

<details>

<summary>countReset</summary>

Resets the value of the counter with the given label.

`countReset(string label = default)`

</details>

{% content-ref url="examples-count.md" %}
[examples-count.md](examples-count.md)
{% endcontent-ref %}

## group

Works like `console.group`.

## profile

## table (and similar)

## record

## time

