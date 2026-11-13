# INTARE Sports Club

Public website hosted on Vercel, with the approved seven pages, photos, and fonts stored in Supabase. No API keys, passwords, private membership records, or local server are required.

## Upload in your browser

1. Extract `INTARE-GitHub-files.zip`.
2. Open https://github.com/IsmaelShadie/INTARE-project .
3. Choose **Add file → Upload files**. In an empty repository, click **uploading an existing file** instead.
4. Drag **all extracted files and the api folder** into the upload area. Upload the contents, not the ZIP or an extra enclosing folder.
5. Confirm the repository root has `package.json`, `vercel.json`, `README.md`, and `api/site.js` (site.js must remain inside api).
6. Commit to the default branch with message `Launch INTARE website`.
7. Open the connected Vercel project and its Deployments tab. The commit should trigger deployment. If no deployment starts, report the state instead of creating a duplicate project.

## Deployment settings if prompted

Framework: **Other**. Root Directory: repository root. No custom install/build command or output directory is required; `vercel.json` supplies the function build and routing. Node.js: **22.x** (also specified in package.json).

Vercel project: https://vercel.com/belyibnsidiiq-7724s-projects/intare-sports-club
Supabase storage dashboard: https://supabase.com/dashboard/project/oejuyodijdjneersnnrz/storage/buckets

## Public access and checks

After Vercel reports Ready, open its assigned production URL in a private browser window without Vercel login. If authentication is required, review this project's Settings → Deployment Protection and allow public production access as available in your plan; do not change the entire team's settings.

Verify Home, Club, Subscriptions, Coaching, Aerobics, Reviews, and Visit; mobile navigation; subscription selection; and WhatsApp drafts. The website does not process payments or activate memberships automatically.

## Architecture

`api/site.js` retrieves only seven allowlisted public HTML files from Supabase. Each page embeds its own photos and fonts. Vercel serves those pages as HTML and caches responses for five minutes, with up to ten minutes of stale-while-revalidate caching. This keeps the website content in Supabase rather than copying it into this repository.

Only approved public website pages are read. Source/website ZIP backups remain in a separate private Supabase bucket. No environment variables are needed for the current public-site read path. Do not add Supabase service-role keys or database passwords to this repository.

Exact conditional membership policies and activation/renewal details still direct visitors to staff. Missing social URLs remain inactive. Confirm photo permissions before public launch.
