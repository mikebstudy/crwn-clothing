# Crown Clothing E-Commerce Project Site

Project site for Complete React Developer Course

## Project Description

- [ ]


## Start Building App - Home Page

### L065a.HelloWorld: Clean and setup initial Hello World state <small>(Refactored out into main.HelloWorld)</small>

- (MB: Hello World seems like a simple starting state to confirm setup is working) 

### L065b.HomePage: Add HomePage basic layout - built without props or state

- (MB: The starting point here is identifying the components and the component structure, without thinking about props or state. It's almost like creating a static html page for layout and control heirarchy.)
- (MB: It's like a pre-step for [Thinking in React: Step 1](https://reactjs.org/docs/thinking-in-react.html#step-1-break-the-ui-into-a-component-hierarchy). That article urges the  [single responsibility principle](https://en.wikipedia.org/wiki/Single-responsibility_principle).)

### L069a.DirectoryStructure: Add directory structure and move components into it

### L069b.HomePageComponents: Refactor HomePage into Directory and MenuItem components

- (MB: Static-like html is refactored into components and the location of data is determined.)
- (MB: The lowest level, MenuItem, is built first and will only contain props passed in. It is created as a const function with arrow sytax. Destructuring of the props is used for coding simplicity.)
- (MB: Next lowest level, Directory, is built to handle the array of MenuItem data. State is used (and hardcoded with values needed that were set in the original static-like html.) The .map function is used on the array in the state to build the MenuItem tags.)

### L069c.MenuItemImage(SnapShot): Add backgroundImage to MenuItem and size dynamically

- (MB: The `style` attribute can be used to add a background image. The `backgroundImage` in the `style` attribute can be set to a js template allowing the image to be setup dynamically by the caller based on a props value. Template is `url(${imageUrl})` and establishes a url call to a dynamic value setup as the image via `imageUrl`. Final code: `style={{backgroundImage: `url(${imageUrl})`}}`)
- (MB: The `className` attribute can be calculated dynamically using a js template. A `size` CSS class can be added to rendering as `${size} menu-item`. If the value of `size` is null, nothing is rendered. Final code: `classNam={`${size} menu-item`}` )

*********************************************************************************
REFACTOR.01 Refactored README.md into separate Setup, Git, Hello World md files

- *(Setup section moved to SetupLearning.md to track and work on as separate subproject)*
- *(Git section moved to GitLearning.md to track and work on as a separate subproject)*
- *(L065a.HelloWorld renamed main.HelloWorld to track and work on as a separate subproject)*

Also, refactored branches as needed into main.subproject branches
Also, added the new Setup and HelloWorld files into appropriate main.subproject branches
- [ ] Also, discovered main.HelloWorld log1 shows more than desired. How to fix?
*********************************************************************************

### L070.MenuItemStyling: Style content box, opacity, fonts, expanding image, hover effect

- Add white background for content box
    + In menu-item.sytles.scss in .content section
    + Add background-color: white;
    + Add opacity: 0.7;
- Setup of Google fonts (Open Sans Condensed)
    + Done in main.setup and merged into L070
    + Added reference to the following to App.css 
        * body { font-family: font-family: 'Open Sans Condensed'; }
    + Note, google recommended: font-family: 'Open Sans Condensed', sans-serif;
- To make h1 titles all uppercase, a javascript function can be used
    + This: <h1 className="title">{title}</h1>
    + Becomes: <h1 className="title">{title.toUpperCase()}</h1>
- Hover effect that increases size of image and Transistion of opacity of content box
    + Very complicated - go back an relisten for detail around 2.5 min
    + Copied final version of lesson 3

### L075.AddRouting: 

