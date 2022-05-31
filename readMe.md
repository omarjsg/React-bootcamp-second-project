# Second-react-bootcamp-project

### This project is about styling react components.

### lessons learnt:

1. `Setting dynamic inline styles` which can be altered based on a conditional values, for example"

```html
  <label style={color: !isValid ? 'red' : 'black'}>Course Goal</label>
```

2. `Setting CSS classes dynamically` which allow the classes to be toggled based on conditional values, for example:

```html
<div className={`form-control ${!isValid ? 'invalid' : ''}`}>
```

3. `Using styled components` which allow the styles to be used in certain elements, however, it makes the code in `Js files` packed.

   - To use the styled components we need some steps before:

   1. install `styled-components` package:

   ```
   npm i --save styled-components
   ```

   2. import the styled components:

   ```js
   import styles from "styled-component";
   ```

   3. you can use them now, for example we can style a button by:

   ```js
   const Button = styled.button`
     font: inherit;
     padding: 0.5rem 1.5rem;
     border: 1px solid #8b005d;
     color: white;
     background: #8b005d;
     box-shadow: 0 0 4px rgba(0, 0, 0, 0.26);
     cursor: pointer;
     &:focus {
       outline: none;
     }

     &:hover,
     &:active {
       background: #ac0e77;
       border-color: #ac0e77;
       box-shadow: 0 0 8px rgba(0, 0, 0, 0.26);
     }
   `;
   ```

   - You can notice that we use ` (``) ` to hold the `CSS` code. With this we can gurantee that the styles will apply only on the selected element. We use `&` to apply the styles for the selected element based on other applied conditions such as: sudo-classes, child nodes, ..., etc.

4. `Using styled components dynamically` which some classes properties to be modified based on conditional values. for example:

```js
//In CourseInput.js
<Button type="submit" darkMode={enableDarkMode}>
  Add Goal
</Button>;

//In Button.js
const Button = styled.button`
    color: ${(props) => (props.darkMode ? "4b4b4b" : "#8b005d")}
    }`;
```

5. `Using media queries with styled components` which simply allows the styles based on the enviromental properties of the webpage to thstyled component. for example:

```js
const Button = styled.button`
    width: 100%;
    }
    
    @media (min-width: 600px) {
        width: auto;
        }`;
```
