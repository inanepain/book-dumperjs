---
description: Dumper's history
---

# Changelog

### 2.4.3 (2022 Aug 16)

* assert now works from Dumper class not just it's instances.
* Stupidly Dumper was removed from global scope, this has been fixed.
* Object creation uses \`null\` resulting in them being cleaner and leaner.
* Minor fixes, optimisations and language updates.

### 2.4.2 (2022 Feb 16)

* assert now returns boolean - if the assert run or not.
* code: cleaned up "mucho mass" redundent code.

### 2.3.0 (2021 Sep 30)

* Improved how setLevel propagates. Replaced `optionUpdateChain` with `optionBubbleFromParent` and `optionBubbleToChildren` for individual control.
* LogLevel checking improved.
* Optimisations and general cleanup of code.

### 2.2.0 (2021 Jul 23)

* Add the children() method which returns an object who's properties as child names and the values are the children themselves.

### 2.1.0 (2021 Jun 04)

> Mostly under the hood changes and optimisations

* Added level property that functions just as set/getLevel
* Set level properties to enumerable
* Many improvements to: code, memory, speed, etc...

### 2.0.0 (2020 Jul 02)

* Removed requirement: Inane (I)
* Priority filtering works from Dumper class now so you never need to create an instance if you so wish

### 1.5.0 (2020 Jun 24)

* Removed requirement: Logger

### 1.4.2 (2020 Jun 18)

* Named Dumpers (instances) append their name to parent's name
* Cleaned the code up a bit
* Removed Dumper from name

### 1.4.1 (2020 Jun 14)

* Removed requirement: underscore (\_)

### 1.4.0 (2020 Jun 12)

* Log priority level no longer dependent on Logger
* Dumper.dump added as static method for instant use
* Code shuffled around and cleaned up a tad
* Updated the jsdoc comments

### 1.3.0 (2020 Jun 08)

* Added a dump function that maps to a global dump method if found else its just an empty function

### 1.2.1 (2020 Jun 01)

* Update: Calling get on an instance now correctly duplicates its options into the new child instance

### 1.2.0 (2020 Apr 18)

* Fix: Assert throws error if no context defined
* New: Dumper instances are cached for quicker recall
* Update: LogCollection removed (About time)

### **1.1.0 (2020 Apr 16)**

* Fix: Corrected internal Dumper references to itself
* New: loggerDefaults - Dumper now automatically calls this with sane defaults so you don't have too

### **1.0.0 (2020 Feb 14)**

* Option: (bool) assert.hhmmss: show time between assert messages as hh:mm:ss
* Assert: Fixed missing context in output
