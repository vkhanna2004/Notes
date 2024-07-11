# Video-2

two ways to initialize a react project \
        1. create-react-app - COOL DUDE \
        2. vite (vite is a bundler) - MILITARY \
**Bundler** : is a tool that takes multiple disparate files, such as JavaScript, CSS, and images, and combines them into a single, optimized package that can be served to the browser.

# Video-3

we understand the file structure in both
 ->using 1 test libraries and some extra libraries are also installed. 
 while,using 2 only two libraries are installed - "react","react-dom" without additional dependencies

 -> react-script library is installed in 1 ,so <script></script> tag is not used.
 while in 2 <script></script> tag is used.

->in 1, component files can be .js or .jsx
but in 2,react-component files must be .jsx

->in react, by convention 
when we return html tag - use .jsx
when we don't return html tag - use .js 

->in 2, tag name/component ( i.e. App,Chai) **must start with an uppercase letter**.

->all the tags must be enclosed in a single tag .<></> this is called **"fragment"**

# Video-4

we tried to understand how react works and tried to create our own custom react app

1.When we create a component in react using createElement () then, by default **babel**(Transpiler) will inject a element React.

2.Evaluated Expression

app.jsx or any other react component is just a function.
react converts these react components into tree structure and inject it.

behind the scene, react element is converted into object which has \
-type of element <a\>,<p\>,<h1\>,etc \
-properties \
-children 

# Video-5

## Hooks

**-React controls UI** \
suppose we have a variable counter which is being incremented and decremented. we are showing this counter value in multiple divs.and now we have to update its value.
so if we have to do this we need to select each div and update it.
react makes it simple and easy!

let [counter, setCounter]  = useState(15)
let [variable, setVariable]  = useState(initial value)

