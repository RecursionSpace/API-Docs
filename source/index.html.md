---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: cURL

toc_footers:
  - <a href='https://recursion.space/dash/'>Sign Up for a Developer Key</a>

includes:
  - errors
  - space
  - modules

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kittn API
---

# Introduction

> BASE URL

```shell
https://api.recursion.space
```

The Recursion.Space API is built on [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) principles. Our API has predictable resource-oriented URLs, accepts [form-encoded](<https://en.wikipedia.org/wiki/POST_(HTTP)#Use_for_submitting_web_forms>) request bodies, returns [JSON-encoded](https://www.json.org/json-en.html) responses, and uses standard HTTP response codes, authentication, and verbs.

API authentication is handled by a unique key generated for your account.

If you need API support or would like to see how others are implementing the platform you will find our staff and community through our Discord server.

<a target="_blank" rel="noopener noreferrer" href="https://discord.com/invite/KnFp4jd9AV" style="width: 100%">
<img src="https://discordapp.com/api/guilds/790311269420630079/widget.png?style=banner2" alt="Discord Banner 2" style="max-width: 100%; margin: auto; display: block;"/>
</a>

<aside class="notice">
BETA - API is currently considered beta and may change unexpectedly. <br>
Breaking changes will be documented in a changelong if they occur.
</aside>

# Authentication

> AUTHENTICATED REQUEST

```shell
# With shell, you can just pass the correct header with each request
curl "https://api.recursion.space/v1/" \
  -H "Authorization: Token xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

> A sample placeholder API key is included in all the examples here, replace with your key prior to making API requests.

Recursion.Space uses API keys to allow access to the API. You can obtain an API key under the developer tab on your dashboard.

Your API key grants privlaged access to your account and by extention spaces, so be sure to keep it secure! Do not share your API keys in publicly accessible areas such as GitHUB, client-side code, and so forth.

<aside class="warning">
All API requests must include the API key and be made over HTTPS, requests that do not meet these requirements will fail.
</aside>

# Client Libraries

Client, or language, libraries provide a streamlined method for you to consume the API in the native language of your application. Libraries will be added as they become available, to find community libraries vist the Recursion.Space Discord.

### Official Repositories

These are the current libraries officially maintained by Recursion.Space on [GitHub](https://github.com/RecursionSpace).

[RecursionSpace-Python](https://github.com/RecursionSpace/RecursionSpace-Python)
