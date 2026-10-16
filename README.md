# StoryCast

StoryCast is a 3-page accessible microsite that showcases short audio and video stories. Every story has captions or a full transcript. It is built with semantic HTML5, Sass, CSS Grid, Flexbox, and a container query, with no frameworks.

## Pages

- **Home** (`index.html`): introduces StoryCast and features three stories
- **Story** (`story/story-01.html`, `story-02.html`, `story-03.html`): a video story and two audio stories, each with a transcript and related stories
- **About & Access** (`about.html`): the mission, accessibility features, and how to explore the site

## Project structure

```
storycast/
  index.html
  about.html
  story/
    story-01.html        Autumn Leaves (video, captions, transcript)
    story-02.html        Rain on the Window (audio, transcript)
    story-03.html        Morning Birdsong (audio, transcript)
  sass/
    main.scss            imports every partial
    _layers.scss         cascade layer order
    _colors.scss         color tokens
    _typography.scss     type tokens
    _spacing.scss        spacing tokens
    _base.scss           reset and base layers, focus styles, skip link
    layout/
      _header.scss
      _main.scss
      _footer.scss
    components/
      _nav.scss
      _button.scss
      _media-card.scss   includes the container query
      _story.scss
      _about.scss
  css/
    main.css             compiled styles
  assets/
    video/
    audio/
    transcripts/         captions (.vtt)
    images/
  docs/                  research document, sitemap
```

## Sass and CSS architecture

- Tokens live in partials (`_colors`, `_typography`, `_spacing`) as Sass variables and CSS custom properties.
- Cascade layers are declared in `_layers.scss` in the order `reset, base, layout, components, utilities`. Each partial wraps its styles in its layer.
- Class names follow BEM (for example `media-card__title`, `nav__link`).
- Layouts use Grid (story card grid, feature list) and Flexbox (header, nav, footer).
- The `.media-card` is a container (`container: media-card / inline-size`). Its title and text get larger when the card is wider than 24rem, regardless of the window width.

## Accessibility checklist

- [x] Semantic landmarks on every page: `header`, `nav`, `main`, `article`, `section`, `figure`, `footer`
- [x] One `h1` per page and a logical heading order (`h1`, `h2`, `h3`)
- [x] `lang="en"` set on every page
- [x] Video has English captions through a `<track kind="captions">` element (`assets/transcripts/story-01.vtt`)
- [x] Every audio and video story has a full text transcript on the same page, including descriptions of meaningful sounds
- [x] `<figcaption>` describes each piece of media
- [x] Skip link as the first focusable element on every page
- [x] Visible focus outline on all interactive elements (purple on light backgrounds, yellow on dark ones)
- [x] Everything is reachable and usable with the keyboard alone
- [x] `aria-label` on each `nav`, `aria-labelledby` on sections, and `aria-current="page"` for the current page
- [x] Colors chosen for WCAG 2.1 AA contrast, with the current page and links not marked by color alone
- [x] Responsive layouts that hold up on small screens and at 200% zoom
- [x] `prefers-reduced-motion` respected
- [x] Checked with Chrome Lighthouse (Accessibility) on all five pages and with keyboard-only testing

## Running locally

1. Clone the repository:
```
   git clone https://github.com/Melyssa-Ingabe/storycast.git
   cd storycast
```
2. Install Sass once:
```
   npm install -g sass
```
3. Compile and watch the styles:
```
   sass sass/main.scss css/main.css --watch
```
4. Open `index.html` in a browser. Using the VS Code Live Server extension gives automatic reloading.

## Design and research

- Research document (PDF): `docs/research-document.pdf` *https://docs.google.com/document/d/1GISwTzxUgBFdC1cQIVOYZsldblZiuoJ9E0YbwYQ9ibQ/edit?usp=sharing*
- Sitemap: `docs/sitemap.png` 
- Wireframes and High-fidelity mockups (Figma): *https://www.figma.com/design/j32T6KzJ4OqOhpegSQVavo/StoryCast?node-id=1-142&t=IploMlBXFu9iEKcl-1*

## Media credits

- Autumn Leaves: video by Kris Møklebust from Pexels
- Rain on the Window: audio by PWLPL from Pixabay
- Morning Birdsong: audio by Creative_Spark from Pixabay