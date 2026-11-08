<div align="center">

<img src="assets/logo.png" alt="BEU Study logo" width="110" />

# BEU Study

**Free branch-wise video lectures for Bihar Engineering University (BEU) students.**

Pick your branch, semester and subject, and the matching YouTube lecture playlist opens instantly. Fast, mobile-friendly and installable as an app.

[**Live Demo**](https://mdzafar864.github.io/Engg-Study-App/) · [Report a Bug](../../issues) · [Request a Feature](../../issues)

![PWA](https://img.shields.io/badge/PWA-ready-16a34a)
![HTML5](https://img.shields.io/badge/HTML5-CSS3-0b1e3a)
![JavaScript](https://img.shields.io/badge/Vanilla-JavaScript-f5a623)
![License](https://img.shields.io/badge/Build%20step-none-blue)

</div>

---

## About

**BEU Study** is a lightweight web app made for students of **Bihar Engineering University (BEU)**. Finding the right lecture playlist for a subject usually means searching YouTube again and again. BEU Study removes that step: choose your **Branch**, then your **Semester**, then your **Subject**, and tap **Watch Playlist**. The curated lecture playlist plays right inside the app.

The app is built with plain HTML, CSS and vanilla JavaScript. There is no framework, no build step and no backend, so it loads quickly even on slow mobile networks.

## Features

- **Branch, semester and subject selection** with three simple dropdowns that unlock one after another
- **Built-in playlist player** that opens the lecture playlist in a full-screen modal, with an **Open in YouTube** button
- **Clean, minimal interface** in a navy and gold theme, designed mobile-first
- **Installable PWA** that you can add to your home screen like a native app
- **Offline app shell**, so the interface loads even on a flaky connection (videos still need internet)
- **Easy to extend**, because all content lives in a single file, `js/data.js`
- **SEO ready** with meta tags, Open Graph, Twitter Card, schema markup, `sitemap.xml` and `robots.txt`
- **Google Analytics 4 events** for branch, semester, subject, watch and install actions
- **No API keys, no server, no cost**

## Branches covered

Computer Science & Engineering (CSE) · Electrical Engineering (EE) · Electronics & Communication Engineering (ECE) · Mechanical Engineering (ME) · Civil Engineering (CE), across Semesters 1 to 8.

## Tech stack

| Layer | Technology |
| --- | --- |
| Markup | HTML5 |
| Styling | CSS3 (custom properties, responsive layout) |
| Logic | Vanilla JavaScript (ES6) |
| Offline and install | Service Worker and Web App Manifest |
| Video | YouTube embedded playlist player |
| Hosting | Any static host, such as GitHub Pages |

## Project structure

```
BEU-Study-App/
├── index.html            Page markup and SEO tags
├── manifest.json         PWA metadata (name, icons, theme color)
├── service-worker.js     Caches the app shell for offline use
├── robots.txt            Search-engine crawl rules
├── sitemap.xml           Search-engine page listing
├── css/
│   └── style.css         All styling
├── js/
│   ├── data.js           Branches, semesters, subjects, playlist ids
│   └── app.js            Dropdown logic, video modal, PWA install
├── assets/               Logo, favicons and app icons
└── README.md
```

## Getting started

No build tools are needed. Clone the repo and serve the folder:

```bash
git clone https://github.com/mdzafar864/Engg-Study-App.git
cd Engg-Study-App
python3 -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

> **Note:** YouTube embeds need a real `http(s)` origin. Use a local server as shown above. Opening `index.html` by double-clicking may show YouTube "Error 153" in the player.

## Adding or editing content

All content lives in `js/data.js`. Nothing else needs to change.

**1. Add a branch** to the `BRANCHES` array:

```js
{ id: "it", name: "Information Technology", short: "IT" }
```

**2. Change semesters** by editing `SEMESTERS`, which is `[1, 2, 3, 4, 5, 6, 7, 8]` by default.

**3. Add a subject and playlist** under `SUBJECTS[branchId][semesterNumber]`:

```js
{ name: "Data Structures", playlistId: "PLxCzCOWd7aiEwaANNt3OqJPVIxwp2ebiT" }
```

The playlist id is the part of the YouTube URL after `list=`. For example, in
`https://www.youtube.com/playlist?list=PLxCzCOWd7aiEwaANNt3OqJPVIxwp2ebiT`
the id is `PLxCzCOWd7aiEwaANNt3OqJPVIxwp2ebiT`.

A subject left as `"REPLACE_WITH_PLAYLIST_ID"` shows a friendly "playlist not added yet" message instead of a broken player, so you can publish the app before every subject has a playlist.

## Deployment

BEU Study is a static site and works on any static host:

- **GitHub Pages:** push the repo, then go to *Settings → Pages* and select the `main` branch.
- **Netlify or Vercel:** drag and drop the folder, or connect the repo.
- **Cloudflare Pages, Firebase Hosting, S3:** upload the folder as it is.

No environment variables or backend are required. After deploying under a new URL, update the canonical link and Open Graph URLs in `index.html`, and the domain in `sitemap.xml` and `robots.txt`.

## Contributing

Contributions are welcome, especially new subject playlists for your branch and semester.

1. Fork the repository
2. Add the subject and playlist id in `js/data.js`
3. Open a pull request

## Developer

**Md Zafar**, Founder of MZ Tech Solutions
Full-Stack Developer · UI/UX Designer · PWA Specialist

- LinkedIn: [mdzafar864](https://www.linkedin.com/in/mdzafar864)
- YouTube: [Engineers Pathway](https://youtube.com/@engineerspathwayofficial)

## Disclaimer

BEU Study is an independent student resource and is not officially affiliated with Bihar Engineering University. All video lectures belong to their respective creators on YouTube.

---

<div align="center">© 2026 MZ Tech Solutions. All Rights Reserved.</div>
