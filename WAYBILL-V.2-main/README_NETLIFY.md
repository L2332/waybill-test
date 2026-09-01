# Netlify Secure Waybill Editor

This is the Netlify-compatible secure version using Netlify Functions.

## Upload to Netlify

1. Upload the whole project to GitHub.
2. In Netlify, choose **Add new site** > **Import an existing project**.
3. Build settings:
   - Build command: leave blank
   - Publish directory: `public`
   - Functions directory: `netlify/functions`

## Environment Variables

In Netlify dashboard:
Site configuration > Environment variables > Add variable

Add:

```txt
APP_PASSWORD=your_password
SESSION_SECRET=long_random_secret
DISCORD_WEBHOOK_URL=your_discord_webhook
```

## Important

- Do not place passwords or Discord webhooks inside frontend HTML/JS files.
- The protected editor is stored in `private/editor.html`.
- If the user is not logged in, `/` and `/editor` redirect to `/login`.
- Password and Discord webhook are handled by Netlify Functions and environment variables.
- Frontend UI code can still be viewed by a logged-in browser user because browsers must download frontend code.
