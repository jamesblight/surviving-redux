# Surviving Redux

While this guide focuses on Redux, it also assumes basic knowledge of React

This guide covers the basics of React as well as common techniques used in large applications. By the end, you should have the necessary knowledge to understand and use both with confidence. You should also have move confidence to understand new developments in the world of React.

The content is aimed at newcomers to React, and those interested in learning more about patterns used in non trivial applications. Effort is made to use concrete examples along the way to aid in understanding.

It isn't feasible or necessary to cover every aspect of React application development here. There's plenty of tutorials and articles that cover individual topics in more depth. The aim is to explain the fundamentals and direct the reader to further resources when required.

### Boilerplate projects should be studied, not copied

React boilerplate projects are great. They consolidate common patterns for creating React applications into a single point of reference. Communities form and collaborate to make them better and better. However, you could be wasting your time trying to wrap your head around the boilerplates structure and patterns instead of doing what you want to be doing. Creating your application.

By using a boilerplate without understanding its individual components, you're missing out on the lessons it can teach. Each of the important ideas and patterns behind a good boilerplate exist to solve specific problems. If you don't know what the problems are, then you won't understand the solution. And you won't be able to easily solve similar problems in the future.

Using a boilerplate project blindly might make your life temporarily easier. But it doesn't guarantee that your application will be simpler. You're injecting all the complexity from the boilerplate into your own project and you're taking on all the trade offs the creators of the boilerplate made. The assumed knowledge makes it harder for your future self and new team members to understand your application.

Boilerplate projects exist for a reason, and you can learn a lot by studying them and reading the source. But they are rigid, can easily become obsolete, and rely on the continual support of the maintainers. The React ecosystem moves fast and new boilerplates are just around the corner. In fact, there's so many that you can now search through 100+ Github repos to [find your perfect React starter project.](http://andrewhfarmer.com/starter-project/ "find your perfect React starter project") The thing is, you probably won't find the perfect one because the perfect one would have everything you need and nothing you don't.

Imagine if some of theses projects were created as guides or tutorials instead. You could pick the topic or problem that you wanted to solve, get a good understanding of potential solutions and then implement the right one in your own project with confidence. Yes it might take a bit longer compared to copying a boilerplate and moving on. But you'll have a much simpler, more maintainable codebase that won't bring you to tears in the future.

### Automate your build configuration instead

[Create React App](https://github.com/facebookincubator/create-react-app "Create") is like a boilerplate for your build config, and it's great. If you're starting a new React project I highly recommend checking it out. Rather than dictate how you should build your application, it does all the heavy lifting of setting up your build config instead. It does force some restrictions in return for simplicity, but you can always eject and go your own way if need be. There are other options to choose from when it comes to build config automation, however, Create React App is the most popular and is supported by the React team.



