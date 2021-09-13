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

### Endpoints

Stage | Hostname
--------- | -----------
beta | https://hdnss8awo4.execute-api.us-west-2.amazonaws.com
prod | 

# Authentication

> First redirect the user to login:
 
```javascript
window.location = 'https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/login';
```

> The user will then be redirected back to the app with a `code` query parameter that needs to be parsed.
 
```javascript
const params = new URLSearchParams(window.location.search);
const code = params.get('code');
```

> Exchange the code for a JWT through the API.

```javascript
const api = axios.create({
  baseURL: 'https://hdnss8awo4.execute-api.us-west-2.amazonaws.com'
});

const exchangeResponse = await api.post('/exchange', {
    code: code
});

const jwt = exchangeResponse.data.jwt;
```

> Set the JWT as an authorization header for all future requests.

```javascript

api.defaults.headers.common['Authorization'] = `Bearer ${jwt}`
```

The API uses JWTs to allow access to the API. A JWT can be obtained by using the login flow.

1. Redirect the user to `/login`. This will prompt them to login with Discord.
2. The user will be redirected to http://localhost:3000/?code=supersecretcode.
3. The frontend needs to handle this request by parsing out the `code` query parameter.
4. Make a POST request to `/exchange` with the `code` in the request body.
5. The response from the above request will contain a JWT for you to use throughout the user session and in all future API requests.

The API expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer JWT_GOES_HERE`

<aside class="notice">
You must replace <code>JWT_GOES_HERE</code> with the <code>jwt</code> from the <code>/exchange</code> response.
</aside>
