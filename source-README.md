# WatchWarden App Store Web Collateral

Last updated: 2026-07-14 America/Chicago

App Store Connect requires public Support URL and Privacy Policy URL values before App Review submission. `watchwarden.app` does not currently resolve from this workspace, so the files in this directory are deployment-ready source pages rather than live URLs.

Recommended hosted paths:

- Support URL: `https://conorgg123.github.io/watchwarden-app-site/support/`
- Privacy Policy URL: `https://conorgg123.github.io/watchwarden-app-site/privacy/`
- User Privacy Choices URL: `https://conorgg123.github.io/watchwarden-app-site/privacy-choices/`
- Terms URL, optional but useful: `https://conorgg123.github.io/watchwarden-app-site/terms/`

Files:

- `support.html`
- `privacy.html`
- `privacy-choices.html`
- `terms.html`
- `app-privacy-answers.md`

Create a static-host deployment package with:

```sh
scripts/package_appstore_web.sh
```

The generated package contains clean route folders for `/support`, `/privacy`,
`/privacy-choices`, and `/terms`, plus Netlify, Vercel, and GitHub Pages routing
metadata. It does not claim an unconfigured custom domain.

After hosting these pages, update App Store Connect:

1. Set the iOS version Support URL to the public support page.
2. Set App Privacy Policy URL to the public privacy page.
3. Set User Privacy Choices URL to the public privacy choices page if App Store Connect asks for it.
4. Use `app-privacy-answers.md` while completing App Privacy data-collection answers.
5. Re-check the hosted URLs with `scripts/check_external_release_gates.sh --report-only --check-urls` before submitting for review.
