# Menu Button
![Menu button](../../etc/menu-button.png)

A WAI-ARIA friendly menu button.

## Introduction
A menu button is a [button](https://www.w3.org/TR/wai-aria-practices/#button) that opens a 
[menu](https://www.w3.org/TR/wai-aria-practices/#menu). It is often styled as a typical push button with a 
downward pointing arrow or triangle to hint that activating the button will display a menu. 
The menu button has roles, attributes and behaviour as outlined in WAI-ARIA Authoring Practices.

A menu is a widget that offers a list of choices to the user, such as a set of actions or functions. A menu is (usually) 
opened, or made visible, by activating a menu button. When a user activates a choice in a menu, the menu (usually) closes.

## To include a MDLEXT **menu button** component:

&nbsp;1. Code a `<button>` element; this is the clickable toggle that will show and hide the menu. Include an `aria-controls` 
attribute whose value will match the id attribute of the unordered list coded in the next step. Inside the button, 
code a `<span>` element to hold the button caption text and a `<i>` element to contain a state icon.

```html
<button aria-controls="menu1">
  <span></span>
  <i></i>
</button>
```

&nbsp;2. Code a `<ul>` unordered list element; this is the container that holds the menu choices. Include an id attribute 
whose value will match the `aria-controls` attribute of the button element.

```html
<ul id="menu1">
</ul>
```

&nbsp;3. Inside the unordered list, code one `<li>` element for each choice. Add a text caption as appropriate.

```html
<ul id="menu1">
  <li>Small</li>
  <li>Medium</li>
  <li>Large</li>
</ul>
```

&nbsp;4. Add one or more MDL classes, separated by spaces, to the button, span and i elements using the class attribute.

```html
<button class="mdl-button mdl-js-button" aria-controls="menu1">
  <span>Select a value</span>
  <i class="material-icons">more_vert</i>
</button>
```

&nbsp;5. Add the `mdlext-js-menu-button` class to define the element as a menu button component.

```html
<button class="mdl-button mdl-js-button mdlext-js-menu-button" aria-controls="menu1">
  <span>Select a value</span>
  <i class="material-icons">more_vert</i>
</button>
```

&nbsp;6. Add the `mdlext-menu` class to the unordered list and the `mdlext-menu__item` class to the list items. 

```html
<ul id="menu1" class="mdlext-menu">
  <li class="mdlext-menu__item">Small</li>
  <li class="mdlext-menu__item">Medium</li>
  <li class="mdlext-menu__item">Large</li>
</ul>
```

The menu button component is ready for use.

### Examples

**A menu button with three options.**

```html
<button class="mdl-button mdl-js-button mdlext-js-menu-button" aria-controls="menu1">
  <span>Select a value</span>
  <i class="material-icons">more_vert</i>
</button>
<ul id="menu1" class="mdlext-menu">
  <li class="mdlext-menu__item">Small</li>
  <li class="mdlext-menu__item">Medium</li>
  <li class="mdlext-menu__item">Large</li>
</ul>
```

> **Note:** If the button and the menu has a common ancestor element, the `aria-controls` attribute of the button and 
the `id` attribute of the menu may be skipped.

```html
<div role="presentation">
  <button class="mdl-button mdl-js-button mdlext-js-menu-button">
    <span>Select a value</span>
    <i class="material-icons">more_vert</i>
  </button>
  <ul class="mdlext-menu">
    <li class="mdlext-menu__item">Small</li>
    <li class="mdlext-menu__item">Medium</li>
    <li class="mdlext-menu__item">Large</li>
  </ul>
</div>
```

With this markup the component will generate a random `id` attribute for the menu and associate it with the `aria-controls` 
of the button.


**A menu button with select listener.**

```html
<div id="selection"></div>
<button class="mdl-button mdl-js-button mdl-button--icon mdl-button--primary mdlext-js-menu-button"
  onselect="document.querySelector('#selection').innerHTML = 'Selected value: " + event.detail.source.innerHTML;">
  <i class="mdlext-aria-expanded-more-less"></i>
</button>
<ul class="mdlext-menu" hidden >
  <li class="mdlext-menu__item">10</li>
  <li class="mdlext-menu__item">25</li>
  <li class="mdlext-menu__item">50</li>
</ul>
```


**A menu button decorated with icons**

```html
<style>
.material-icons.md-18 {
   font-size: 18px;
}
</style>

<button class="mdl-button mdl-button--raised mdl-js-ripple-effect mdl-js-button mdlext-js-menu-button"
  aria-controls="demo-menu">
  <i class="material-icons">gesture</i>
  <span class="mdlext-menu-button__caption">Select</span>
  <i class="material-icons mdlext-aria-expanded-more-less"></i>
</button>

<ul id="demo-menu" class="mdlext-menu" hidden>
  <li class="mdlext-menu__item">
    <i class="material-icons md-18">info</i>
    <span class="mdlext-menu__item__caption">Menu item #1</span>
  </li>
  <li class="mdlext-menu__item">
    <i class="material-icons md-18">help_outline</i>
    <span class="mdlext-menu__item__caption">Menu item #2. A long text to check ellipsis overflow 0123456789</span>
    <i class="material-icons md-18">radio</i>
  </li>
  <li class="mdlext-menu__item-separator"></li>
  <li class="mdlext-menu__item" disabled>
    <span class="mdlext-menu__item__caption">Menu item #3, disabled</span>
    <i class="material-icons md-18">accessibility</i>
  </li>
  <li class="mdlext-menu__item-separator"></li>
  <li class="mdlext-menu__item">
    <span class="mdlext-menu__item__caption">Menu item #IV</span>
    <i class="material-icons md-18">build</i>
  </li>
  <li class="mdlext-menu__item">
    <span class="mdlext-menu__item__caption">Menu item #V</span>
    <i class="material-icons md-18">build</i>
  </li>
  <li class="mdlext-menu__item-separator"></li>
  <li class="mdlext-menu__item">
    <span class="mdlext-menu__item__caption">Menu item #VI</span>
    <i class="material-icons md-18">build</i>
  </li>
  <li class="mdlext-menu__item">
    <span class="mdlext-menu__item__caption">Menu item #VII</span>
    <i class="material-icons md-18">build</i>
  </li>
  <li class="mdlext-menu__item">
    Menu item #n
  </li>
</ul>
```

### More examples
* The [snippets/menu-button.html](./snippets/menu-button.html) and the [tests](../../test/menu-button/menu-button.spec.js) provides more detailed examples.
* Try out the [live demo](http://leifoolsen.github.io/mdl-ext/demo/menu-button.html)


## Characteristics

### Keyboard interaction, Menu Button 
* With focus on the button:
    * <kbd>Space</kbd> or <kbd>Enter</kbd>: opens the menu, sets `aria-expanded="true"`, and place focus on the previously selected menu item - or on the first menu item if no selected menu item.
    * <kbd>Down Arrow</kbd>: opens the menu, sets `aria-expanded="true"`, and moves focus to the first menu item.
    * <kbd>Up Arrow</kbd>: opens the menu, sets `aria-expanded="true"`, and moves focus to the last menu item.

### Mouse interaction, Menu Button 
* With focus on the button:
    * <kbd>Click</kbd>: opens the menu, sets `aria-expanded="true"`, and place focus on the previously selected menu item - or on the first menu item if no selected menu item.
    
### Keyboard interaction, Menu
* With focus on the menu:
    * <kbd>Space</kbd> or <kbd>Enter</kbd>: sets `aria-selected="true"` on active menu item, sets `aria-expanded="true"` on menu button, closes menu and moves focus back to menu button. The button emits a custom `select` event with a referfence to the selected menu element.
    * <kbd>Home</kbd>: move focus to first menu item.
    * <kbd>End</kbd>: move focus to last menu item.
    * <kbd>Up Arrow</kbd> or <kbd>Left Arrow</kbd>: move focus to previous menu item.
    * <kbd>Down Arrow</kbd> or <kbd>Right Arrow</kbd>: Move focus to next menu item.
    * <kbd>Esc</kbd>: Closes the menu, sets `aria-expanded="true"` on menu button, and move focus back to menu button.

>The keyboard behaviors after the menu is open are described in more detail in WAI-ARIA Authoring Practices, [2.19 Menu or Menu bar](https://www.w3.org/TR/wai-aria-practices/#menu).

### Mouse interaction, Menu
* With focus on the menu:
    * <kbd>Click</kbd>: sets `aria-selected="true"` on active menu item, sets `aria-expanded="true"` on menu button, closes menu and moves focus back to menu button. The button emits a custom `select` event with a referfence to the selected menu element. 

## WAI-ARIA Roles, States, and Properties
The menu button has the following roles, states and properties set by the menu button component.

### Menu Button
* `role="button"`: the element that opens the menu has role [button](http://www.w3.org/TR/wai-aria-1.1/#button).
* `aria-haspopup`: the element with role `button` has [aria-haspopup](http://www.w3.org/TR/wai-aria-1.1/#aria-haspopup) set to `true`.
* `aria-controls`: identfies the content on the page (e.g. using IDREFs) that this menu button controls.
* `aria-expanded`: the element with role `button` has [aria-expanded](https://www.w3.org/TR/wai-aria-1.1/#aria-expanded) set to `true` if the corresponding menu is open, oterwise false.
* `aria-expanded`: when a menu item is disabled, `aria-disabled` is set to `true`.
* `disabled"`: indicates that a button is disabled, otherwise not present.

### Menu, WAI-ARIA Roles
* `role="menu"`: identifies the element as a menu widget.
* `hidden`: the menu has attrubute hidden if the controlling buttoun has `aria-expanded="false"`, otherwise the attribute is not present.
* `role="menuitem"`: identifies an element as a menu item widget.
* `role="menuitemcheckbox"`: (not yet implemented).
* `role="menuitemradion"`: (not yet implemented).
* `aria-selected`: the selected menu item has `aria-selected="true"`, otherwise not present.
* `role="separator"`: a divider that separates and distinguishes sections of content or groups of menuitems..
* `disabled"`: indicates that a menu item is disabled, otherwise not present.

 
>The roles, states, and properties needed for the menu are described in more detail in WAI-ARIA Authoring Practices, [2.19 Menu or Menu bar](https://www.w3.org/TR/wai-aria-practices/#menu).


## Strategy used to position a menu when opened
When a menu is opened, the following strategy is used to position the menu next to the button.

1. menu.height > viewport.height<br/>
      let menu.height = viewport.heigt<br/>
      let menu.overflow-y = auto
2. menu.width > viewport.width<br/>
      let menu.width = viewport.width
3. position menu below button, align left edge of menu with button left<br/>
      done if menu inside viewport
4. position menu below button, align right edge of menu with button right<br/>
      done if menu inside viewport
5. positions menu above button, aligns left edge of menu with button left<br/>
      done if menu inside viewport
6. position menu at button right hand side, aligns menu top with button top<br/>
      done if menu inside viewport
7. position menu at button left hand side, aligns menu top with button top<br/>
      done if menu inside viewport
8. position menu inside viewport
    1. position menu at viewport bottom
    2. position menu at button right hand side<br/>
       done if menu inside viewport
    3. position menu at button left hand side<br/>
       done if menu inside viewport
    4. position menu at viewport right
9. done


## Events emitted from the component
The menu button emits a custom `select` event when a menu item is selected. The event has a detail object with the following structure:

```javascript
detail: { 
  source: item // The selected menu item 
}
```

To set up an event listener to receive the select custom event.
```javascript
document.querySelector('#my-menubutton').addEventListener('select', function(e) {
  console.log('menu item selected:', e.detail.source);
});
```
Refer to [snippets/menu-button.html](./snippets/menu-button.html) or the [tests](../../test/menu-button/menu-button.spec.js) for detailed usage.


## Configuration options

The MDLEXT CSS classes apply various predefined visual and behavioral enhancements to the menu button. 
The table below lists the available classes and their effects.

| MDLEXT class                     | Effect | Remarks |
|----------------------------------|--------|---------|
|`mdl-button`                      | Defines button as an MDL component | Required on button element |
|`mdl-js-button`                   | Assigns basic MDL behavior to button | Optional on button element |
|`mdl-js-ripple-effect`            | Applies ripple click effect to button and menu items | Optional on button element |
|`mdl-button--icon`                | Applies icon (small plain circular) display effect to button | Optional on button element |
|`mdl-button--xxxxxxxxxx`          | Apply any of the mdl-button classes | See: Material Design Lite, [BUTTONS](https://getmdl.io/components/index.html#buttons-section) |
|`mdlext-js-menu-button`           | Assigns basic MDLEXT behavior to menu button. Identifies the element as a menu button component | Required on the element that should act as a menu button |
|`mdlext-menu-button__caption`     | Holds the button text | Optional on span element inside button element - but required if you want to decorate a button with icons. More than one caption can be used to control various aspects of the button text, e.g. font size. |
|`material-icons`                  | Defines span as a material icon | Required on an inline element. Decorates button or menu item with an icon |
|`mdlext-menu`                     | Defines an unordered list container as an MDLEXT component | Required on ul element |
|`mdlext-menu__item`               | Defines menu options | Required on list item elements |
|`mdlext-menu__item__caption`      | Holds the menu text | Optional on span element inside list item element - but required if you want to decorate a menu item with icons. More than one caption can be used to control various aspects of the menu text, e.g. font size. |
|`mdlext-menu__item-separator`     | Items in a menu may be divided into groups by placing an element with a role of `separator` between groups. | Optional; goes on unordered list element |
|`mdlext-aria-expanded-plus-minus` | State icon. Displays '+' or '-' | Optional; goes on button element |
|`mdlext-aria-expanded-more-less`  | State icon. Displays 'more' or 'less' Material Design icons | Optional; goes on button element |

> **Note:** 
> Disabled versions of the button are provided, and are invoked with the standard HTML boolean attribute `disabled` 
`<li class="mdlext-menu__item" disabled>A menu item</li>`. This attribute may be added or removed programmatically via scripting.

> Disabled versions of the menu items are provided, and are invoked with the standard HTML boolean attribute `disabled` 
`<li class="mdlext-menu__item" disabled>A menu item</li>`. This attribute may be added or removed programmatically via scripting.

> If you decorate the button with icons, wrap the button text inside a span to separate icons and text 
```html
<button class="mdl-button mdl-button--raised mdl-js-ripple-effect mdl-js-button mdlext-js-menu-button">
  <i class="material-icons">gesture</i>
  <span class="mdlext-menu-button__caption">Select</span>
  <i class="material-icons mdlext-menu-button__aria-expanded-more-less"></i>
</button>
```

> If you decorate a menu item with icons, wrap the menu item text inside a span to separate icons and text 
```html
<ul id="demo-menu" class="mdlext-menu" hidden>
  <li class="mdlext-menu__item">
    <i class="material-icons md-18">help_outline</i>
    <span class="mdlext-menu__item__caption">Menu item</span>
    <i class="material-icons">info</i>
  </li>
</ul>
```