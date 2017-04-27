# \<isw-responsive-behavior\>

Provides feedback about device and orientation, using material design breakpoints.

https://material.io/guidelines/layout/responsive-ui.html#responsive-ui-breakpoints

### Add behavior
Polymer 2.0:

```javascript
class MyApp extends Polymer.mixinBehaviors([ iswResponsiveBehavior ], Polymer.Element ) {
  ...
}
```

Polymer 1.0:

```javascript
Polymer({
  is: 'my-app',
  behaviors: [ iswResponsiveBehavior ]

  ...
});
```

### CSS
The `device` and `orientation` properties reflect to attribute, so attribute selectors can be used.

```css
:host([device="desktop"]) .someSelector { ... }
:host([device="mobile"][orientation="landscape"]) .someSelector { ... }
```

### Elements
Some of our elements, e.g. isw-toolbar, are using `device` and `orientation` to display.
Simply bind these properties to make them responsive.

```html
<isw-toolbar device="[[device]]" orientation=[[orientation]]> ... </isw-toolbar>
```

### Imperative
iswResponsiveBehavior gets the onResize function called, with Polymer 2.0 classes they can be used like lifecycle functions.

```javascript
onResize() {
  super.onResize();

  switch( this.device ) {
    case 'desktop':
      // Desktop.
      break;
    case 'tablet':
      // Tablet.
      break;
    default:
      // Mobile.
  }
}
```