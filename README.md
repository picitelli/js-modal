# Javascript modal
A simple CSS-driven vanilla Javascript modal plugin.

- Lightweight, no dependencies
- Customizable through CSS
- Works in IE9 and up

## Usage
Reference the modal stylesheet in the document head

```html
<link rel="stylesheet" href="css/modal.css">
```

Reference the modal plugin before the body ends
```html
<script src="js/modal.js"></script>
```

Create a modal element in the document and specify an `id`
```html
<div class="modal" id="modal-example">
  <div class="modal__window">...</div>
</div>
```

Create a button element within the modal that has a `data-close-modal` attribute
```html
<button type="button" data-close-modal>Close modal</button>
```

*Note: You can create as many close buttons within the modal as you like. Any element with a `data-close-modal` attribute living inside the modal will trigger the closing of the modal when clicked.*

Modal element markup example:
```html
<div class="modal" id="modal-example">
  <div class="modal__window">
    <button class="modal__close-btn" type="button" data-close-modal>X</button>
    <div class="modal__header">
       <h2 class="modal__title">Title of modal</h2>
     </div>
     <div class="modal__content">
       <!-- Modal content -->
       <button type="button" data-close-modal>Close modal</button>
     </div>
  </div>
</div>
```

Outside of the modal, if using a button element to trigger the opening of the modal, define the trigger button and reference the `id` of the modal as the `data-trigger-modal` attribute value
```html
<button type="button" data-trigger-modal="modal-example">Trigger Example modal</button>
```

In your JS, reference the modal element, pass it in as an argument and initialize an instance of the modal

```javascript
var modalEl = document.getElementById('modal-example');
var modalExample = new Modal(modalEl);
modalExample.init();
```

Click on the trigger button to open the modal and that's all there is to it!

Additionally, you can open and close a modal using the `openModal` and `closeModal` methods

```javascript
modalExample.openModal();
```

```javascript
modalExample.closeModal();
```

## Plugin options
Option | Type | Default | Description
--- | --- | --- | ---
activeClass | string | 'modal--active' | Active class set to the modal when it opens
bodyClass | string | 'modal-is-active' | Active class set to the body when the modal opens
overlay | boolean | true | Enables the modal overlay
overlayClass | string | 'modal__overlay' | Class for the modal overlay
openCallback | function | null | Callback that fires after the modal opens
closeCallback | function | null | Callback that fires after the modal closes