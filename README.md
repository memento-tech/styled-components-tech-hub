# Styled Components with React JS

Styled Components is a popular library for React that allows us to write CSS directly inside our components instead of using external CSS files. The beauty of styled-components is that each styled component is unique and scoped to the component itself. This means that if we define a style for a component A (e.g., a <p> tag) and another style for component B (also a <p> tag), the styles will not interfere with each other. However, you can still define global styles to maintain consistency across the entire application.

## Installing Styled Components

To install Styled Components in a React project, open your terminal and run the following command:

```bash
npm install styled-components
```

This will add the necessary dependencies to use styled components in your project.

## Creating Styled Components

There are two primary ways to create styled components:
1. Styling HTML Tags
To create a styled component from an existing HTML tag, follow these steps:
Step 1: Import styled-components
import styled from "styled-components";
Step 2: Define a styled component
```javascript
const StyledParagraph = styled.p`
  color: blue;
  font-size: 18px;
`;
```
Note: The backticks (`) are not apostrophes or single quotes; they are template literals in JavaScript that allow us to define multi-line strings and embed variables.

2. Styling an Existing Component
You can also create a styled component based on an existing React component:
```javascript
const StyledComponent = styled(ComponentToStyle)`
  background-color: lightgray;
  padding: 10px;
`;
```

This approach allows you to extend the styles of an already defined React component.
Improving Developer Experience with Styled Components

## Syntax Highlighting in VS Code

When you first start using styled-components, you might notice that Visual Studio Code does not recognize CSS key-value pairs inside template literals. To fix this, install the vscode-styled-components extension:
```bash
ext install vscode-styled-components
```

This extension provides:
-  Syntax highlighting for JavaScript and TypeScript files.
-  Error reporting for incorrect CSS properties.
-   SS IntelliSense for better code autocompletion.

## Using Props to Customize Styles

Styled components support dynamic styling by passing props to them:

```javascript
const Button = styled.button`
  background-color: ${(props) => (props.primary ? "blue" : "gray")};
  color: white;
  padding: 10px 20px;
`;
```
Usage:

```javascript
<Button primary>Primary Button</Button>
<Button>Default Button</Button>
```

## Global Styles

For defining global styles, use createGlobalStyle from styled-components:
import { createGlobalStyle } from "styled-components";

```javascript
const GlobalStyle = createGlobalStyle`
  body {
    margin: 0;
    font-family: Arial, sans-serif;
  }
`;
```

Then, include it in your main component:

```javascript
function App() {
  return (
    <>
      <GlobalStyle />
      <StyledParagraph>Hello, world!</StyledParagraph>
    </>
  );
}
```

## Theming with Styled Components

Styled Components support theming using the ThemeProvider component:

```javascript
import { ThemeProvider } from "styled-components";

const theme = {
  primaryColor: "blue",
  secondaryColor: "gray",
};

const ThemedButton = styled.button`
  background-color: ${(props) => props.theme.primaryColor};
  color: white;
  padding: 10px 20px;
`;

function App() {
  return (
    <ThemeProvider theme={theme}>
      <ThemedButton>Themed Button</ThemedButton>
    </ThemeProvider>
  );
}
```

## What to Explore Next

To further enhance your knowledge of styled-components, consider exploring:

-  Extending styles: Learn how to inherit styles from another styled component.
-  Animations: Use keyframes to add animations to your components.
-  Styled-components with TypeScript: Learn how to type styled components properly.
-  CSS Grid & Flexbox with styled-components: Structure complex layouts using styled-components.
-  Server-side rendering (SSR) support: Optimize your styled-components for Next.js and other SSR frameworks.

Styled Components provides a powerful and flexible way to style React applications while keeping styles modular and maintainable. Happy coding! 🎨🚀
