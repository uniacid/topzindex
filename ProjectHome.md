# TopZIndex plugin for jQuery #
## Version 1.2 ##

This jQuery plugin calculates the highest CSS z-index value in the current document or specified set of elements, and also provides the ability to push one or more elements to the top of the z-index order.

The plugin is particularly useful for dynamic HTML popup windows/panels (or other dynamic elements) the order of which need to be re-shuffled on the page dynamically.

### Version 1.2 Release Notes ###
  * Changed default selector back to `"*"` from `"body *"`. Internally, the element selection was re-worked to use the browser's native `document.getElementsByTagName("*")` if all elements are to be selected, as this will perform better than creating a jQuery instance, regardless of the default selector used.
  * Worked around a bug in WebKit browsers that returns scientific notation (instead of an integer value) for large z-index values. For example, Safari for Windows returns `1e+006` instead of `1000000` (1 million).
  * Slight performance increase through setting the z-index style on elements using the native DOM style property of each element, rather than generating a jQuery matched set for each element and using `.css("z-index", ___)`.


### Version 1.1 Release Notes ###
  * Default selector changed from `"*"` to `"body *"`, which increases performance overall.
  * Simplified z-index calculation internally, also increasing performance.