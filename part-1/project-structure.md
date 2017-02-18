Before we delve into the world of Redux, I'd like to briefly cover how the structure of your application can cause issues when your app grows. I'm talking about file structure here and some things to watch out for in your own projects. Be aware that the best structure is highly dependant on the project. If you have something that works and you're happy with, stick with it. You can treat the following section as my opinion, and it's subject to change!

The official Redux examples use a structure similar to this

```
actions/
components/
constants/
containers/
reducers/
```

This is great for small examples and applications. The problem is, if you continue to build your application like this, you might find that it becomes unmaintainable as youl have to sift through an increasingly large number of components, containers, actions and reducers.

```
actions/
components/
    Alert/
    Button/
    Form/
    FormInput,
    Link,
    LoginForm/
    RegisterForm/
    ...
constants/
containers/
    EventAlertContainer/
    LoginFormContainer/
    RegisterFormContainer/
    ...
reducers/
```

You can see in the `components` directory that regular UI components are mixed with page specific components like `LoginForm`. Depending on how strict you are with what classifies as a container, you could combine the presentational components `LoginForm` and `RegisterForm` into their respective containers. On the topic of containers, while I'm not against separating presentational components from their smarter siblings, I don't think you need to explicitly separate them into files under different directories.

```
actions/
components/
    ...
    LoginForm/
        LoginForm.js
        LoginFormContainer.js
    ...
constants/
reducers/
```

## Containers and presentational components are just components

In React Redux apps, there's a common idea of separating container and presentational components. I think it's an important conecpt to know, but I'm not convinced that you need to strictly separate these components into containers or components. They are all just components that are used and combined to render other React components.

If you find yourself creating containers like this, you should really consider why you're creating them at all. Don't just create a container for the sake of it. If it's unikely that you'll need another container that uses the LoginForm component, you could combine them like this:

```
//LoginForm.js

// Export the presentational component as a named export for testing
export class LoginForm extends React.Component {...}

// Write the container code in the same file
const mapStateToProps = state => {};
const mapDispatchToProps = dispatch => {};

// Export the container as default if it is the one you always want to import
export default connect(
    mapStateToProps
    mapDispatchToProps
)(LoginForm);
```

Now the LoginForm directory looks like this

```
...
components/
    ...
    LoginForm/
        LoginForm.js
    ...
...
```

To differentiate between container and presentational components, you can use a naming convention like `LoginFormContainer.js` or `LoginForm.container.js` or `LoginForm.c.js`- Just be consistent.

Even if you have a container component that simply connects a presentational component with state and actions, you can still keep it under the `components` directory

```
...
components/
    ...
    Link/
    FilterLink/
        FilterLink.container.js
```

This is better but our common UI components are still mixed with our app components and this will become messy. An obvious solutions is to group the components by feature.

```
...
components/
    ui/
        Button/
        Link/
        Input/
    app/
        FilterLink/
        LoginForm/
        RegisterForm/
```

Multi-page apps commonly have a component for each page/route.

```
components/
    app/
        FilterLink/
        ProfilePage/
        DashboardPage/
```

Due to the nature of creating React applications, you'll probably have some page specific components as well. Instead of adding these to the `app` directory, let's keep them close to the page where they are used. If they need to be shared with another component in the future, you can always lift them up. Don't import page specific components from other pages, move them to a common area.

```
components/
    app/
        ProfilePage/
            ProfilePage.js
            Avatar/                # Avatar is only used on the Profile Page
                Avatar.js
```

In practice, even though sharing and reusing components is great, often there are small differences that add up to complicating a simple component that is trying to be ultra customisable. There's a balance here. Only reuse or customise a component if it really is the same. Don't complicate things when it might be simpler and more maintainable to create a new component altogether. You might be able to extract some lower level components and reuse them instead. This helps avoid situations like this

`<Avatar src={imgSrc} large noPadding disableHover profile showShadow />`

## Pages

```
src/
    components/
    pages/
        ProfilePage/
        DashboardPage/
```

## Micro apps

```
src/
    App/
    Dashboard/
    
```



