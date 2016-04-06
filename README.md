# x-editable-defaults
extending the x-editable default options functionality

* Adding defaults to specific input type
* Flexible adding of defaults through filter

## Getting started

1.) Include the script into your page.

**NOTE: be sure to include it AFTER the x-editable library.**


```html
<script src="x-editable-defaults.jquery.js"></script>
```

## How to use

You can now start adding default options using the `$.fn.editable.defaults`.

### Global
```javascript
$.fn.editable.defaults.showbuttons = false;
```
### Input type specific
```javascript
$.fn.editable.defaults.select2.showbuttons = false;
```

### Input type specific using the addFilter() method

```javascript
$.fn.editable.defaults.select2.addFilter(function(options){

  if (options.select2.multiple === true) {
    options.showbuttons = false;
  }

  return options;
});
```
