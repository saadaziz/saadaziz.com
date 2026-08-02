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


## Contact form

The contact form is a static GitHub Pages form submitted asynchronously to Formspree using the endpoint configured in `index.html`.

Current public contact email: `hiresaad@gmail.com`

Before production use, confirm in the Formspree dashboard that form endpoint `mgoggvpv` is active and delivers submissions to `hiresaad@gmail.com`. The website includes a direct email fallback when Formspree is unavailable.

## Deployment

Commit the changed files to the `main` branch of `saadaziz/saadaziz.com`. GitHub Pages will publish the custom domain automatically through the existing `CNAME` file.

## Favicon

The site includes a complete favicon set: `favicon.ico`, `favicon.svg`, 16px and 32px PNG icons, an Apple touch icon, Android icons, and `site.webmanifest`. All HTML entry pages reference the same root-level icon assets.
