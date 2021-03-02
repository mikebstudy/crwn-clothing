# SetupLearning

### Intention

- Intended to capture the setup for the project to use as a starting point for another project or experimental copies of this project
- Realized it might be possible by creating a main.setup branch with this in it
    + Still need to prove out the concept
- Also intended for notes on fixup and learning about setup fixups to make things work

### (From Original README.md)

A01.Setup: Run npx create-react-app, then start Readme
- Add repo to GitHub
- Create folder for project ie `crwn-clothing`
- cd into folder
- `git clone <SSH URL> .` (causes clone into current folder)
    + adds git with single `Initial commit` 
        * Apparently using author from github site and name and email
- `npx create-react-app .` (to create in current folder)
    + when done in this sequence, there is no extra git commit created by npx

A01.Setup: Add sass

- `yarn add node-sass`

### main.Setup

- Create and start SetupLearning.md
- Rename A01.Setup to main.Setup

### Add Google Fonts - Open Sans Condensed

- Google fonts link added to public/index.html
    + <link rel="preconnect" href="https://fonts.gstatic.com">
    + <link href="https://fonts.googleapis.com/css2?family=Open+Sans+Condensed:ital,wght@0,300;0,700;1,300&display=swap" rel="stylesheet">
    + CSS rules: font-family: 'Open Sans Condensed', sans-serif;
- However, a local copy also kept and not used, so that experimental versions could use local copy
- Downloaded Open_Sans_Condensed.zip to have a local copy of the fonts
- Added OpenSansCondensed (-Bold,-Light,-LightItalic) fonts to public/GoogleFonts

### Update Packages - See L073

- L073: Updating Packages + Lastest Version of React
    + Explains how to do the update
    + [ ] Watch and extract info sometimes

### Resolve Package update issue - See L066

- L066: Project Files + Modules
    + Explains various files, structure and modules
    + Also explains update issue solved with resolution (or resolve) attribute in package.json (I think)

### Add react-router-dom

- L075: Routing In Our Project
- yarn add react-router-dom
