# wheelplayer-site

GitHub Pages site for `wheelplayer.infra.nikolla.me`, the domain behind the
WheelPlayer (iPod) app's NFC album tags.

- `.well-known/apple-app-site-association` lets album links
  (`https://wheelplayer.infra.nikolla.me/album/<album id>`) open the app.
- `.nojekyll` keeps GitHub Pages from skipping the `.well-known` folder.
- `CNAME` sets the custom domain.
- `404.html` is shown when a tag is scanned on an iPhone without the app.

## Publishing

1. DNS: `CNAME wheelplayer.infra` → `<github-username>.github.io`.
2. Push this repo to GitHub, then in **Settings → Pages** publish from the `main`
   branch root and tick **Enforce HTTPS** once the certificate is ready.
3. Check it:

   ```sh
   curl -i https://wheelplayer.infra.nikolla.me/.well-known/apple-app-site-association
   curl -i https://app-site-association.cdn-apple.com/a/v1/wheelplayer.infra.nikolla.me
   ```

4. Reinstall the app on each iPhone once Apple's servers (second command) return the file.
