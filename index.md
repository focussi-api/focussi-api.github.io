---
title: Home
nav_order: 1
---
# CBA Customer API

This is the API documentation for customers to integrate with CBA. If you want to get the work automated for your company, this would be what you are looking for. 

Before you get started let's prepare the things we need to use the API.

1. **Tokens**. Please contact our IT department to get following tokens. 
    - `Authentication Tokens`. Pelease refer to [Authentication](/references/authentication) to see how an API request is authenticated.
    - `Fleet Token`. More information is availabel for you to see the definition for [Fleet](/references/terms_and_concepts.html#fleet). 
    - `Product Token`. Product token is needed for you to add coverage via API. The [product](references/terms_and_concepts.html#product) must be specified for any type of coverage.

2. **Tools**. Web API doesn't depend on any language or platform, so it's OK for you to develop with any tools you like. We recommend you use a REST client to test the APIs. Our IT team uses `postman` and `curl` to test a single API request. 

Now you should be ready to start your API integration. Let's run our "Hello World" test.

```bash
curl --user <user>:<password> -X POST -H "Content-Length: 0" \
https://connect-test.focussi.com/api/test_connection
```

If you receive a response with status `200` in your end, that would mean your first API request runs successfully. Good luck to you!

