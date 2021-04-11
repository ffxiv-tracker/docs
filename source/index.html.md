---
title: API Reference

language_tabs:
  - javascript

includes:
  - tasks

search: true

code_clipboard: true
---

# Introduction

Welcome to the FFXIV Tracker! You can this API to access FFXIV Tracker's API endpoints, which stores information about tasks in FFXIV.

# Authentication

> To authorize, use this code:

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>
