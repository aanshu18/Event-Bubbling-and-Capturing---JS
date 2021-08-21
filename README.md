# Event-Bubbling-and-Capturing---JS
  https://javascript.info/bubbling-and-capturing

🎲Event bubbling and capturing are two ways of event propagation in the HTML DOM API, when an event occurs in an element inside another element, and both elements have registered a handle for that event. The event propagation mode determines in which order the elements receive the event.

🎲With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.

🎲With capturing, the event is first captured by the outermost element and propagated to the inner elements.

🎲Capturing is also called "trickling", which helps remember the propagation order:
trickle down, bubble up


🎲We can use the addEventListener(type, listener, useCapture) to register event handlers for in either bubbling (default) or capturing mode. To use the capturing model pass the third argument as true.

🎲Events first are captured down to deepest target, then bubble up. In IE<9 they only bubble.
All handlers work on bubbling stage excepts addEventListener with last argument true, which is the only way to catch the event on capturing stage.
Bubbling/capturing can be stopped by event.cancelBubble=true (IE) or event.stopPropagation() for other browsers.


🎲Almost all events bubble.
For instance, a focus event does not bubble. There are other examples too, we’ll meet them. But still it’s an exception, rather than a rule, most events do bubble.



🎲event.target
A handler on a parent element can always get the details about where it actually happened.
The most deeply nested element that caused the event is called a target element, accessible as event.target.
Note the differences from this (=event.currentTarget):
event.target – is the “target” element that initiated the event, it doesn’t change through the bubbling process.
this – is the “current” element, the one that has a currently running handler on it.
For instance, if we have a single handler form.onclick, then it can “catch” all clicks inside the form. No matter where the click happened, it bubbles up to <form> and runs the handler.
In form.onclick handler:
this (=event.currentTarget) is the <form> element, because the handler runs on it.
event.target is the actual element inside the form that was clicked.

  
🎲Stopping bubbling
A bubbling event goes from the target element straight up. Normally it goes upwards till <html>, and then to document object, and some events even reach window, calling all handlers on the path.
But any handler may decide that the event has been fully processed and stop the bubbling.
The method for it is event.stopPropagation().
For instance, here body.onclick doesn’t work if you click on <button>:
<body onclick="alert(`the bubbling doesn't reach here`)">
  <button onclick="event.stopPropagation()">Click me</button>
</body>
  
  🎲Handlers added using on<event>-property or using HTML attributes or using two-argument addEventListener(event, handler) don’t know anything about capturing, they only run on the 2nd and 3rd phases.
