# contrapaul.com — portfolio / about / blog
Warm editorial light theme. Serves as personal portfolio, about page, and blog.
## To add a blog post
1. Create `/posts/your-post-name.html` using the same HTML structure
1. Link to it from the writing section in `index.html`
## To replace the profile photo
Replace the `.profile-image-placeholder` div in `index.html` with:
`<img src="assets/virginia.jpg" alt="Virginia Paul" class="profile-photo">`
And add `.profile-photo { width:160px; height:160px; border-radius:50%; object-fit:cover; }` to style.css
## Structure
- `index.html` — main page
- `style.css` — all styles
- `posts/` — add blog post HTML files here
- `assets/` — images and other media
