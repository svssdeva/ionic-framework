```tsx
import { Component, h } from '@stencil/core';

@Component({
  tag: 'select-option-example',
  styleUrl: 'select-option-example.css'
})
export class SelectOptionExample {
  render() {
    return [
      <ion-item>
        <ion-label>Select</ion-label>
        <ion-select>
          <ion-select-option value="brown">Brown</ion-select-option>
          <ion-select-option value="blonde">Blonde</ion-select-option>
          <ion-select-option value="black">Black</ion-select-option>
          <ion-select-option value="red">Red</ion-select-option>
        </ion-select>
      </ion-item>
    ];
  }
}
```

### Customizing Options

```tsx
import { Component, h } from '@stencil/core';

@Component({
  tag: 'select-option-example',
  styleUrl: 'select-option-example.css'
})
export class SelectOptionExample {
  options = {
    cssClass: 'my-custom-interface'
  };

  render() {
    return [
      <ion-item>
        <ion-label>Select: Alert Interface</ion-label>
        <ion-select interfaceOptions={options}>
          <ion-select-option value="brown">Brown</ion-select-option>
          <ion-select-option value="blonde">Blonde</ion-select-option>
          <ion-select-option value="black">Black</ion-select-option>
          <ion-select-option value="red">Red</ion-select-option>
        </ion-select>
      </ion-item>,

      <ion-item>
        <ion-label>Select: Alert Interface (Multiple Selection)</ion-label>
        <ion-select interfaceOptions={options} multiple={true}>
          <ion-select-option value="brown">Brown</ion-select-option>
          <ion-select-option value="blonde">Blonde</ion-select-option>
          <ion-select-option value="black">Black</ion-select-option>
          <ion-select-option value="red">Red</ion-select-option>
        </ion-select>
      </ion-item>,

      <ion-item>
        <ion-label>Select: Popover Interface</ion-label>
        <ion-select interface="popover" interfaceOptions={options}>
          <ion-select-option value="brown">Brown</ion-select-option>
          <ion-select-option value="blonde">Blonde</ion-select-option>
          <ion-select-option value="black">Black</ion-select-option>
          <ion-select-option value="red">Red</ion-select-option>
        </ion-select>
      </ion-item>,

      <ion-item>
        <ion-label>Select: Action Sheet Interface</ion-label>
        <ion-select interface="action-sheet" interfaceOptions={options}>
          <ion-select-option value="brown">Brown</ion-select-option>
          <ion-select-option value="blonde">Blonde</ion-select-option>
          <ion-select-option value="black">Black</ion-select-option>
          <ion-select-option value="red">Red</ion-select-option>
        </ion-select>
      </ion-item>
    ];
  }
}
```

```css
/* Popover Interface: set color for the popover using Item's CSS variables */
.my-custom-interface .select-interface-option {
  --color: #971e49;
  --color-hover: #79193b;
}

/* Action Sheet Interface: set color for the action sheet using its button CSS variables */
.my-custom-interface .select-interface-option {
  --button-color: #971e49;
  --button-color-hover: #79193b;
}

/* Alert Interface: set color for alert options (single selection) */
.my-custom-interface .select-interface-option .alert-radio-label {
  color: #971e49;
}

/* Alert Interface: set color for alert options (multiple selection) */
.my-custom-interface .select-interface-option .alert-checkbox-label {
  color: #971e49;
}

/* Alert Interface: set color for checked alert options (single selection) */
.my-custom-interface .select-interface-option[aria-checked=true] .alert-radio-label {
  color: #79193b;
}

/* Alert Interface: set color for checked alert options (multiple selection) */
.my-custom-interface .select-interface-option[aria-checked=true] .alert-checkbox-label {
  color: #79193b;
}
```

> Note: In the CSS examples, some of the selectors could be combined together, but are separated out in order to better explain what each selector is for.

### Customizing Individual Options

To customize an individual option, set a class on the `ion-select-option`:

```tsx
import { Component, h } from '@stencil/core';

@Component({
  tag: 'select-option-example',
  styleUrl: 'select-option-example.css'
})
export class SelectOptionExample {
  options = {
    cssClass: 'my-custom-interface'
  };

  render() {
    return [
      <ion-item>
        <ion-label>Select</ion-label>
        <ion-select interface="popover" interfaceOptions={options}>
          <ion-select-option value="brown" class="brown-option">Brown</ion-select-option>
          <ion-select-option value="blonde">Blonde</ion-select-option>
          <ion-select-option value="black">Black</ion-select-option>
          <ion-select-option value="red">Red</ion-select-option>
        </ion-select>
      </ion-item>
    ];
  }
}
```

```css
/* Popover Interface: set color for the popover using Item's CSS variables */
.my-custom-interface .brown-option {
  --color: #5e3e2c;
  --color-hover: #362419;
}
```