# Mahad Hassan Shire — Portfolio & CV

Dark, 3D-interactive portfolio + matching CV for **Mahad Hassan Shire**
(Computer Science student, Networking Security — Jamhuriya University, Mogadishu, Somalia).

## Files
- `index.html` — the complete portfolio (single file, no build step)
- `assets/badge.png` — Junior Developer ID badge (used hanging in Hero + in About)
- `assets/certificate-successwise.png` / `.pdf` — SuccessWise.ai 28-Day AI Challenge certificate
- `assets/Mahad-Hassan-Shire-CV.pdf` — CV (linked from "Download CV" buttons)
- `cv/cv.html` — editable source of the CV
- `cv/Mahad-Hassan-Shire-CV.pdf` — CV output

## Real content already in place
- Name, location, status (Open to internships)
- Email: mahadhassanshire@gmail.com · WhatsApp: +252 61 073 9015
- GitHub, LinkedIn, Instagram links
- Education: Jamhuriya University (2025–Present, 3rd semester, CS — Networking Security),
  Imamu Malik School (graduated), Uhud Primary & Secondary School
- Projects: Somali Business Alliance (live), Shirkada Tech, Responsive Web Design
- Certificate: SuccessWise.ai — 28-Day AI Challenge, 13 Aug 2026, SW-2026-5G4TMQ
- Stats: 5+ projects, 1 certificate, 3rd semester, learning since 2025
- Tech Stack tab: honest "currently learning" list (no fake percentages)
- Experience section removed (no work experience yet)

## Edit the CV
Change text in `cv/cv.html`, then regenerate:
```
pip install weasyprint
cd cv && python3 -c "from weasyprint import HTML; HTML('cv.html').write_pdf('Mahad-Hassan-Shire-CV.pdf')"
cp Mahad-Hassan-Shire-CV.pdf ../assets/
```

## Publish on mahadhassan.com
1. Netlify: drag the folder onto app.netlify.com → add domain in Domain management
2. Vercel: New Project → upload folder → add domain
3. GitHub Pages: push to a repo → Settings → Pages → main branch

## Forms & comments (configuration)
Two JS variables at the bottom of `index.html` control how forms deliver:

1. `CONTACT_ENDPOINT` (in the CONTACT FORM script)
   - Empty = the "Send message" button opens the visitor's email app with the message pre-filled.
   - Set it to a form service (e.g. `https://formspree.io/f/xxxxxxx` or Web3Forms) to deliver messages in-page without leaving the site.

2. `COMMENTS_API` (in the COMMENTS script)
   - Empty = "preview mode": comments save in the visitor's own browser only (not public).
   - Set it to a JSON API (Supabase / Firebase / any REST endpoint) to publish comments for everyone.
     GET  -> [{name, comment, photo, createdAt}]
     POST {name, comment, photo} -> {ok:true}
