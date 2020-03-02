# Platform API Project Seed

This project seed includes the following [Platform API](https://openfin.co/platform-api) capabilites:

* Examples of the configuration required to use the Platform API and apply customizations
* Usage of the Platform API to group, tab, and rearrange application windows
* API examples of View management and creation
* API examples of Snapshot saving and applying
* Examples of visual customization via CSS
* Examples of visual customization by providing a custom Platform Window
* Examples of behavioral customization by overriding the Platform APIs


## How to use this repository:

* Clone this repository
* Install the dependencies: `npm install`
* Start the live-server and launch the application: `npm start`

## Understanding the code

### Platform configuration
* [Platform configuration](https://developers.openfin.co/docs/platform-api#section-1-launching-a-platform) has been included in the provided [app.json](app.json) file.
* The [defaultWindowOptions](https://developers.openfin.co/docs/platform-api#section-standard-window-customization) key in the provided `app.json` will instruct the platform to replace our Standard Window with the provided [platform-window.html](platform-window.html) file.
* The [commands](https://developers.openfin.co/docs/platform-api#section-5-3-using-keyboard-commands) key in the provided `app.json` will allow keyboard access to the next tab command.
* The [providerUrl]() key in the provided `app.json` will allow you to make custom changes to the Platform APIs, by pointing to a hosted [provider.html](provider.html) file. (STARTING IN v15.80.50.x)

### Provider
The [provider.html](provider.html) file, when set with the `providerUrl` key, will change the Platform API in the following ways:
* Override `getSnapshot` to include [hostSpecs](https://cdn.openfin.co/docs/javascript/15.80.49.21/tutorial-System.getHostSpecs.html)
* Override `applySnapshot` to reject if 3 or more Windows have been created.

### CSS Customization
* A [stylesheet](https://developers.openfin.co/docs/platform-api#section-standard-window-customization) is linked in the [platform-window.html](platform-window.html) file, and allows for [visual customization](styles/frame-styles.css). For a complete view of all properties, please refer to the [example stylesheet](https://github.com/openfin/layouts-v2-style-examples)

### Platform Window
The [js/platform-window.js](js/platform-window.js) file is composed of the [layout-container](https://developers.openfin.co/docs/platform-api#section-5-2-complete-window-customization) element and two custom elements: `left-menu` and `title-bar`.

##### left-menu
Provides examples of the following functionality:
* Adding a View to an existing Window
* Adding a View in a new Window
* Saving the Window's current Layout
* Restoring the Window's current Layout
* Creating a regular OpenFin Window
* Saving/Restoring Platform Snapshots
* Applying a preset arrangement on the current window (Grid, Tabs, Rows)

##### title-bar
Provides examples of the following functionality:
* Draggable area
* Close/Maximize/Minimize buttons
