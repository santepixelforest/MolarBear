# MolarBear — complete website source (version 4)

Exported September 24, 2026. This is the latest published illustrated website:
https://molarbear-care-journey.ishan-3196.chatgpt.site

Commit: b10300bc05b63b2dd2f0120876190da50c59fd4d

## Included

- `dist/index.html`: complete landing page, CSS and JavaScript.
- `dist/patient-journey/index.html`: separate illustrated patient journey with
  clickable milestones, questions, message/call examples, self-assessment and ROI calculator.
- `dist/assets/care-journey.jpg`: the original AI-generated illustration used on both pages.
- `.openai/hosting.json`: original hosting configuration, not needed for other hosts.

All styles and scripts are inline in the HTML. Favicons are embedded SVG data URLs.
There are no external JavaScript libraries, downloaded fonts, package dependencies,
build tools, backend services or database requirements in this version. Nothing
needs to be installed through npm. All website assets are included.

## Run locally

Extract the ZIP, open a terminal in the `MolarBear-Website` folder, and run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1 --directory dist
```

On Windows with Python installed:

```powershell
py -m http.server 8000 --bind 127.0.0.1 --directory dist
```

Open http://localhost:8000/ or http://localhost:8000/patient-journey/.
Press Ctrl+C to stop. This server is for local development, not public hosting.
Use a local HTTP server rather than double-clicking HTML: navigation and image paths
are relative to the web root.

## Host elsewhere

Upload the CONTENTS of `dist/` to the root of any static web host. Keep `assets/`
and `patient-journey/` alongside `index.html`. If asked for an output or publish
directory, choose `dist`; no build command is required.

Enable normal directory index serving so `/patient-journey/` serves
`patient-journey/index.html`. Do not use a single-page-app fallback that sends
all routes to the landing page. Use HTTPS for a public site.

The site uses root-relative URLs such as `/assets/care-journey.jpg`. Hosting under
a subdirectory instead of the domain root requires updating these paths and the
navigation links in both HTML files. The existing ChatGPT domain and access controls
are not transferred by this ZIP. Do not upload the README or hosting configuration
to your public web root; only the `dist/` contents are needed.

## Editing

Edit the two HTML files directly: `<style>` elements contain CSS and `<script>`
elements contain behaviour. Replace `dist/assets/care-journey.jpg` to change the
illustration. The four milestones and conversation examples are in the `stages`
array in the patient journey page. This is a static source-code project, not a
native drag-and-drop editor project.

## Current limitations

- Landing-page survey and booking destinations remain “coming soon.”
- The patient journey's self-assessment runs locally in the browser. It does not
  send responses, save patient data or email a report.
- The audit button opens an informational dialog; no booking is made.
- ROI calculations are illustrative scenarios, not promised results or quoted prices.
- Message and call examples are demonstrations, not a live communication platform.
- Research links require internet access. The website itself needs no remote assets.

Before a public launch, connect real survey/booking services and review service
availability claims, research references and privacy/consent requirements.

The tracked published source is included without modification. Git history,
credentials, hosting tokens and unrelated files are not included. Exporting this
ZIP does not alter the live website.
