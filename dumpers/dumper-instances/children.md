---
description: Using children to control you logging. Dumper.children()
---

# Children

## How are babies made?

By simply calling `get('NewName')` on a Dumper you create a child of that Dumper. It's name will show up in the console as `GrandParentName - ParentName - Name.` Each successive child appends to this name.

Calling get('Name') again on the parent will return to same child make it unnecessary to store the child individually unless of course if it suits the situation.

### Logging with children

Children start life inheriting their parent's options but by changing these you can adjust the log level for various sections of your code.

Setting a level on a Dumper will bubble that level down through it's descendants. Each Dumper's [bubbling options](../../functions/option-methods/#level-bubbling) control how it reacts and if it will continue the propagation.

Finally, the `children()` method can be used to see a Dumper's direct decadents.

### Example

Not practical but you get the idea.

{% tabs %}
{% tab title="JavaScript" %}
```javascript
// Let's create out main Dumper
const logger = Dumper.get('App', {
    level: 'debug'
});

logger.log('My Level:', logger.level);

logger.log('');

// And some children and adjust their level by chaining commands.
logger.get('AreaA').log('Level', logger.get('AreaA').level);
logger.get('AreaB', {level: 'info'}).log('Level', logger.get('AreaB').level);
logger.get('AreaC').setLevel('warn').log('Level', logger.get('AreaC').level);
// a few more
logger.get('AreaD').get('AreaE').get('AreaF');
// lets save E & F to variables
const AE = logger.get('AreaD').get('AreaE'), AF = logger.get('AreaD').get('AreaE').get('AreaF');

// But this one we tell not to listen for level changes
logger.get('AreaD').optionBubbleFromParent = false;
// another not to propagate them
AE.optionBubbleToChildren = false;

// Lets set the parent level
logger.setLevel('error');

logger.log('');

// All the children have taken the new level
logger.get('AreaA').log('Level', logger.get('AreaA').level);
logger.get('AreaB').log('Level', logger.get('AreaB').level);
logger.get('AreaC').log('Level', logger.get('AreaC').level);

// Almost all
logger.get('AreaD').log('Level', logger.get('AreaD').level); // DEBUG: change not allowed but propagated.
AE.log('Level', logger.children().AreaD.children().AreaE.level); // ERROR: change allowed but...
AF.log('Level', AF.level); // DEBUG: the change propagation was stopped by it's parent.
```
{% endtab %}

{% tab title="Output" %}
```
[App] – "My Level:" – LogLevel {name: "DEBUG", value: 2}
[App] – ""
[App - AreaA] – "Level" – LogLevel {name: "DEBUG", value: 2}
[App - AreaB] – "Level" – LogLevel {name: "INFO", value: 3}
[App - AreaC] – "Level" – LogLevel {name: "WARN", value: 5}
[App - AreaA] – "Level" – LogLevel {name: "DEBUG", value: 2}
[App - AreaB] – "Level" – LogLevel {name: "INFO", value: 3}
[App - AreaC] – "Level" – LogLevel {name: "WARN", value: 5}
[App - AreaD] – "Level" – LogLevel {name: "DEBUG", value: 2}
[App - AreaD - AreaE] – "Level" – LogLevel {name: "DEBUG", value: 2}
[App - AreaD - AreaE - AreaF] – "LevelAreaF" – LogLevel {name: "DEBUG", value: 2}
[App] – ""
[App - AreaA] – "Level" – LogLevel {name: "ERROR", value: 8}
[App - AreaB] – "Level" – LogLevel {name: "ERROR", value: 8}
[App - AreaC] – "Level" – LogLevel {name: "ERROR", value: 8}
[App - AreaD] – "Level" – LogLevel {name: "DEBUG", value: 2}
[App - AreaD - AreaE] – "Level" – LogLevel {name: "ERROR", value: 8}
[App - AreaD - AreaE - AreaF] – "Level" – LogLevel {name: "DEBUG", value: 2}
```
{% endtab %}
{% endtabs %}
