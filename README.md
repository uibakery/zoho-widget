# Installation
1. `npm install -g zoho-extension-toolkit`
1. Create UI Bakery app that will be inserted in ZOHO CRM as a widget
2. Fork this repository
3. In `/app/widget.html`
    1. Insert UI Bakery app Embed URL - Open app settings > Copy Embed URL
    2. Define custom events handling by example
4. Pack widget - `zet pack`
5. Get archive from `/dist/` folder and upload as a ZOHO hosted widget
6. Get access to PageLoad data in UI Bakery
```
{{JSON.parse(activeRoute.queryParams.page_load_data)}}
```
7. Call ZOHO.CRM APIs from UI Bakery
```
window.workbenchParent.parent.postMessage({
	type: 'CLOSE_ZOHO_POPUP',
}, '*');
```