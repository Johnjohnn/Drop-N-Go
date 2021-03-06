# Drop-N-Go
Drag and drop resources Link:
https://www.w3schools.com/html/html5_draganddrop.asp
Example 
<!DOCTYPE HTML>
<html>
<head>
<script>
function allowDrop(ev) {
  ev.preventDefault();
}

function drag(ev) {
  ev.dataTransfer.setData("text", ev.target.id);
}

function drop(ev) {
  ev.preventDefault();
  var data = ev.dataTransfer.getData("text");
  ev.target.appendChild(document.getElementById(data));
}
</script>
</head>
<body>

<div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>

<img id="drag1" src="img_logo.gif" draggable="true" ondragstart="drag(event)" width="336" height="69">

</body>
</html>


Make an Element Draggable
First of all: To make an element draggable, set the draggable attribute to true:

<img draggable="true">
Where to Drop - ondragover
The ondragover event specifies where the dragged data can be dropped.

By default, data/elements cannot be dropped in other elements. To allow a drop, we must prevent the default handling of the element.

This is done by calling the event.preventDefault() method for the ondragover event:

event.preventDefault()

Do the Drop - ondrop
When the dragged data is dropped, a drop event occurs.

In the example above, the ondrop attribute calls a function, drop(event):

function drop(ev) {
  ev.preventDefault();
  var data = ev.dataTransfer.getData("text");
  ev.target.appendChild(document.getElementById(data));
}
Code explained:

Call preventDefault() to prevent the browser default handling of the data (default is open as link on drop)
Get the dragged data with the dataTransfer.getData() method. This method will return any data that was set to the same type in the setData() method
The dragged data is the id of the dragged element ("drag1")
Append the dragged element into the drop element