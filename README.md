# Event-Bubbling-and-Capturing---JS

🎲Event bubbling and capturing are two ways of event propagation in the HTML DOM API, when an event occurs in an element inside another element, and both elements have registered a handle for that event. The event propagation mode determines in which order the elements receive the event.

🎲With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.

🎲With capturing, the event is first captured by the outermost element and propagated to the inner elements.

🎲Capturing is also called "trickling", which helps remember the propagation order:
trickle down, bubble up


🎲We can use the addEventListener(type, listener, useCapture) to register event handlers for in either bubbling (default) or capturing mode. To use the capturing model pass the third argument as true.

