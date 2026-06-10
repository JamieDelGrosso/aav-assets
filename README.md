# aav-assets

Public CDN bucket for assets served on [aav.space](https://aav.space).

Files in this repo are fetched at runtime by client-side JavaScript via the
[jsDelivr GitHub CDN](https://www.jsdelivr.com/github), so the repo is public
by necessity — anything a browser can load is fetchable by anyone with the URL.
The Aurora Avionics website source itself lives elsewhere (Webflow); only
deliverable assets that don't fit inside Webflow's allowed file types are
hosted here.

## Hosted assets

| File | Purpose | jsDelivr URL |
|---|---|---|
| `stack-xhd.glb` | Hero 3D model for the homepage stack viewer | `https://cdn.jsdelivr.net/gh/JamieDelGrosso/aav-assets@main/stack-xhd.glb` |

## Versioning

Pin a specific commit in the jsDelivr URL for stability:

```
https://cdn.jsdelivr.net/gh/JamieDelGrosso/aav-assets@<commit-sha>/stack-xhd.glb
```

Using `@main` is fine for in-flight iteration; switch to a pinned SHA before the
embed goes live so a future commit can't accidentally break the homepage.

## Updating an asset

1. Replace the file locally.
2. `git commit -am "update stack-xhd.glb"` and push.
3. jsDelivr serves the new content within a few minutes.
4. If you've pinned a SHA in the Webflow embed, update that to the new commit
   SHA to publish the change.
