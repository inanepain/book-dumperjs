---
description: Assert logging examples.
---

# Examples: assert

{% hint style="success" %}
@since **2.4.3** assert available on Dumper class not only instances.
{% endhint %}

#### Simple

```javascript
// log an error if an object has an invalid id (null).

const id = playground.get('id');
logger.assert(id, `invalid id: #{id}`);
```

#### Extended

Negative example: Do something if assertion test is true.

```javascript
// log an error if an object has an invalid id, assuming the id must be a number.
// if the assertion takes place, fix the problem

const id = playground.get('id');

// Dumper.assert will log an error if test fails and the if is skipped.
// N.B: note the `!` in the if. Dumper returns IF assertion fails
// So the if reads as such: if NOT assertion fails
if (!logger.assert(id, `invalid id: #{id}`)) {
    playground.set('id', UUID.generateV4());
}
```

Positive example: When assertion fails, run code (possibly clean up)

```javascript
// Handle clean up if assertion fails

// If the transaction fails, notify involved accounts
if (Dumper.assert(acc1.transfer(amount, acc2), 'Transfer', acc1, acc2, amount)) {
    acc1.notify(new TEN(/*stuff*/));
    ...
}
```
