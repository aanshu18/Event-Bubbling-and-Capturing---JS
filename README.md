# Event-Bubbling-and-Capturing---JS

🎲Event bubbling and capturing are two ways of event propagation in the HTML DOM API, when an event occurs in an element inside another element, and both elements have registered a handle for that event. The event propagation mode determines in which order the elements receive the event.

🎲With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.

🎲With capturing, the event is first captured by the outermost element and propagated to the inner elements.

🎲Capturing is also called "trickling", which helps remember the propagation order:
trickle down, bubble up


🎲We can use the addEventListener(type, listener, useCapture) to register event handlers for in either bubbling (default) or capturing mode. To use the capturing model pass the third argument as true.

Events first are captured down to deepest target, then bubble up. In IE<9 they only bubble.
All handlers work on bubbling stage excepts addEventListener with last argument true, which is the only way to catch the event on capturing stage.
Bubbling/capturing can be stopped by event.cancelBubble=true (IE) or event.stopPropagation() for other browsers.


Almost all events bubble.
For instance, a focus event does not bubble. There are other examples too, we’ll meet them. But still it’s an exception, rather than a rule, most events do bubble.
