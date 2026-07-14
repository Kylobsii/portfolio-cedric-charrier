# 🔦 Project Name

Optional: per-page background via CSS variables (see Chasm.md's <style> block) — drop in a splash image and tint each project page to have its own
mood/atmosphere:

    ```html
    <style>
    :root {
        --page-bg: url('../assets/images/YourImage.png');
        --page-bg-opacity: 1;
        --page-bg-brightness: 1;
        --content-overlay: rgba(0, 0, 0, 0.92);
        --header-bg-color: rgb(20, 20, 20);
    }
    </style>
    ```

One-line pitch (the hook — what it is, in a single punchy sentence). Bold the 2-3 key nouns/verbs that matter (genre, core mechanic).

**Role:** what I did
**Team size:** solo / N people
**Duration:** X weeks/months
**Tools:** engine, language, libraries
**Links:** [GitHub](#) · [Play it](#) · [Trailer](#screenshots-video or #videos)

## Overview
2-4 sentences of context — what the project is, why it exists (school project? jam? personal?), what the creative/design constraints or starting themes were if relevant. Good place for a side-by-side figure pair showing the core mechanics or hook, using the two-column layout:

    ```html
    <div class="figures-row" markdown>

    <figure markdown>
    ![Alt text](../assets/images/example.gif){ width="400" }
    <figcaption>Caption</figcaption>
    </figure>

    <figure markdown>
    ![Alt text](../assets/images/example2.gif){ width="400" }
    <figcaption>Caption</figcaption>
    </figure>

    </div>
    ```

Couple sentences on scope/output (how long, how much content was produced) and a short line of pride/reflection.

## My Contribution

Concrete, specific bullets/paragraphs of what you personally did — systems,
features, tools.
Another figures-row pairing works well here too if you have supporting GIFs.

## Videos

For YouTube trailers/gameplay clips, embed via iframe rather than a raw
<video> tag :

    ```html
    <figure>
    <iframe
        width="560"
        height="315"
        src="https://www.youtube.com/embed/VIDEO_ID"
        title="YouTube video player"
        frameborder="1"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin"
        allowfullscreen>
    </iframe>
    <figcaption><em>Caption for this video.</em></figcaption>
    </figure>
    ```

One `<figure>` per video with caption.

## Challenges & what I learned

1-2 concrete problems + how worked through them
