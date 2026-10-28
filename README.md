# BuildRight Construction Website

A responsive static website for a construction company, built with HTML, CSS, and vanilla JavaScript.

## Features

- Homepage, services, and contact pages with responsive navigation.
- Construction services overview and contact form.
- Contact name and email saved in the current browser using `localStorage`.
- Homepage chatbot UI and AI-generated About Us and Services content.

## Run locally

From this folder, start a local static web server:

```powershell
python -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000) in a browser. Use a local server rather than opening the files directly so browser storage and same-origin requests work as expected.

The contact form validates the fields, saves the name and email in the browser, and displays a confirmation. It does not transmit submissions.

## Gemini integration

The homepage requests AI responses from the same-origin `/api/gemini` endpoint. A backend proxy must be provided at that route, read the Gemini API key from server-side configuration, and return JSON in this shape:

```json
{ "text": "Generated response text" }
```

Do not put the Gemini API key in the HTML or browser JavaScript. Without a configured backend proxy, generated content and chatbot requests show fallback messages.
