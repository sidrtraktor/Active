![Async Logo](https://raw.githubusercontent.com/caolan/async/master/logo/async-logo_readme.jpg)

[![Build Status via Travis CI](https://travis-ci.org/caolan/async.svg?branch=master)](https://travis-ci.org/caolan/async)
[![Build Status via Azure Pipelines](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)
[![NPM version](https://img.shields.io/npm/v/async.svg)](https://www.npmjs.com/package/async)
[![Coverage Status](https://coveralls.io/repos/caolan/async/badge.svg?branch=master)](https://coveralls.io/r/caolan/async?branch=master)
[![Join the chat at https://gitter.im/caolan/async](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/async?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/async/badge?style=rounded)](https://www.jsdelivr.com/package/npm/async)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [asynchronous JavaScript](http://caolan.github.io/async/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i async`, it can also be used directly in the browser.  A ESM/MJS version is included in the main `async` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`async-es`](https://www.npmjs.com/package/async-es).

For Documentation, visit <https://caolan.github.io/async/>

*For Async v1.5.x documentation, go [HERE](https://github.com/caolan/async/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var async = require("async");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

async.forEachOf(obj, (value, key, callback) => {
    fs.readFile(__dirname + value, "utf8", (err, data) => {
        if (err) return callback(err);
        try {
            configs[key] = JSON.parse(data);
        } catch (e) {
            return callback(e);
        }
        callback();
    });
}, err => {
    if (err) console.error(err.message);
    // configs is now a map of JSON data
    doSomethingWith(configs);
});
```

```javascript
var async = require("async");

// ...or ES2017 async functions
async.mapLimit(urls, 5, async function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```

Auto-commit on 2025-02-18 18:23:20 | rand=42794

Auto-commit on 2025-02-18 18:36:10 | rand=52333

Auto-commit on 2025-02-18 18:49:04 | rand=43352

Auto-commit on 2025-02-18 19:01:56 | rand=60299

Auto-commit on 2025-02-18 19:14:46 | rand=80404

Auto-commit on 2025-02-18 19:27:34 | rand=12649

Auto-commit on 2025-02-18 19:40:31 | rand=41808

Auto-commit on 2025-02-18 19:53:23 | rand=16107

Auto-commit on 2025-02-18 20:06:16 | rand=36466

Auto-commit on 2025-02-18 20:19:09 | rand=46387

Auto-commit on 2025-02-18 20:32:02 | rand=44305

Auto-commit on 2025-02-18 20:44:58 | rand=96409

Auto-commit on 2025-02-18 20:57:51 | rand=50284

Auto-commit on 2025-02-18 21:10:44 | rand=69337

Auto-commit on 2025-02-18 21:23:37 | rand=72379

Auto-commit on 2025-02-19 08:13:23 | rand=84061

Auto-commit on 2025-02-19 08:26:17 | rand=77754

Auto-commit on 2025-02-19 08:39:18 | rand=20757

Auto-commit on 2025-02-19 08:52:14 | rand=93306

Auto-commit on 2025-02-19 09:05:04 | rand=14508

Auto-commit on 2025-02-19 09:18:03 | rand=90971

Auto-commit on 2025-02-19 09:31:01 | rand=74434

Auto-commit on 2025-02-19 09:43:57 | rand=14378

Auto-commit on 2025-02-19 09:56:51 | rand=24326

Auto-commit on 2025-02-19 10:09:50 | rand=55431

Auto-commit on 2025-02-19 10:22:40 | rand=90439

Auto-commit on 2025-02-19 10:35:32 | rand=26503

Auto-commit on 2025-02-19 10:48:29 | rand=14771

Auto-commit on 2025-02-19 11:01:22 | rand=96021

Auto-commit on 2025-02-19 11:14:18 | rand=81636

Auto-commit on 2025-02-19 18:25:38 | rand=92816

Auto-commit on 2025-02-19 18:38:39 | rand=77479

Auto-commit on 2025-02-19 18:51:37 | rand=80032

Auto-commit on 2025-02-19 19:04:25 | rand=97921

Auto-commit on 2025-02-19 19:17:25 | rand=84827

Auto-commit on 2025-02-19 19:30:17 | rand=19546

Auto-commit on 2025-02-19 19:43:09 | rand=54022
