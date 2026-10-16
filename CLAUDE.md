# CLAUDE.md — SonzaSpark Site

This folder is the SonzaSpark global brand site (sonzaspark.com). It is **one site in a larger workspace** — see the workspace `CLAUDE.md` at `../CLAUDE.md` for workspace-wide conventions.

## Always Do First
- **Invoke the `frontend-design` skill** before writing any frontend code, every session, no exceptions.

## Site identity (locked)

- **Brand:** SonzaSpark. Developed by HyracTech. Operated in Tanzania by Afriqo E-Learning Tanzania.
- **Audience:** young makers (ages 8–18), their parents, schools, sponsors, AND a global audience of college students / international STEM enthusiasts following the project content.
- **Tagline direction:** "Spark curiosity. Build real things."
- **Palette (locked, from the real SVG logo):**
  - Primary orange `#f97316` (brand mark + accents, CTAs)
  - Orange dark `#c2410c` (hover/active)
  - Orange light `#fb923c`
  - Primary blue `#3b82f6` (brand mark star + secondary accents)
  - Blue dark `#1e40af`
  - Blue light `#60a5fa`
  - Slate ink `#0F172A` (text)
  - Muted slate `#475569` (secondary text)
  - Paper `#FFFFFF`, cream paper `#FFFBF5`
  - Line `#E2E8F0`
- **Typography:** Nunito (friendly rounded sans — matches the current site's warmth; works for kids, teens AND adults). Weights 400, 500, 600, 700, 800. **No display serifs. Not Poppins (that's Afriqo).**
- **Logo:** real SVG at [brand_assets/sonzaspark-logo.svg](brand_assets/sonzaspark-logo.svg). Hero image at [brand_assets/sonzaspark-hero.png](brand_assets/sonzaspark-hero.png).
- **What SonzaSpark DOES feature:** Robotics, Coding, 3D Printing, Electronics & IoT, Fabrication, Soft Skills. Weekend classes, holiday bootcamps, school STEM clubs, online classes & communities (via LMS + HyracHub), mobile STEM lab, teacher training.
- **Online channel:** SonzaSpark runs self-paced courses on its LMS, live video workshops, and open learner communities on [HyracHub](https://hyrachub.com). HyracHub is a HyracTech-owned community platform (separate from HyracTech the organization) — reference it when talking about online or community delivery.
- **What SonzaSpark DOES NOT feature (locked):**
  - No prices or local workshop dates — those live on afriqoelearningtz.com (Tanzania operator)
  - No enrollment forms — same reason
  - **No OBA mention** — donor channel stays behind the scenes
  - No Afriqo Nexus / sister-country references (future)
  - No cartoon kid-doodle aesthetic (dashed-everywhere outlines, excessive rotation). Keep energy but credible.

## Positioning (locked)

Project-first, built for curious minds of all ages. The hero is a real project a student built, not a stock photo of a happy kid. Energy comes from the actual work shown, not from decorative tricks.

Three audiences, one brand:
- **Young makers & parents** — enrol / "In Tanzania?" → afriqoelearningtz.com
- **Schools & NGOs** — partnership inquiries
- **Global followers** — follow the projects on social

## Reference Images
- If a reference image is provided: match layout, spacing, typography, and color exactly.
- If no reference: design from scratch with high craft (see guardrails below).
- Screenshot output, compare, fix, re-screenshot. At least 2 comparison rounds.

## Local Server
- From the workspace root: `node tools/serve.mjs sonzaspark 3001`
  (I'm using port 3001 to not conflict with afriqo-tz on 3000 if both are running.)
- Pass just the site name and port; defaults to port 3000 if omitted.

## Screenshot Workflow
- `node tools/screenshot.mjs http://localhost:3001 label` from workspace root
- Mobile: `node tools/screenshot.mjs http://localhost:3001 mobile 390`
- Screenshots save to `../temporary screenshots/`.

## Output Defaults
- Single [index.html](index.html), inline CSS
- Tailwind CSS via CDN
- Mobile-first responsive
- All asset paths **relative** (`brand_assets/...`, `photos/...`)

## Brand Assets
- [brand_assets/](brand_assets/) — SonzaSpark SVG logo + hero image
- [photos/](photos/) — real program photos

## Anti-Generic Guardrails
- Palette is locked. Use the SonzaSpark orange + blue exactly as above.
- Shadows should be color-tinted (orange-shadow on orange cards, blue on blue sections) not flat `shadow-md`.
- Typography: Nunito everywhere. Vary weight for hierarchy. Tight tracking on large headlines, generous line-height on body.
- Gradients: layer blue → orange gradients sparingly for depth; add noise texture where it adds warmth.
- Animations: only `transform` and `opacity`. Never `transition-all`.
- Interactive states: hover, focus-visible, active on every clickable element.
- Images: real photos drive the design. Add subtle gradient overlays only where captions need legibility.
- Depth: layered (base → elevated card → floating badge), not flat.

## Hard Rules
- Do not add Tanzania-specific pricing, dates, or enrollment flows (that's for afriqoelearningtz.com)
- Do not re-introduce OBA or sister-country references
- Do not use default Tailwind blue/indigo as primary — use the SonzaSpark `#3b82f6` exactly (it's the brand's chosen blue, not a Tailwind-generic choice)
- Do not use `transition-all`

## Deployment
- Will deploy to: GitHub repo `sonzaspark-website` under `afriqodev001` (will transfer to a HyracTech org later)
- Will serve at: https://sonzaspark.com (replacing current WordPress site after review)
- Deploys on push to `main` via GitHub Pages
