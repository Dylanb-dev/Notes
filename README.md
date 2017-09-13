# Learning guide for React and javascript


## Getting Started

[Install MS Visual Studio](https://code.visualstudio.com/download) it has minimal config and great performance.

- [Great introduction video](https://www.youtube.com/watch?v=7OussBP55lg)

### OPTIONAL - Install [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

My Editor settings after installing these packages (using atom keybindings)
```json
{
  "editor.tabSize": 2,
  "prettier.eslintIntegration": true,
  "eslint.autoFixOnSave": true,
  "prettier.semi": false,
  "window.zoomLevel": 1,
  "editor.formatOnSave": true,
  "javascript.format.enable": false,
  "atomKeymap.promptV3Features": true,
  "editor.multiCursorModifier": "ctrlCmd",
  "editor.formatOnPaste": true,
  "editor.renderWhitespace": "none"
}
```

Now you should be able to use the editor format shortcut to get amazing formatting instantly BAM!

# 1. Modern javascript and React

- Learn Javascript and basic es5/es6 syntax
http://es6-features.org/ [[REPL/DEMO](https://babeljs.io/repl/)]
- Learn [Basic React](https://medium.freecodecamp.org/all-the-fundamental-react-js-concepts-jammed-into-this-single-medium-article-c83f9b53eac2)
- Install [Create react app](https://github.com/facebookincubator/create-react-app) and read the guide (yes its long)
- Understand Promises with this [article by eric elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-promise-27fc71e77261)
- Use styled components as much as possible e.g
```jsx
const FlexCentre = ({ children }) => 
  <div style={{ display: 'flex', justifyContent: 'center' }}>{children}</div>
```
OR
```jsx
const FlexCentre = ({ children }) => 
  <div className="FlexCentre">{children}</div>
```
with 
```css
.FlexCentre {
  display: flex;
  justifyContent: center;
}
```
- Use stateless components as much as possible e.g
```jsx
const Button = ({ onClick, name }) => 
  <button onClick={onClick}>{name}</button>
```
- Use proptypes whenever possible e.g
```jsx
const ListOfNumbers = props => (
  <ol className={props.className}>
    {
      props.numbers.map(number => (
        <li>{number}</li>)
      )
    }
  </ol>
);

ListOfNumbers.propTypes = {
  className: React.PropTypes.string.isRequired,
  numbers: React.PropTypes.arrayOf(React.PropTypes.number)
};
```

### Optional
- Learn react from a lower level
[React Armory](https://reactarmory.com/)
- Learn basic routing with [react-mini-router](https://github.com/larrymyers/react-mini-router)(URL based) or similar.

# 2. More Javascript, testing and tooling for react

- Understand functional patterns that are everywhere in react and modern javscript with the 
[FunFunFunction video series](https://www.youtube.com/watch?v=BMUiFMZr7vk) (watch the whole series)
- Learn [Jest Test Framework](https://facebook.github.io/jest/)(Comes built into create react app) [[REPL/DEMO](https://repl.it/languages/jest)] TIP: Use smoke test for all stateless/functional/presentational components and Jest snapshots for containers/class/state components.
- Learn [Redux](http://redux.js.org/) and watch the [fantastic video series](https://egghead.io/courses/getting-started-with-redux)
- Learn advanced routing with either [React-router v4](https://reacttraining.com/react-router/)(component based), [redux-first-router](https://github.com/faceyspacey/redux-first-router)(redux based)


### Optional
- Learn how closures work [Closures by Eric Elliott](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36)
- Explore functional and fundamental javascript concepts with Eric Elliot
[Functional Javascript by Eric Elliott](https://medium.com/javascript-scene/the-rise-and-fall-and-rise-of-functional-programming-composable-software-c2d91b424c8c) (the whole series is great)

# 3. Emerging trends and advanced tooling

- Understand advanced functional patterns that influence emerging techniques in javascript and react.
[Frisby composable javascript course](https://egghead.io/courses/professor-frisby-introduces-composable-functional-javascript) (you dont need to finish this, check the code if you are confident)
- Learn [Flow](https://flow.org/) [[REPL/DEMO](https://flow.org/try/)]
- Learn how to apply [Recompose](https://github.com/acdlite/recompose) and write functional UI [Example](https://github.com/jxnblk/rebass)

### Optional
- Explore styled component library for better css management
- Check out rxjs

## Resources

Great libraries worth a look

- Lodash and lodash/Fp
- date-fns
- Rambda
- FairyTale (Task)
