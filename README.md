# Jann Alvin Naraja — Portfolio

Personal portfolio website for **Jann Alvin Naraja**, a video editor, filmmaker and creative designer.

The whole site is **one file: `index.html`**. All the CSS, JavaScript and images are inside it, so there is nothing to install or build. Open it in a browser or host it as-is.

## Features

- **Hero section** with a short intro, headline, photo and a "View my work" button.
- **Demo reel** from Vimeo with custom controls (play/pause, seek slider, time, volume, fullscreen).
- **Selected work** grid with filter buttons (All, Video, Design, Website) and a **Show more / Show less** button. It shows 3 projects at first.
- **Clients I've worked with**: a scrolling logo strip. Each logo is clickable and opens the client's website in a new tab.
- **About** section with a bio, a **Skills** list and work experience.
- **Contact** section with email, phone, location, Instagram and LinkedIn.
- **Dark / light mode** button in the menu (next to Contact). It follows the visitor's device setting at first and remembers their choice.
- **Logo in the menu** and as the **browser tab icon** (dark version in light mode, white version in dark mode).
- **Hover effects**: the photo, project thumbnails, client logos and buttons grow slightly when hovered. These are turned off for visitors who have "reduce motion" enabled.
- **Responsive layout** for phones, tablets and desktops.

## How the site is built

| Part | Where to find it in `index.html` |
| --- | --- |
| Colors (light and dark) | CSS variables at the top of `<style>` (`--bg`, `--fg`, `--muted`, `--line`, `--tile`) |
| Menu, logo, theme button | `<header>` |
| Intro and headline | `<div class="hero">` |
| Demo reel | `<iframe id="rv">` and the `.bar` controls |
| Selected work | `<section id="work">` |
| Clients | `<section id="clients">` |
| About, skills, experience | `<section id="about">` |
| Contact | `<section id="contact">` |
| Behavior (filters, Show more, theme toggle, reel controls) | `<script>` at the bottom |

## Common edits

**Change text**
Search the file for the text you want (for example `Hey, Jann Alvin here!`) and edit it.

**Add or change a project**
Each project is a card inside `<div class="grid">`:

```html
<a class="card" data-t="video" href="YOUR-LINK">
  <div class="ph v"><span>Video thumbnail</span></div>
  <h3>Project title</h3>
  <small>Video · 2026</small>
</a>
```

- `data-t` decides which filter it belongs to: `video`, `design` or `website`.
- The cards are still **placeholders**. Replace the title, year and thumbnail with real work.
- Only 3 cards show at first. The rest appear when "Show more" is clicked. To change how many show at first, change `var LIMIT=3` in the script.

**Add a filter**
Add a button next to the others, for example `<button data-f="motion">Motion</button>`, then give matching cards `data-t="motion"`.

**Change a client logo link**
Find the logo's `<a class="lg-link" href="...">` and change the `href`.

**Add a client logo**
Copy an existing `<a class="lg-link">...</a>` block. The logos are single-color images used as masks, so use a PNG with a transparent background (the shape is what matters, not its color). The page's script duplicates the strip automatically so it scrolls in a loop. If you add logos, you can change the speed by editing `slide 45s` in the CSS (a larger number is slower).

**Change the reel video**
In the `<iframe id="rv">` line, change the number after `player.vimeo.com/video/` to your Vimeo video ID.

**Change contact details**
Edit the email, phone (`tel:+639620592335`), Instagram and LinkedIn links inside `<section id="contact">`.

## Publish with GitHub Pages

1. Create a new **public** repository on GitHub.
2. Upload `index.html` and this `README.md` (**Add file → Upload files**, then **Commit changes**).
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
5. After a minute or two, your site is live at `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`.

To update the site later, upload a new `index.html` with the same name. If you don't see the change, hard refresh (Ctrl+Shift+R, or Cmd+Shift+R on Mac).

## Notes

- Images are embedded inside `index.html`, which is why the file is large (around 700 KB). That is normal for this setup.
- The client logos are shown in a single color on purpose. If you want full-color logos, the images would need to be replaced with the original colored files.
- The demo reel is hosted on Vimeo, so it needs an internet connection to play.

## Contact

Jann Alvin Naraja — Bulacan, Philippines
Email: jnnlvn.naraja@gmail.com
Instagram: [@_jann.mov](https://www.instagram.com/_jann.mov/)
LinkedIn: [jannalvinnaraja](https://www.linkedin.com/in/jannalvinnaraja/)
