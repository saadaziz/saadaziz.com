# saadaziz.com

Static portfolio site with an authenticated CareerGPT demo.

## CareerGPT demo authentication

`demo.html` prompts for credentials supplied by Saad, calls the backend `/auth/login` endpoint, and stores only the returned signed session token in a first-party `saadaziz.com` cookie. It never stores the raw username or password.

The protected analysis call sends the token in an `Authorization: Bearer ...` header to:

```text
https://aurorahours.com/chatgpt_v1/demo
```

When the token expires or becomes invalid, the page deletes the cookie and prompts again. A sign-out control is included.

The backend must be deployed first and configured with:

```text
demo_username
demo_password
```
