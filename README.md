# Surviving Redux

If you're like me, when you first started learning Redux, once you got past the initial learning curve, you had some "aha" moments where you really understood it and it felt great. You started to see your future. It's covered in reducers and there's an action for everything. At any moment you can see exactly what's happening. You can pause, rewind and replay time. You're in control. Until your app grows. Then you wonder why simple changes require so much effort. You're trying to remember why you created so many action creators, and why they exist at all. Weren't they meant to reduce boilerplate?

The purpose of this guide is to try and solve some of the issues I've encountered when creating applications with React and Redux. In the first part, I'll go over these issues and try to come up with solutions. In part 2 I'll create an application while following the new rules and patterns from part 1 to see if they are helping in practice. Let's see how it goes.

While this guide focuses on Redux, it assumes basic knowledge of Redux and React. If you're using something other than React for your UI then you should still be able to follow along. If you are using React then it's a good idea to get a solid understanding of all the features it provides before moving on to Redux.

#### But first...

### Boilerplate projects should be studied, not copied

React boilerplate projects are great. They consolidate common patterns for creating React applications into a single point of reference. Communities form and collaborate to make them better and better. However, you could be wasting your time trying to wrap your head around the boilerplates structure and patterns instead of doing what you want to be doing. Creating your application.

By using a boilerplate without understanding its individual components, you're missing out on the lessons it can teach. Each of the important ideas and patterns behind a good boilerplate exist to solve specific problems. If you don't know what the problems are, then you won't understand the solution. And you won't be able to easily solve similar problems in the future.

Using a boilerplate project blindly might make your life temporarily easier. But it doesn't guarantee that your application will be simpler. You're injecting all the complexity from the boilerplate into your own project and you're taking on all the trade offs the creators of the boilerplate made. The assumed knowledge makes it harder for your future self and new team members to understand your application.

Boilerplate projects exist for a reason, and you can learn a lot by studying them and reading the source. But they are rigid, can easily become obsolete, and rely on the continual support of the maintainers. The React ecosystem moves fast and new boilerplates are just around the corner. In fact, there's so many that you can now search through 100+ Github repos to [find your perfect React starter project.](http://andrewhfarmer.com/starter-project/ "find your perfect React starter project") The thing is, you probably won't find the perfect one because the perfect one would have everything you need and nothing you don't.

Imagine if some of theses projects were created as guides or tutorials instead. You could pick the topic or problem that you wanted to solve, get a good understanding of potential solutions and then implement the right one in your own project with confidence. Yes it might take a bit longer compared to copying a boilerplate and moving on. But you'll have a much simpler, more maintainable codebase that won't bring you to tears in the future.

### Automate your build configuration instead

[Create React App](https://github.com/facebookincubator/create-react-app "Create") is like a boilerplate for your build config, and it's great. If you're starting a new React project I highly recommend checking it out. Rather than dictate how you should build your application, it does all the heavy lifting of setting up your build config instead. It does force some restrictions in return for simplicity, but you can always eject and go your own way if need be. There are other options to choose from when it comes to build config automation, however, Create React App is the most popular and is supported by the React team. I'll be using it in part 2 when we create an actual application.
