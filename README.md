# Purushottam Khakurel — Portfolio v2

Responsive personal portfolio and Markdown-powered blog built with plain HTML, CSS and JavaScript. No build step required.

## Enable GitHub Pages
1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select **main** and **/(root)**, then Save.
4. The site will publish at https://purushottamkhakurel.com.np/  (allow a few minutes).

## Publish a blog post
1. Add a Markdown file inside `posts/`, e.g. `my-new-post.md`.
2. Add an entry to `posts/posts.json`:
   ```json
   {
     "slug": "my-new-post",
     "title": "My New Post",
     "date": "2026-11-10",
     "category": "GRC",
     "excerpt": "A short summary shown on the blog listing.",
     "readingTime": 4,
     "file": "my-new-post.md"
   }
   ```
3. Categories: `Cybersecurity`, `GRC`, `AI`, `Football`.
4. Commit both files. The article will appear automatically.

## Customize
- Edit your details and links in `index.html`.
- The portrait and résumé currently load from the original portfolio repository; that repository is not modified.
- Edit styles in `css/styles.css`.
- Markdown rendering uses Marked from jsDelivr.

Four editable starter articles are included. Review and personalize them before sharing.
