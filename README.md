Creating two global variables to use in our script:
React
ReactDOM
We need both in order for the library to be available.
We need the react-dom.development.js for webpages.

        A React node is defined as:
        a light, stateless, immutable, virtual representation
        of a DOM node.


    <script src="https://unpkg.com/react@16/umd/react.development.js"></script>

    <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>

      Our code will go here
      We've used the querySelector method on the
      global document object in JavaScript to select
      the #application-root element in the page.
      appRoot is a DOM object

      const appRoot = document.querySelector("#application-root");

      ReactDOM.render(element, container);
        ReactDOM.render('Hello, world!', appRoot);
      ReactDOM.render('<h1>Hello, world!</h1>', appRoot);
      This doesn't work, because it's writing the
      characters to the page instead of converting them into HTML.

      React.createElement(type, props, children)
      const helloWorldH1 = React.createElement("h1", null, "Hello, world!");

      Whenever we use 'createElement' we are creating
      an instance of some element.
      We'll discuss instances soon.
      ReactDOM.render(helloWorldH1, appRoot);
      
      JSX is a convenient syntax for React developers because it's quick to write, visually distinct from non-JSX JavaScript, and familiar to read. 

      Having to write React.createElement()can become tedious 

<body>
  <div id="application-root"></div>

<script
  src="https://unpkg.com/react@16/umd/react.development.js">
</script>
<script
  src="https://unpkg.com/react-dom@16/umd/react-dom.development.js">
</script>
<script
  src="https://unpkg.com/babel-standalone@6/babel.min.js">
</script>

<script type="text/babel">
  ReactDOM.render(
    <div>
      <h1>Hello, world!</h1>
      <p>How are you today?</p>
      <h2>Look what React can do!</h2>
    </div>,
    document.querySelector('#application-root')
  );
</script>
</body>

We're creating elements and inserting them all into the page inside a <div>. Notice that the JSX isn't inside strings; no quotes or backticks.

<!-- // With Babel and JSX
<div>
  <h1>Hello, world!</h1>
  <p>How are you today?</p>
  <h2>Look what React can do!</h2>
</div>

// Without JSX
React.createElement('div', null, [
  React.createElement('h1', null, 'Hello, world!'),
  React.createElement('p', null, 'How are you today?'),
  React.createElement('h2', null, 'Look what react can do!')
]) -->

The first argument (our app) is like the trunk of the tree. The elements and strings of text inside our app are the branches.
const App = <div>
  <h1>Hello, world!</h1>
  <p>How are you today?</p>
  <h2>Look what React can do!</h2>
</div>
We call this App variable a component. Components have an important role in React; they are the branches of our tree. 

You can also write it as a function 
Now we can make the function return JSX with div, h1, p, and a ul elements.

function App() {
  return (
    <div>
      <h1>Hello, everyone!</h1>
      <p>We think</p>
      <ul>
        <li>React</li>
        <li>is</li>
        <li>brilliant!</li>
      </ul>
    </div>
  );
};

// Use the App component:
// insert the App's element tree into the #application-root
ReactDOM.render(
  <App />,
  document.querySelector('#application-root')
);

What is React?
React is a library for building JavaScript applications that is designed for speed, simplicity, and scalability.
fits with the best practice of "separation of concerns" (SOC) 

It's important to understand that props aren't HTML attributes, even though many of the names are similar. One difference becomes clear when we want to add a class to an element for CSS styling. If we are going to add a class attribute to the output HTML, we need to use the prop className.

We pass props into components in the same way we pass arguments into functions.

//   We add props for whatever we need, the same way we add arguments to a function. Everything we add gets put inside the props object.
// Take a look at this code with arbitrary props added to App.
  foo='bar'
    boolProp={false}
    numberProp={123}
    objectProp={{ baz: 'buzz' }}
    arrayProp={[ '3', '2', '1' ]}>
    //notice that we had to use curly braces for 
    //all of the values except for the strings.

    Glossary

Compiler: A tool that takes JavaScript code and transforms it to new JavaScript code, such as Babel.
CDN: content delivery network to serve files across the globe in an optimized manner, such as the react.development.js file.
JSX: A syntactical sugar for JavaScript similar to HTML to help write UI code.
Element: A building block in React, the output from writing a tag in JSX.
Component: A reusable piece of code to create elements.
Props: The inputs or arguments to a React component. Similar to HTML element attributes.
props.children: A special prop containing embedded elements.