# Video no. 6 
- virtual dom, reconcilation and fibre
visit - [https://github.com/acdlite/react-fiber-architecture]

# video no 6

visit - [https://github.com/acdlite/react-fiber-architecture] \
1.The createRoot create's its own DOM and then compare it with the web browser's DOM and only update those components which are actually updated.

2.But the browser removes the whole DOM and then recrates the whole DOM with the updated values this is called reload. 

3.However virtual DOM tracks whole DOM like a tree like structure and updates only those values which were only changed. 

4.But some values depends on network call so if we update a value it might get update immediately via a network call.

5.So we will have to update it again. To avoid this overhead we can drop the updation calls for the immediate value update.

6.The current algo used by the React is called the React Fibre algo.

7.The algo react uses to differentiate the web browser's tree and React's tree formed through create root is called reconciliation.

8.Reconciliation is the algo behind what popularly known as the Virtual-DOM.

9.In UI it is not necessary for every update to be applied immediately. 

# video no 7

**React props** -: to send data from one component to another.

Props are sent inside the component brackets. \
eg. `<Card channel = "chaiaurcode">`

1. Always use curly brackets for a variable { variableName } to send it as props.
Props can be in any form but passed as a variable.
eg. `<Card username = "chaiaurcode"/> `
eg. `<Card object = "myobject"/> `
eg.` <Card array = "myarray"/>` 

2. props send the data in the object form to the component.
so to access -> \
                   props.properties or {properties ="defaultValue if props doesn't receive any value"}
                   eg.props.username

# Video-9-10

Imagine hooks in React like little helpers you can call on in your code. These helpers let you add features to regular function components that were previously only possible with more complex class components.

## hooks-SUPERPOWERS

1. **UseState Hook** :
The React useState Hook allows us to track state in a function component. \
State generally refers to data or properties that need to be tracking in an application. \
useState accepts an initial state and returns two values:
*  The current state.
*  A function that updates the state.

2. **useEffect Hook** :
 The useEffect Hook allows you to perform side effects in your components. \
 Side effects are operations that interact with the outside world\
Some examples of side effects are: fetching data, directly updating the DOM, and timers. \
useEffect accepts two arguments. .
`useEffect(<function>, <dependency>)` \
Runs on the first render and any time any dependency value changes

3. **useRef** :
The useRef Hook allows you to persist values between renders. \
It can be used to store a mutable value that does not cause a re-render when updated. \
It can be used to access a DOM element directly. \
In React applications, when the state of a component or its props change, React automatically re-evaluates the component and its children. This process is called a **re-render**. 

During a re-render, React: \
* 1. Calls the component function: This   creates a new virtual DOM (a lightweight   representation of the UI). 
* 2. Compares the virtual DOM with the    previous one: React identifies differences  between the old and new virtual DOMs.

* 3. Updates the real DOM

4. **useCallback**:
The React useCallback Hook returns a memoized callback function.

hook in React is a performance optimization mechanism that helps prevent unnecessary re-renders of child components when their parent component re-renders.

Think of memoization as caching a value so that it does not need to be recalculated.

This allows us to isolate resource intensive functions so that they will not automatically run on every render. \
The useCallback Hook only runs when one of its dependencies update. This can improve performance.

->The **useCallback** and **useMemo** Hooks are similar. The main difference is that useMemo returns a memoized value and useCallback returns a memoized function.

# Video-12

## React Router

anchor tag or <a\> tag is not used in React as it refreshes the whole page which is not the concept of react, that's why Link tag is used in react which is imported from react-router-dom.

### Link

**Purpose**: Used for creating navigational links within a React single-page application (SPA). \
**Behavior:** Renders an accessible <a\> element with a href attribute that points to the target route. \ 

Clicking the link triggers a client-side navigation, preventing the entire page from reloading. This enhances user experience and performance in SPAs. \

**props**-to (required): The path or URL of the route to navigate to.


React also provides **NavLink** with some additional features like highlighting the active nav page. \

**NavLink** is a specialized version of Link that provides additional features for navigation menus, breadcrumbs, or other UI elements where highlighting the active link is desirable. \
**props**- isActive

# Video-13
### Context API

The Context API in React provides a way to pass data through the component tree without having to pass props down manually at every level. \
**redux** is for state management \
react-redux \
redux-toolkit : simpler version of redux \

assume context as a global variable.each context is provider(variable provider), so we have to make a provider.

# Video-14
### Context API with local storage

`let lastname = localStorage.getItem(key)`
`localStorage.setItem(key, value);`

remove data from local storage
`localStorage.removeItem(key);`

clear local storage
`localStorage.clear();`

in this the data is in string format so we have to convert it into JSON when required.\
The localStorage object allows you to save key value pairs in the browser.\

Note\
The localStorage object stores data with no expiration date.\

The data is not deleted when the browser is closed, and are available for future sessions.\

# Video-15
### Redux Toolkit

**Never Mutate your state** or **never modify your state** \
Redux is an independent state management library. To use redux in react "react-redux" is used.\
redux: core library \
react-redux : react implementation of redux

**Centralized Store:**  Redux creates a single place to hold all the application's state. This makes it easier to access and update the state from any part of your application.

**Predictable Updates:** Redux follows strict rules for how the state can be changed.  Think of it like having a specific process to follow when adding or removing items from the vault. This predictability makes it easier to understand how your app behaves and to fix any issues.

**Clear Communication:**  Components in your application can't directly change the state in the vault. Instead, they send messages (called "actions") describing what needs to happen.  The vault then uses these messages to update itself following the set rules.

Overall, Redux helps keep your application's state organized, predictable, and easier to manage, especially in complex applications. \

**slices :** reducers are called slices in redux toolkit
**what is reducer?** Functionality

**useDispatch:** uses reducer to do changes in the store.

**useSelector:**

# Mega Blog Project

**.env** - environment variables
to access enviroment variables in 
- create react app 
        process.env.REACT_APP_APPWRITE_URL
- vite app
        import.meta.env.VITE_APPWRITE_URL

add .env file in gitignore

**conf.js**
- create a "conf" folder and conf.js in it . just create an object and add keyvalue pairs to acess env variables.
- this is production grade approach .

**Vendor login** 
- writing code in such a manner that it is easy to change "authentication system/service " .
for example, we want to replace appwrite with any other service, then there should not be much problem. we can make changes in the functions in auth.js file
- service class is created

**Container**: container is used for styling purpose .it is simply a container i.e. something is above and below it. we just define classname /styling properties here.

## Video no. 24
### RTE
- Controller: This component simplifies working with form data in React applications. It handles two-way binding between the form state and the RTE component.
- control : to pass on the control of this RTE component to form(or whoever calls RTE)
- plugins: An array of strings specifying the plugins to be loaded. Here, we're enabling plugins for image insertion, advanced lists, autolinking, basic formatting, link management, character maps, content preview, anchors, search and replace, visual blocks, code editing, full-screen mode, date and time insertion, media management, tables, code highlighting, help, and word count.
- toolbar: Defines the toolbar layout, specifying the available buttons and their arrangement.
- content_style: Sets the default CSS styles for the content within the RTE, such as font family and size.
- onEditorChange: This prop is set to the onChange function provided by Controller. It ensures that any changes made to the RTE content are reflected in the form state.

### PostForm
- The post prop will likely be used for editing an existing post or creating a new one.
- watch: Function for watching specific form fields for changes and performing actions based on those changes.
- setValue: Function for programmatically setting the value of a specific form field.
- control: This object provides access to form state and validation within the RTE component.
- getValues: Function for retrieving the current values of all form fields.


-init = auth.js
-getting preview before posting
-
