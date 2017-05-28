---
title: Sweet Alert Options
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
    language:
        - javascript
        - js
menu: Options
slug: options
---

|  Option  |   Default   |   Description    |
|----------|-------------|------------------|
| title    | null (required)  |   The title of the modal. It can either be added to the object under the key "title" or passed as the first parameter of the function.  |
| text | null | A description for the modal. It can either be added to the object under the key "text" or passed as the second parameter of the function. |
| type | null | The type of the modal. SweetAlert comes with 4 built-in types which will show a corresponding icon animation: "warning", "error", "success" and "info". You can also set it as "input" to get a prompt modal. It can either be put in the object under the key "type" or passed as the third parameter of the function. |
| allowEscapeKey | true | If set to true, the user can dismiss the modal by pressing the Escape key. |
| customClass | null | A custom CSS class for the modal. It can be added to the object under the key "customClass". |
| allowOutsideClick | false | If set to true, the user can dismiss the modal by clicking outside it. |
| showCancelButton | false | If set to true, a "Cancel"-button will be shown, which the user can click on to dismiss the modal. |
| showConfirmButton | true | If set to false, the "OK/Confirm"-button will be hidden. Make sure you set a timer or set allowOutsideClick to true when using this, in order not to annoy the user. |
| confirmButtonText | "OK" | Use this to change the text on the "Confirm"-button. If showCancelButton is set as true, the confirm button will automatically show "Confirm" instead of "OK". |
| confirmButtonColor | "#AEDEF4" | Use this to change the background color of the "Confirm"-button (must be a HEX value). | 	
| cancelButtonText | "Cancel" | Use this to change the text on the "Cancel"-button. | 	 	
| closeOnConfirm | true | Set to false if you want the modal to stay open even if the user presses the "Confirm"-button. This is especially useful if the function attached to the "Confirm"-button is another SweetAlert. |	 	
| closeOnCancel | true | Same as closeOnConfirm, but for the cancel button. | 	 	
| imageUrl | null | Add a customized icon for the modal. Should contain a string with the path to the image. | 	 	
| imageSize | "80x80" | If imageUrl is set, you can specify imageSize to describes how big you want the icon to be in px. Pass in a string with two values separated by an "x". The first value is the width, the second is the height. | 	 	
| timer | null | Auto close timer of the modal. Set in ms (milliseconds). | 	 	
| html | false | If set to true, will not escape title and text parameters. (Set to false if you're worried about XSS attacks.) |
| animation | true | If set to false, the modal's animation will be disabled. Possible (string) values : pop (default when animation set to true), slide-from-top, slide-from-bottom |
| inputType | "text" | Change the type of the input field when using type: "input" (this can be useful if you want users to type in their password for example). |
| inputPlaceholder | null | When using the input-type, you can specify a placeholder to help the user. |
| inputValue | null | Specify a default text value that you want your input to show when using type: "input" |
| showLoaderOnConfirm | false | Set to true to disable the buttons and show that something is loading. |
