# `@ds-pack/property-controls`

A package for interacting with Framer-X like "Property Controls" for any React
component.

## Example

```js
import { types } from '@ds-pack/property-controls'

function Avatar({
  initials,
  backgroundImage,
  size
}) {
  return (
    <div
      style={{
        backgroundImage: `url(${backgroundImage})`,
        width: size,
        height: size,
				borderRadius: '50%',
        display: 'flex',
        justifyContent: 'center',
        alignItems: 'center'
      }}
    >
      <span>{initials}</span>
    </div>
  );
}

Avatar.propertyControls = {
  initials: {
    type: types.string,
    label: 'The users initials to display over the background image'
  },
  backgroundImage: {
    type: types.string,
    label: `The background image on the avatar.

Ensure that this image has a high enough contrast for the color of the initials provided.`
    default: null
  },
  size: {
    type: types.enum,
    values: [ 20, 40, 80 ],
    label: `The dimensions of the avatar component`,
    default: 40
  }
}
```

## Package API

The Property Controls package exports the following:

- `types` (named export) - An object of supported property controls

Note: To see how this can be integrated, take a look at the
[suggested implementation](./suggested-implementation.md)
