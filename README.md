# browserstack-select

Filters BrowserStack Automate flat map of browser configurations (as from their REST API) and outputs a JSON array fit to be used with `browserstack.json` config for [browserstack-runner](https://github.com/browserstack/browserstack-runner).

## Usage

`npm install -g browserstack-select`

`browserstack-select <os> <os_version> <browser> <browser_version> <device>`

Put `any` where you want all possibilies.

**Expects a file `browserstack.options.json` containing source data in working directory.**

Source data can be retrieved from BrowserStack API with a command like:

`curl -u "USERNAME:PASSWORD" https://www.browserstack.com/automate/browsers.json > browserstack.options.json`

## Example

We want a config for Chrome 47.0 on all Windows versions.

```
$ node browserstack-select.js Windows any chrome 47.0 any
[ { os_version: 'XP',
    browser_version: '47.0',
    device: null,
    os: 'Windows',
    browser: 'chrome' },
  { os_version: '8',
    browser_version: '47.0',
    device: null,
    os: 'Windows',
    browser: 'chrome' },
  { os_version: '7',
    browser_version: '47.0',
    device: null,
    os: 'Windows',
    browser: 'chrome' },
  { os_version: '10',
    browser_version: '47.0',
    device: null,
    os: 'Windows',
    browser: 'chrome' },
  { os_version: '8.1',
    browser_version: '47.0',
    device: null,
    os: 'Windows',
    browser: 'chrome' } ]
  ```
  
  ## Wishlist
  
  * Get source data directly from BrowserStack REST API (take credentials as input)
  * Directly write output into browserstack.json `browsers` field
