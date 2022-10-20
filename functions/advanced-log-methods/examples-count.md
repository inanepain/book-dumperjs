---
description: Count logging examples.
---

# Examples: count

#### Count usage

```javascript
# count how often a function is called and item in array just for fun.

function testCount(label) {
    logger.count('test');
    logger.count(label);
}

for (let i of ['a', 'b', 'a', 'c', 'a']) testCount(i);

# will log something like this:
# [Example] - test: 1
# [Example] - a: 1
# [Example] - test: 2
# [Example] - b: 1
# [Example] - test: 3
# [Example] - a: 2
# [Example] - test: 4
# [Example] - c: 1
# [Example] - test: 5
# [Example] - a: 3

# reseting a label
logger.countReset('a');
logger.count('a') # 1
logger.count('b') # 2
```
