# contrapaul.com — portfolio / about / blog
Warm editorial light theme. Serves as personal portfolio, about page, and blog.
## To add a blog post
The homepage (`index.html`) builds its post list automatically at page load — it fetches
`posts/manifest.json`, reads each listed post's own `<meta>` tags, and sorts everything by
date. Nothing on `index.html` is ever hand-edited.
1. Open `new-post.html` in a browser (works straight from disk, no server needed) and use it
   to write the post and generate the code — see that file for the full workflow.
2. Save the generated code as a new file in `posts/`.
3. Add the generated manifest line to the array in `posts/manifest.json`.

If writing a post file by hand instead of using the tool, it must include these `<meta>` tags
in its `<head>` (see any existing post for reference):
- `<meta name="post-title" content="...">` — title shown on the homepage card
- `<meta name="post-date" content="YYYY-MM-DD">` — drives sort order
- `<meta name="post-date-label" content="...">` — optional, overrides the displayed date text
- `<meta name="post-tag" content="...">` — topic pill
- `<meta name="description" content="...">` — excerpt

Because `index.html` fetches these files, viewing the site locally requires serving it over
`http://` rather than opening it as a `file://` — e.g. `python3 -m http.server` from this
directory.
## To replace the profile photo
Replace the `.profile-image-placeholder` div in `index.html` with:
`<img src="assets/virginia.jpg" alt="Virginia Paul" class="profile-photo">`
And add `.profile-photo { width:160px; height:160px; border-radius:50%; object-fit:cover; }` to style.css
## Structure
- `index.html` — main page, renders the post list dynamically from `posts/manifest.json`
- `new-post.html` — local authoring tool: fill in fields, write the post, generate the code
- `style.css` / `posts.css` — shared styles
- `posts/` — blog post HTML files, plus `manifest.json` listing which ones to show
- `assets/` — images and other media
