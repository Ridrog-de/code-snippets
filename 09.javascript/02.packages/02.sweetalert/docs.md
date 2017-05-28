---
title: Sweet Alert Package
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
    language:
        - javascript
        - js
menu: Sweet Alert
slug: sweet-alert
---

[Official Site](http://t4t5.github.io/sweetalert/)



## Usage

**Einfach**

```js
swal("Here's a message!")
```


**Mit Text unterm Titel**

```js
swal("Here's a message!", "It's pretty, isn't it?")
```

**Erfolgsnachricht**

```js
swal("Good job!", "You clicked the button!", "success")
```

**Mit Bestätigen/Abbrechen Knopf**

```js
swal({
  title: "Are you sure?",
  text: "You will not be able to recover this imaginary file!",
  type: "warning",
  showCancelButton: true,
  confirmButtonColor: "#DD6B55",
  confirmButtonText: "Yes, delete it!",
  closeOnConfirm: false
},
function(){
  swal("Deleted!", "Your imaginary file has been deleted.", "success");
});
```

**Mit verschiedenen Funktionen für Bestätigen und Abbrechen**

```js
swal({
  title: "Are you sure?",
  text: "You will not be able to recover this imaginary file!",
  type: "warning",
  showCancelButton: true,
  confirmButtonColor: "#DD6B55",
  confirmButtonText: "Yes, delete it!",
  cancelButtonText: "No, cancel plx!",
  closeOnConfirm: false,
  closeOnCancel: false
},
function(isConfirm){
  if (isConfirm) {
    swal("Deleted!", "Your imaginary file has been deleted.", "success");
  } else {
	    swal("Cancelled", "Your imaginary file is safe :)", "error");
  }
});
```

**Mit einem eigenen Icon**

```js
swal({
  title: "Sweet!",
  text: "Here's a custom image.",
  imageUrl: "images/thumbs-up.jpg"
});
```

**Mit HTML in der Nachricht**

```js
swal({
  title: "HTML <small>Title</small>!",
  text: "A custom <span style="color:#F8BB86">html<span> message.",
  html: true
});
```



**Schließt sich autmatisch**

```js
swal({
  title: "Auto close alert!",
  text: "I will close in 2 seconds.",
  timer: 2000,
  showConfirmButton: false
});
```


**Mit Eingabge**

```js
swal({
  title: "An input!",
  text: "Write something interesting:",
  type: "input",
  showCancelButton: true,
  closeOnConfirm: false,
  animation: "slide-from-top",
  inputPlaceholder: "Write something"
},
function(inputValue){
  if (inputValue === false) return false;
  
  if (inputValue === "") {
    swal.showInputError("You need to write something!");
    return false
  }
  
  swal("Nice!", "You wrote: " + inputValue, "success");
});
```


**Mit Ladeanimation**

```js
swal({
  title: "Ajax request example",
  text: "Submit to run ajax request",
  type: "info",
  showCancelButton: true,
  closeOnConfirm: false,
  showLoaderOnConfirm: true,
},
function(){
  setTimeout(function(){
    swal("Ajax request finished!");
  }, 2000);
});
```