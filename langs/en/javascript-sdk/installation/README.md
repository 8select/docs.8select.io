# Installation

## How the 8select-CSE JavaScript SDK works

The widget-loader script `loader.js` is a JavaScript file of approximately 8 KB. This script generates a FIF \(Friendly IFrame\) in which the 8select-CSE is loaded.

This technique prevents any possible blocking of downloads and other resources of the page. In addition the browser `onload` event isn't blocked either. This way the 8select-CSE integration doesn't affect the loading speed of your site in any way.

After loading the 8select-CSE JavaScript SDK, all marked div elements are filled with its widgets accordingly.

