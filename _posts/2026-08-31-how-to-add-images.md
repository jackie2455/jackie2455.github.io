---
layout: post
title: How to Add an Image to Your Academic Homepage
date: 2026-08-31 00:00:00 +0000
description: A short tutorial on adding images to an al-folio site — the profile picture on the homepage and inline images in posts.
tags: tutorial images
categories: sample-posts
thumbnail: assets/img/blog-profile-pic.png
---

This is a quick, copy-paste tutorial for adding images to your [al-folio](https://github.com/alshedivat/al-folio) homepage. There are two common cases: **(1) the profile picture** on the home page, and **(2) inline images** inside a page or blog post.

## 1) The profile picture (homepage avatar)

The homepage shows your photo next to your biography. Two steps:

**Step 1 — put your photo in the images folder.** Copy your image into `assets/img/` and give it a name. For example, this site uses `assets/img/prof_pic.jpg`:

```bash
cp path/to/your-photo.jpg assets/img/prof_pic.jpg
```

**Step 2 — point `about.md` to it.** Open `_pages/about.md` and set the `profile.image` field to your file name. Set `image_circular: true` if you want it cropped into a circle:

```yaml
profile:
  align: right
  image: prof_pic.jpg      # the file name inside assets/img/
  image_circular: true     # true = circular avatar
  more_info: >
    <p>School of Marine Engineering, Jimei University</p>
    <p>Email: you@example.com</p>
```

That's it — the homepage will now show your profile photo.

## 2) Inline images in a post

To show an image inside a blog post or page, put the file in `assets/img/` and render it with the `figure.liquid` include (this is the al-folio way, giving you responsive sizing and captions):

{% include figure.liquid path="assets/img/blog-profile-pic.png" class="img-fluid rounded z-depth-1" zoomable=true %}

<div class="caption">
  The profile image above is rendered with the <code>figure.liquid</code> include and <code>zoomable=true</code>.
</div>

You can also write a plain Markdown image:

```markdown
![My profile photo](/assets/img/blog-profile-pic.png)
```

Which looks like this:

![My profile photo](/assets/img/blog-profile-pic.png)

## Tips

- **Where images live:** always under `assets/img/` (the `path` is relative to the site root, e.g. `assets/img/your-image.png`).
- **Keep them small:** a profile photo around 180×180 px and under ~50 KB loads fast.
- **Post thumbnail:** set `thumbnail: assets/img/your-image.png` in the post's front matter to show a small image on the blog list card.
- **Zoomable:** add `zoomable=true` to `figure.liquid` so readers can click to enlarge.

Feel free to delete this example post once you've got the hang of it. Happy publishing!
