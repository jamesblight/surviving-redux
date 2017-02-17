Before we delve into the details of Redux, I'd like to briefly cover how the structure of your application can cause issues when your app grows. I'm talking about file structure here and some things to watch out for in your own projects.

The official Redux examples use a structure similar to this

```
actions/
components/
constants/
containers/
reducers/
```

This is great for small examples and applications. The problem is, if you continue to build your application like this, you'll find that it becomes unmaintainable and you'll have to sift through an increasingly large number of components, containers, actions and reducers.

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

You can see in the \`components\` directory that regular UI components are mixed with non-generic components like \`LoginForm\`. Depending on how strict you are with what classifies as a container, you could combine the presentational components \`LoginForm\` and \`RegisterForm\` into their respective containers. On the topic of containers, while I'm not against separating presentational components from their smarter siblings, I don't think you need to explicitly separate them into files under different directories.

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





