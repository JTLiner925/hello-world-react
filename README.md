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
