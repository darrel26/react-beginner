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

## React PropTypes

to check/validate react components

for example, there is a `SayHello` component with `firstName` and `lastName` as it props. To make sure the props is rendered with the right data types you can check it by using `PropTypes`

```javascript
// ...
SayHello.propTypes = {
    firstName(props, propName, componentName) {
        if(typeof props[propName] !== 'String') {
            return null;
        }
    }
}
```

the above code is to make sure that `propName` has `String` types

> **_NOTE_** : to use propTypes you need to import the CDN links or install it using npm
>
> PropTypes are not required, so make sure if you want it to be required just add `PropTypes.isRequired`

## Interpolation

in _Interpolation_ you can't use `if / for loop / etc.` you can only use the javascrript expressions like `ternary`

in React element

```javascript
<div> // JSX
    {`The ${text} is `} // JS 
    {text.length ? <strong>{text.length}</strong> : 'Null'} // JS -> JSX -> JS -> JS
    {' characters'} // JS
</div>
```
