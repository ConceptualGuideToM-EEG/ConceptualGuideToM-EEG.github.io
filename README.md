# Companion tools for the M/EEG Conceptual Guide: front door

This repository is the permanent public address (the "front door") for the chatbots that accompany the book.
It only contains static pages. The chatbots themselves run elsewhere, so they can be moved without changing any printed link.

## Structure

| Path | Purpose |
|---|---|
| `index.html` | Landing page with links to the two tools and the "good to know" notes |
| `student/index.html` | Forwards to the student tutor (address set in `config.js`) |
| `lecturer/index.html` | Forwards to the lecturer tools (address set in `config.js`) |
| `privacy.html` | Privacy notice (template: adjust to the final setup) |
| `config.js` | The only file to edit when a chatbot moves |
| `style.css` | Shared styling |

Public addresses (never rename the organization or this repository once they are printed):

- Home: `https://conceptualguidetom-eeg.github.io/`
- Student tutor: `https://conceptualguidetom-eeg.github.io/student/`
- Lecturer tools: `https://conceptualguidetom-eeg.github.io/lecturer/`

## When the chatbot moves

Edit `config.js`, put the new `https://` address between the quotes, and commit to `main`.
The site updates within a minute or two.

## Before publishing

1. Replace every `[[...]]` placeholder. To list them: `grep -rn "\[\[" .`
2. Make `privacy.html` describe exactly what the final system does, and have the University of Cyprus data protection officer read it.
3. In GitHub: Settings → Pages → deploy from the `main` branch; tick "Enforce HTTPS".

## Rules for this repository

- It is public. Never commit API keys, access codes, persona instructions, rubrics, or the book summaries/index used by the chatbot. Keep those on the server side of the chatbot.
- Two-factor authentication on for every owner, and at least two owners in the organization.
- Do not rename the organization or this repository after the address has been printed.

## Preview locally

```
python3 -m http.server 8000
```

Then open http://localhost:8000
