# resin-electron-vue

> An electron-vue project
a boilerplate for developing kiosks, digital signage or other human-machine interaction projects based on
[resin.io](https://resin.io)
[ElectronJS](https://electron.atom.io/)
[Vue.js](https://vuejs.org)

## Getting started

- Sign up on [resin.io](https://dashboard.resin.io/signup)
- go throught the [getting started guide](http://docs.resin.io/raspberrypi/nodejs/getting-started/) and create a new application
- clone this repository to your local workspace
- add the _resin remote_ to your local workspace using the useful shortcut in the dashboard UI ![remoteadd](https://raw.githubusercontent.com/resin-io-playground/boombeastic/master/docs/gitresinremote.png)
- `git push resin master`
- see the magic happening, your device is getting updated Over-The-Air!

## Configure via [environment variables](https://docs.resin.io/management/env-vars/)
Variable Name | Value | Description | Device-specific
------------ | ------------- | ------------- | -------------
**`RESIN_HOST_CONFIG_gpu_mem`** | a value from `64` to `160` | the amount of RAM dedicated to the GPU | Raspberry Pi (all revs)

Apply the above settings in the "Fleet Configuration" panel (if applying it for the all devices withing your application), or "Device Configuration" panel (if applying it for a single device).


### WHY THIS TEMPLATE

Achieving kinda-smooth desktop application display on a devices like the raspberrypi is hard. This project aims to provide a quickstart template.

### WHY FLUXBOX

We did a lot of researches and tests with several window managers. [Fluxbox](http://fluxbox.org/) ended up being the most balanced between minimum footprint and features

### URL LAUNCHER config via ENV VARS
*__!!! Please note that since `0.1.0` the `bool`-based env vars dropped `true` / `false` strings in favour of `0` / `1` ones. !!!__*

simply set these [environment varables](http://docs.resin.io/#/pages/management/env-vars.md) in your app via "Environment Variables" panel in the resin dashboard to configure the behaviour of your devices.
*__Please note that the `bool` type definition in the table is meant to accept to either `0` or `1` values.__*

* **`URL_LAUNCHER_URL`** *string* - the URL to be loaded. use `file:////usr/src/app/data/index.html` to load a local electronJS (or any website) app - *defaults to* `file:////usr/src/app/data/index.html`
* **`URL_LAUNCHER_KIOSK`** *bool* (converted from *string*) - whether or not enter KIOSK mode - *defaults to* `1`
* **`URL_LAUNCHER_TITLE`** *string* - the title of the window. Seen only with `URL_LAUNCHER_FRAME`=`true` - *defaults to* `RESIN.IO`
* **`URL_LAUNCHER_FRAME`** *bool* (converted from *string*) - set to "true" to display the window frame. Seen only with `URL_LAUNCHER_KIOSK`=`false` - *defaults to*  `0`
* **`URL_LAUNCHER_WIDTH`**  *int* (converted from *string*) -  - *defaults to* `1920`
* **`URL_LAUNCHER_HEIGHT`**  *int* (converted from *string*) -  - *defaults to* `1080`
* **`URL_LAUNCHER_TOUCH`** *bool* (converted from *string*) - enables touch events if your device supports them  - *defaults to* `0`
* **`URL_LAUNCHER_TOUCH_SIMULATE`** *bool* (converted from *string*) - simulates touch events - might be useful for touchscreen with partial driver support - be aware this could be a performance hog  - *defaults to* `0`
* **`URL_LAUNCHER_ZOOM`** *float* (converted from *string*) - The default zoom factor of the page, 3.0 represents 300%  - *defaults to* `1.0`

#### Build Setup

``` bash
# install dependencies
yarn install

# serve with hot reload at localhost:9080
yarn run dev

# build electron application for production
yarn run build


# lint all JS/Vue component files in `src/`
yarn run lint

```

---

This project was generated with [electron-vue](https://github.com/SimulatedGREG/electron-vue)@[3a1e893](https://github.com/SimulatedGREG/electron-vue/tree/3a1e893e10e8dcfb4c5e5580810ed70f74b3a83e) using [vue-cli](https://github.com/vuejs/vue-cli).
Integrated with resin based on [resin-electronjs](https://github.com/resin-io/resin-electronjs)
Documentation about the original structure can be found [here](https://simulatedgreg.gitbooks.io/electron-vue/content/index.html).


