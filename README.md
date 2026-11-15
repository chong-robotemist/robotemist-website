# Robotemist Open lab: GoDaddy deployment

This is the ready-to-upload Open lab website. It uses the approved Open Workcell logo. Contact email is info@robotemist.com. Our vision follows Meet JARVIS. The background video is a closed 100-second loop.

The package contains a static website. No build command is needed on GoDaddy. No database or Node.js server is needed.

## Files

Extract the whole `robotemist-open-lab-godaddy-v2.zip` on your computer. The website files appear immediately. There is no inner ZIP. Double-click `index.html` to preview the page.

- `index.html`: the complete Open lab page. Styling and playback code are embedded. Fonts and logo presentation are embedded too.
- `media/`: the looping MP4 and its poster. Keep this folder beside `index.html`.
- `assets/`: the original logo files and font license.
- `asset-licenses.txt`: illustration notices. Keep this file online.
- `README.md`: these instructions. Keep this file locally.
- `file-manifest.json`: checksums for the uploaded files. Keep this file locally.

The ZIP places `index.html` directly at its root. It includes the light video and poster. The HTML has no external script or stylesheet dependency. It preserves the illustration credits. It excludes design controls and alternate themes.

## Hosting target

These steps target **GoDaddy Web Hosting (cPanel)**. Open your hosting account's File Manager. Use the document root assigned to the intended domain. The primary domain normally uses `public_html`. An additional domain can use a different folder. See [GoDaddy's upload guide](https://www.godaddy.com/en-uk/help/upload-files-using-my-web-hosting-cpanel-file-manager-3239).

## Upload

1. Sign in to GoDaddy. Open **My Products**.
2. Under **Web Hosting**, select **Manage** for the hosting account.
3. Open **File Manager** for the target domain.
4. Confirm the domain's document root. Save a backup of any existing website before replacing it.
5. Select **Upload**. Upload `robotemist-open-lab-godaddy-v2.zip`. Wait for the upload to reach 100%.
6. Return to File Manager. Select the ZIP. Select **Extract**. Explicitly set the destination to the target document root.
7. Confirm that `index.html` is directly inside that folder. The `assets` and `media` folders must sit beside it. Do not leave them inside a second `upload` folder.
8. If an old homepage still takes priority, move its `index.php`, `default.htm` or other default page into your backup. Review any old `.htaccess` redirects with the hosting administrator.
9. Delete the uploaded ZIP from the web folder after extraction. Keep your local copy. You can also remove README.md and file-manifest.json from the server.

GoDaddy documents the extraction step in its [ZIP extraction guide](https://www.godaddy.com/en-in/help/unzip-files-in-my-web-hosting-cpanel-account-8396).

## Domain and HTTPS

Use the domain assigned to this hosting account. Point its website DNS records to the hosting account as needed. Preserve email DNS records for info@robotemist.com.

Check that a valid SSL certificate is installed. If your plan provides AutoSSL, use **cPanel Admin → SSL/TLS Status → Run AutoSSL**. See [GoDaddy's AutoSSL guide](https://www.godaddy.com/help/install-an-ssl-using-autossl-on-my-web-hosting-cpanel-41641).

After SSL is working, open **cPanel Admin → Domains**. Enable **Force HTTPS Redirect** for the domain. The domain must already point to the hosting account. See [GoDaddy's HTTPS guide](https://www.godaddy.com/help/redirect-my-website-to-https-using-cpanel-27870?preview=true).

## Check the live site

- Open the HTTPS address in a private browser window.
- Confirm the Open Workcell logo in the header and footer.
- Confirm that no design selector is visible.
- Check that Meet JARVIS comes before Our vision.
- Click Contact us. Confirm the address is info@robotemist.com.
- Check the email link in a browser with an email app configured.
- Check that the background video starts muted.
- Watch through the 100-second boundary. The robots should return to their starting poses before repeating.
- Check the page on a phone.
- Open Illustration credits. Keep this file online.

The mailto link opens an email app. This package does not create a mailbox. The supplied address must exist with your email provider.

## Troubleshooting

**The old site appears:** confirm the domain's document root. Check for an old default page or redirect. Clear any hosting cache. Reload in a private window.

**The page looks unstyled:** confirm that you extracted the new package. Its index.html includes the styling. The older export used separate stylesheets. Replace the old HTML with the new file.

**The local video is missing:** extract the whole ZIP. Keep the media folder beside index.html. Open the extracted HTML in a browser. Do not open it inside an archive preview.

**The video is missing:** confirm `media/laboratory-work-v19-light.mp4` and its JPG poster were uploaded. Open the MP4 URL directly. The server should serve it as `video/mp4`. Browsers can limit autoplay under power-saving settings. The poster remains visible in that case.

**The email link does nothing:** configure a default email app. The address can also be copied.

**The account has no File Manager:** check the product name. This README targets Web Hosting (cPanel). A website-builder editor uses a different publishing process.

## Updates and rollback

Keep the previous site backup. To roll back, restore that backup to the same document root.

For a future update, change the source website. Run `python3 package_godaddy.py` from the source folder after the website dependencies are installed. Upload the resulting ZIP. No build tools are uploaded to GoDaddy.

The package has been prepared locally. It has not been uploaded to a hosting account.

The package has no JavaScript module requests. This avoids the local-file restrictions described in [MDN’s module guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules/Modules_on_the_web).
