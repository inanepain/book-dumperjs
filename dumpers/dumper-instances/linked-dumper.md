---
description: >-
  Dumpers created using get are named and linked to their creating dumper or the
  Global Dumper.
---

# Linked Dumper

## Overview

Linked dumpers are chained to the Dumper creating them if that Dumper is also a Linked dumper or else they are linked to the Global Dumper if it or a Single dumper created it.

## Features

* The name is print before its messages: `[ User ] - Message`
* Child Dumpers inherit the name: `[ User - Auth ]`
* Chained Levels: **a child can opt-out of chained effects but still hands them to its children.**
  * Global changes to LogLevel effect **ALL** Linked dumpers.
  * Changes to a linked dumper effects its child chain.
* Child Cache:
  * Calling get on a Linked Dumper stores that child in its cache.
  * Repeated gets can be use to get that child. As a new child it **not** created, rather the existing one is returned.
  * Linked dumpers have their own cache independent of other linked dumpers to names across linked dumpers are unique.

## Example

```javascript
var cdump = Dumper.get('Car', { level: 'DEBUG' }); // Car Dumper
cdump.debug('Building...'); // [ Car ] - Building...

edump = cdump.get('Engine'); // Car -> Engine Dumper
edump.warn('Temp: High!'); // [ Car - Engine ] - Temp: High!
adump = edump.get('Alert', { level: 'WARN', bubbling: { listen: false} }); // new Linked that ignores chained level updates
edump.get('Alert').optionBubbleFromParent; // false, can also be set

edump.get('Alert') === adump; // true. get will return an cached dumper rather than create a new dumper.
adump.warn('FIRE!!!'); // [ Car - Engine - Alert ] - FIRE!!!

Dumper.level = 'INFO';
// Sets:
// - default for new Standard
// - Level existing Named
edump.get('Alert').getLevel(); // 'WARN'
edump.level; // 'INFO'
```
