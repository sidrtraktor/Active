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

Auto-commit on 2025-02-19 19:56:08 | rand=45496

Auto-commit on 2025-02-19 20:09:02 | rand=82161

Auto-commit on 2025-02-19 20:21:58 | rand=65538

Auto-commit on 2025-02-19 20:34:55 | rand=55726

Auto-commit on 2025-02-19 20:47:48 | rand=54832

Auto-commit on 2025-02-19 21:00:49 | rand=51133

Auto-commit on 2025-02-19 21:13:43 | rand=77046

Auto-commit on 2025-02-19 21:26:42 | rand=82377

Auto-commit on 2025-02-20 09:31:55 | rand=42730

Auto-commit on 2025-02-20 09:44:57 | rand=76588

Auto-commit on 2025-02-20 14:08:37 | rand=27442

Auto-commit on 2025-02-20 14:20:44 | rand=42381

Auto-commit on 2025-02-20 14:32:51 | rand=75954

Auto-commit on 2025-02-20 14:44:53 | rand=88205

Auto-commit on 2025-02-20 14:56:50 | rand=39698

Auto-commit on 2025-02-20 15:08:57 | rand=14947

Auto-commit on 2025-02-20 15:20:57 | rand=45485

Auto-commit on 2025-02-20 15:33:03 | rand=12810

Auto-commit on 2025-02-20 15:45:10 | rand=80532

Auto-commit on 2025-02-20 15:57:15 | rand=35025

Auto-commit on 2025-02-20 16:09:22 | rand=39376

Auto-commit on 2025-02-20 16:21:28 | rand=32165

Auto-commit on 2025-02-20 16:33:35 | rand=74144

Auto-commit on 2025-02-20 16:45:36 | rand=26457

Auto-commit on 2025-02-20 16:57:47 | rand=50584

Auto-commit on 2025-02-21 15:11:27 | rand=76246

Auto-commit on 2025-02-21 15:23:34 | rand=52900

Auto-commit on 2025-02-21 15:35:32 | rand=82128

Auto-commit on 2025-02-21 15:47:32 | rand=25046

Auto-commit on 2025-02-21 15:59:27 | rand=43242

Auto-commit on 2025-02-21 16:11:24 | rand=32903

Auto-commit on 2025-02-21 16:23:24 | rand=23235

Auto-commit on 2025-02-21 16:35:28 | rand=29690

Auto-commit on 2025-02-21 16:47:32 | rand=7961

Auto-commit on 2025-02-21 16:59:28 | rand=67578

Auto-commit on 2025-02-21 17:11:28 | rand=36873

Auto-commit on 2025-02-21 17:23:26 | rand=77697

Auto-commit on 2025-02-21 17:35:25 | rand=26002

Auto-commit on 2025-02-21 17:47:24 | rand=24387

Auto-commit on 2025-02-21 17:59:24 | rand=80245

Auto-commit on 2025-02-22 00:17:39 | rand=7609

Auto-commit on 2025-02-22 00:29:46 | rand=10204

Auto-commit on 2025-02-22 00:41:51 | rand=87570

Auto-commit on 2025-02-22 00:53:52 | rand=36445

Auto-commit on 2025-02-22 01:05:55 | rand=83794

Auto-commit on 2025-02-22 01:18:02 | rand=6517

Auto-commit on 2025-02-22 01:30:02 | rand=20768

Auto-commit on 2025-02-22 01:42:05 | rand=45710

Auto-commit on 2025-02-22 01:54:07 | rand=44888

Auto-commit on 2025-02-22 02:06:15 | rand=34864

Auto-commit on 2025-02-22 02:18:21 | rand=90602

Auto-commit on 2025-02-22 02:30:29 | rand=82273

Auto-commit on 2025-02-22 02:42:34 | rand=20237

Auto-commit on 2025-02-22 02:54:33 | rand=16510

Auto-commit on 2025-02-22 03:06:51 | rand=40352

Auto-commit on 2025-02-22 14:46:46 | rand=24646

Auto-commit on 2025-02-22 14:58:56 | rand=84313

Auto-commit on 2025-02-22 15:11:01 | rand=71947

Auto-commit on 2025-02-22 15:23:07 | rand=68041

Auto-commit on 2025-02-22 15:35:07 | rand=72464

Auto-commit on 2025-02-22 15:47:13 | rand=71079

Auto-commit on 2025-02-22 15:59:19 | rand=79041

Auto-commit on 2025-02-22 16:11:18 | rand=9816

Auto-commit on 2025-02-22 16:23:19 | rand=44181

Auto-commit on 2025-02-22 16:35:19 | rand=52969

Auto-commit on 2025-02-22 16:47:23 | rand=19681
