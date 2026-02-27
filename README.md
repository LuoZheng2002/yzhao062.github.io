# How to Update Your Info on the FORTIS Lab Page

This repository hosts the source code for the [FORTIS Lab webpage](https://viterbi-web.usc.edu/~yzhao010/lab.html).

Member sections are now data-driven.
Please update JSON files instead of editing `lab.html` directly.

## Files You Should Edit

- `data/lab-current-phd.json` for current Ph.D. students
- `data/lab-members.json` for current Master/Undergrad members and all past members

## Standard Workflow

1. **Fork and clone**
   - Fork this repository on GitHub.
   - Clone your fork locally.

2. **Add your photo**
   - Put your image under `images/others/`.
   - Use a square image when possible.
   - Prefer `.webp` format.
   - Example: `images/others/your_name.webp`

3. **Update the correct JSON file**
   - Do **not** manually edit member cards in `lab.html`.
   - Add or update your entry in the relevant data file.

4. **Preview locally**
   - Open `lab.html` in a browser (or use a local server in PyCharm) and verify your card.

5. **Keep commit clean**
   - Do not include unrelated local files (for example `.DS_Store`, `.idea/*.xml`).

6. **Commit, push, and open PR**
   - Commit your changes, push to your fork, and submit a pull request.

## JSON Examples

### A. Current Ph.D. student (`data/lab-current-phd.json`)

```json
{
  "name": "Jane Doe",
  "profile_url": "https://example.com",
  "image": "images/others/jane_doe.webp",
  "alt": "Jane Doe",
  "year_info": "1st year, Joined Fortis in Aug 2026",
  "research": "LLM Safety, Robustness",
  "awards": ["Example Fellowship"],
  "email": "janedoe@usc.edu",
  "co_advised_by": {
    "name": "Prof. X",
    "url": "https://example.com/prof-x"
  }
}
```

`awards` and `co_advised_by` are optional.

### B. Current Master/Undergrad (`data/lab-members.json`)

```json
{
  "group": "current",
  "name": "Jane Doe",
  "profile_url": "https://example.com",
  "image": "images/others/jane_doe.webp",
  "alt": "Jane Doe",
  "research": "Multimodal / Generative AI",
  "status_text": "Master Student",
  "email": "janedoe@usc.edu",
  "awards": ["Example Fellowship"],
  "publications": [
    "Paper title, Venue 2026"
  ]
}
```

`awards` and `publications` are optional.

### C. Past member (`data/lab-members.json`)

```json
{
  "group": "past",
  "name": "Jane Doe",
  "profile_url": "https://example.com",
  "status_text": "Master Student → Now Ph.D. Student at XYZ",
  "email": "janedoe@xyz.edu",
  "publications": [
    "Paper title, Venue 2026"
  ]
}
```

## Moving Someone from Current to Past

When a current Master/Undergrad member graduates:

1. Open `data/lab-members.json`
2. Find that member's object
3. Change:
   - `"group": "current"` → `"group": "past"`
4. Optionally update `status_text` and `email`

That single field change (`group`) moves the member from the Current section to Past Members automatically.
