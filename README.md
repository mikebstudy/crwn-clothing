tt# Crown Clothing E-Commerce Project Site

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

......................
REFACTOR.01 Refactored README.md into separate Setup, Git, Hello World md files

- *(Setup section moved to SetupLearning.md to track and work on as separate subproject)*
- *(Git section moved to GitLearning.md to track and work on as a separate subproject)*
- *(L065a.HelloWorld renamed main.HelloWorld to track and work on as a separate subproject)*

Also, refactored branches as needed into main.subproject branches
Also, added the new Setup and HelloWorld files into appropriate main.subproject branches
- [ ] Also, discovered main.HelloWorld log1 shows more than desired. How to fix?
.......................

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

### L075.AddRouting: Add Switch and Route tags from react-router-dom and sample hats page in App

- react-router-dom added through main.Setup branch
- In index.js nest <App> inside <BrowserRouter> (from react-router-dom)
- In App.js, routing setup
    - Add Route from react-router-dom
    - Add sample const HatsPage function for testing
    - Use Route tag to point to HomePage with path='/'
    - Add Route tag to point to HatsPage with path='/hats'
    - Tested
- In Appjs, switch control of routing setup
    - Add <Switch> from react-router-dom
    - Nest the <Route> tags within the <Switch> tag

### L076: Add main.RouterSample to capture explination example of Routing 

- Created main.RouterSample branch from main.Setup
- Coded along in L076 and created some commits 

### L077.MenuItemNavLinks: Use withRouter and Routing Props to create Nav Links in MenuItem

- <Route> only passes the routing props into the child component in the component attribute
    + So the routing props are not available beyond that child if not explicitly passed down through other child components
        * Some of which will have no interest
        * Pattern called prop drilling and considered a bad pattern
- withRouter component offers a alternate solution to the prop drilling approach
    + Is a first order component, so it can be made an enclouser for any component
        * Thus making the routing props available at any level 
        * Is a function that takes a component as an argument and returns a modified version of that component that provides the routing props
    + ex. export default withRouter(MenuItem); to wrap it 
- Adding withRouter to MenuItem logic
- Added linkUrl to 'section' state data which exists in Directory component
    + Directory component is what calls MenuItem
- In MenuItem, started to add `onClick={() => history.push()}`
- Also modified code to use a spread parameter to pass in all the 'section' state data as a single argument rather than name value pairs from the 'section' state
    + This is simplification based on the observation that all the values passed into MenuItem have the same name,value pairs as exists in the 'section' state array entries
    + So, this:
```    
            this.state.sections.map(({ title, imageUrl, id, size }) => (
                <MenuItem key={id} title={title} imageUrl={imageUrl} size={size} />
```    
    + Becomes:
```
            this.state.sections.map(({ id, ...otherSectionProps }) => (
                <MenuItem key={id} {...otherSectionProps} />
```
    + Due to the json data looking like this:
```
        [    {
                title: 'mens',
                imageUrl: 'https://i.ibb.co/R70vBrQ/men.png',
                size: 'large',
                id: 5,
                linkUrl: 'shop/mens'
            }, 
            ...
        ]
```
- Continuing in MenuItem, the onClick is modified to provide a location path to go to the proper page
    + onClick={() => history.push(`${match.url}${linkUrl}`)}
        * The `match.url` provides all the leading url part to get to the proper place in the url hierarchy
        * The linkUrl is the actual path part to be matched
        * So this is an example of having a component that is rendering a url that is independent of its location in the url path structure.
        * ie /someMatchedUrl/linkUrl
    
    
