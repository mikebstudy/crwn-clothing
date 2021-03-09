# RouterLearning

### main.RouterSample

### L076.Setup: Setup initial main.RouterSample from L076 React Router Dom

- Created branch from main.Setup
- Cleaned App.css
- Added App.FinalSourceFromSite.js from L76 React Router Dom source provided
- Setup App.js to correspond to beginning of lesson of L76
-  Fixed title in index.html - <title>Crown Clothing - Router Sample</title>
- Setup index.js to wrap App.js in <BrowserRouter> tag

### L076b.NavToSpecificPath: Added Link and Button to demo ways to directly nav to a path location

- Added access to props.match.params.topicId into <TopicDetailPage>
- Added <Link> to <HomePage> to nav to Topics in direct fashion using 'to' attribute
- Added <Button> to <HomePage> to nav to Topics in a dynamic fashion using 'onClick' attribute

### L076c.NavToDynamicallyMatchedPath: Added Link using string match `${props.match.url/Id}` so prior part of url does not matter, just the path/:id part at the end. Allows multiple initial paths to nav to same location

- Added Links to TopicsListPage
      <Link to={`${props.match.url}/13`}>TO TOPIC 13</Link>
      <Link to={`${props.match.url}/17`}>TO TOPIC 17</Link>
      <Link to={`${props.match.url}/21`}>TO TOPIC 21</Link>
- Changed App paths in topics and topics/:id to other paths to prove Links did not care about actual url path prior to topics/:id. So this topics page can be used anywhere in the site if matching prior part is provided (as in this example)
      <Route exact path='/blog/asdqw/topics' component={TopicsList} />
      <Route path='/blog/asdqw/topics/:topicId' component={TopicDetail} />
      <Route exact path='/blog/topics' component={TopicsList} />
      <Route path='/blog/topics/:topicId' component={TopicDetail} />

