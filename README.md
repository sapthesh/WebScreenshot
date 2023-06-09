## WEB SCREENSHOT

<h1 align="center"><a href="https://github.com/sapthesh/WebScreenshot" target="_blank">WebScreenshot</a></h1>
<p align="center">Website Screenshot API </p>

<p align="center">
    <a href="https://github.com/sapthesh/WebScreenshot"><img src="https://img.shields.io/npm/v/webstack-screenshot?logo=npm" alt="Version"></a>
    <a href="https://github.com/sapthesh/WebScreenshot/blob/main/LICENSE"><img src="https://img.shields.io/npm/l/webstack-screenshot" alt="MIT License"></a>
</p>

## Introduction

Just some simple screenshot operations, if you have any needs, or want to participate in the development, we welcome you to PR

## Quick Start

### Vercel Free Deployment

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/sapthesh/WebScreenshot/tree/Vercel)

### Installation

```bash
npm install webstack-screenshot --save
```

```js
const webstackScreenshot = require('webstack-screenshot')

webstackScreenshot({ url: 'https://example.com' }).then((buffer) => {
  console.log('buffer', buffer)
})

webstackScreenshot({ url: 'https://example.com', encoding: 'base64' }).then((base64) => {
  console.log('base64', base64)
})
```

### ServerLess

```js
module.exports = require('webstack-screenshot/dist/src/serverless')
```

### Clone Warehouse

Clone remote repository start **Website screenshot API**

```bash
# Clone the repository and go to the WebStack-Screenshot directory
git clone https://github.com/Lete114/WebStack-Screenshot.git WebStack-Screenshot
cd WebStack-Screenshot

# Installing Dependencies
npm install

# Start service
npm run start
```

## Properties

Request Method: GET | POST

| Properties | Default | Type          | Description                                                                                                       |
| ---------- | ------- | ------------- | ----------------------------------------------------------------------------------------------------------------- |
| url        |         | String        | The URL of the requested website, if the domain name is entered it will be automatically spelled out as `http://` |
| type       | png     | String        | The image type, `png`, `jpeg`, `webp`                                                                             |
| cache      | 86400   | Int & Boolean | cache, default cache is 1 day, pass `false` to disable cache, pass number like:`123` to cache 123 seconds         |
| quality    |         | Int           | Image quality between **0-100**, ignored if the image type is `png`                                               |
| viewport   |         | Int           | Screenshot 100 wide by 200 high, format `100x200`                                                                 |
| fullPage   | false   | Boolean       | Capture the full page                                                                                             |
| isMobile   | false   | Boolean       | If or not it is mobile                                                                                            |
| await      | 1000    | Int           | Wait for the page to finish rendering                                                                             |
| timeout    | 30000   | Int           | Screenshot timeout, `0` means no limit (in milliseconds)                                                          |
| encoding   | binary  | String        | Image encoding, `binary`, `base64`                                                                                |
| clip       |         | String        | Clip the specified area, receive 4 units divided by English **comma**, `x,y,width,height`                         |
| font       |         | String        | If the specified screenshot site is garbled, you can specify the font `url` address with this parameter           |
| waitUntil  | load    | String        | At what time the screenshot is triggered, [see another table below for details](#waituntil)                       |

### waitUntil

| Properties       | Description                                    |
| ---------------- | ---------------------------------------------- |
| load             | Done when the load event is fired              |
| domcontentloaded | Done when the DOMContentLoaded event is fired. |
| networkidle0     | when no site request is made for 500ms         |
| networkidle2     | when there are only 2 requests in 500ms        |
