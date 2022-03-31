# Beginner Guide For Learning React

based on [egghead](https://egghead.io/courses/the-beginner-s-guide-to-react) courses - The Beginner's Guide to React

## React and ReactDOM

The different between React and ReactDOM is, React is used for creating react element, and ReactDOM is used to render the react element.

### CDN Link

```javascript
<script crossorigin src="https://unpkg.com/react@17/umd/react.production.min.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js"></script>
```

## React createElement

```javascript
const newElement = React.createElement(component, props, ...children)
```

For example :

```javascript
const newElement = React.createElement('div', {
    children: 'Hello World',
    className: 'container'
});
```

The above code will create an HTML `div`, with `text` Hello World, and `class` container

## React Fragment

[A common pattern in React is for a component to return multiple elements. Fragments let you group a list of children without adding extra nodes to the DOM.](https://reactjs.org/docs/fragments.html)

```javascript
const element1 = React.createElement('span', null, 'Hello');
const element2 = React.createElement('span', null, 'World');
const element = React.createElement(React.Fragment, null, element1, ' ', element2);
```

With JSX :

```javascript
const element = (
    <>
        <span>Hello</span> <span>World</span>
    </>
)
```

The above code will render an HTML text `Hello World`;

## Reusable React Component
