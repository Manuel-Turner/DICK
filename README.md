````markdown
# DICK — *Disciplinary Inquiries into Casual Knowledge* (Demo Journal Portal)

DICK is a **demo** academic-journal portal that showcases editorial workflows and UI patterns for a journal whose core ethos is **serious methods, unserious domains**. The repository emphasizes credible journal-grade information architecture, submission/access flows, and policy-bound presentation—**not** real publishing operations.

> **Demo status:** This site and its contents exist to demonstrate editorial workflows and UI patterns. It is not a live journal service.

---

## Scope and Sections

Depending on the current implementation (see `src/pages/`), the site typically includes:

- **Home** — journal positioning and primary entry points  
- **Articles / Archive** — listing, filters, and access routing (OA / Non-OA)  
- **Article Detail** — metadata + abstract; OA full text or Non-OA gating  
- **Columns** — thematic sections and calls for papers (status, scope notes, editors)  
- **Aims & Scope / Policies** — methods standards, ethics, and editorial boundaries  
- **Team / Masthead** — named roles + open roles (vacant)  
- **Submit** — submission workflow (demo implementation)

---

## Editorial & Compliance Constraints (Hard Rules)

This project must comply with the following non-negotiable constraints:

1. **Demo site and content**  
   All demo articles must be labeled **“DEMO”** and include a demo notice.

2. **No DOI**  
   Do **not** mention, display, or imply any real DOI. Do **not** imply DOI registration.

3. **Demo authorship convention**  
   All demo article authors are listed as **“Cardo”** (site demonstration rule), without exceptions.

4. **Access model (OA vs Non-OA)**  
   - **OA** pages display full text.  
   - **Non-OA** pages keep metadata/abstract public while gating full text.

5. **Payment/contact flows are illustrative only**  
   Any QR/payment/contact flow is a UI example only: it **does not** process real payments, **does not** automatically provision access, and **does not** collect sensitive payment data.

6. **Editorial boundaries (must be visible in key entry points)**  
   The site must explicitly exclude:  
   - explicit sexual content  
   - illegal how-to content  
   - cheating construction or evasion guides  
   - doxxing or personal accusations  
   Sensitive topics require non-harm framing and appropriate anonymization.

7. **Contact email must be present**  
   Editor contact: **m_turner@163.com**

---

## Tech Stack

- **Astro** (site framework)
- Node.js + npm
- Static assets served from `public/`

If additional UI components are used (Astro/React/etc.), place them under `src/components/` and keep props explicit and auditable (no hidden side effects).

---

## Project Structure

```text
/
├── public/                 # Static assets (images, icons, etc.)
├── src/
│   ├── pages/              # Routes (.astro / .md)
│   ├── components/         # UI components (optional)
│   ├── layouts/            # Shared layouts (optional)
│   └── content/            # Content collections (optional)
└── package.json
````

Astro maps `.astro` / `.md` files in `src/pages/` to routes based on file names. Static assets belong in `public/`.

---

## Local Development

Run commands from the project root:

| Command             | Action                                      |
| ------------------- | ------------------------------------------- |
| `npm install`       | Install dependencies                        |
| `npm run dev`       | Start dev server at `http://localhost:4321` |
| `npm run build`     | Build production site to `./dist/`          |
| `npm run preview`   | Preview the production build locally        |
| `npm run astro ...` | Run Astro CLI (e.g., `astro check`)         |

---

## Deployment — GitHub Pages (Manuel-Turner/DICK)

This repository deploys to GitHub Pages via **GitHub Actions**.

1. In GitHub: `Settings → Pages`
2. Under **Build and deployment**, set **Source** to **GitHub Actions**
3. Push to `main` (or manually run the workflow from the `Actions` tab via `workflow_dispatch`)

Pages URL:

* `https://manuel-turner.github.io/DICK/`

### Astro `site` / `base` configuration

GitHub Pages serves this site under the `/DICK/` subpath. Ensure `astro.config.mjs` includes:

```js
site: "https://manuel-turner.github.io",
base: "/DICK",
```

This is required so built asset paths resolve correctly under the `/DICK/` subpath.

---

## Content Authoring Notes

* **Demo articles:** must display a “DEMO” label and a demo notice; author must be **Cardo**.
* **Non-OA pages:** only metadata + abstract are public; full text must be gated with an explicit notice.
* **Policies/boundaries:** use academic, auditable language; avoid marketing tone; apply non-harm framing and anonymization for sensitive topics.

---

## Contact

Editorial / demo inquiries: **[m_turner@163.com](mailto:m_turner@163.com)**

---

## References

* Astro Docs: [https://docs.astro.build](https://docs.astro.build)
* Astro Community Chat: [https://astro.build/chat](https://astro.build/chat)

```
::contentReference[oaicite:0]{index=0}
```

