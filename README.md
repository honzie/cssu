# cssu
A simple CSS Unit test library.

## Use

In order to use, include cssu.js into your webpage. Then, initialize it.

```
      // Initialize a cu instance
      var cu = new Cu({logger: true});
```

The `logger` option is a boolean that allows for verbose logging.

Then, define your tests. Tests are called by passing both a node and property object to the assert function on the CSS U instance.

A node should be a DOM node. The property object should map JS-safe property names (e.g. `color` for `color` and `fontSize` for `font-size`) to the expected values. Expected values will be applied and normalized, so `gray`, `#808080`, and `rgb(128,128,128)` are all the same colors.

```
      // Make some assertions about the header
      cu.assert(
        document.querySelector('h1'),
        {color: '#444'});
```

## TODO

These features are slated for future development.

1. Allow passing in CSS declarations as strings and parse them.
1. Ignore browser-specific properties, like those beginning in 'webkit'.
1. Add a fuzz layer to `rgba` values.
1. Support jQuery nodes being passed in.
