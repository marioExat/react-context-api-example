# [Getting Started with Create React App](https://www.freecodecamp.org/news/context-api-in-react/)

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

`npx create-react-app react-context-api-example`

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### Why Use context API

![Passing props](https://www.freecodecamp.org/news/content/images/2023/03/image-198.png)

In many cases, passing props can be an effective way to share data between different parts of your application. But passing props down a chain of multiple components to reach a specific component can make your code overly cumbersome.
image-198
Illustration of passing props from parent to children

From the above diagram, to pass data down to the component "Child B", we need to pass it down through all the intermediate components, even if those components don't actually use the data themselves. This is what is referred to as "prop drilling."

Prop drilling can make your code more difficult to read and maintain, and can also make it harder to refactor your components later on.

This is where the Context API comes in. With Context API, you can store data at the top level of the component tree and make it available to all other components that need it without passing props.

### How the context API works

Context API allows data to be passed through a component tree without having to pass props manually at every level. This makes it easier to share data between components.

![](https://www.freecodecamp.org/news/content/images/2023/03/image-197.png)

It’s like having a big box that holds all the things you need for your shopping trip. You can take things out of the box when you need them, and put them back in when you’re done.

Basically, Context API consists of two main components: the context provider and the context consumer. The provider is responsible for creating and managing the context, which holds the data to be shared between components. On the other hand, the consumer is used to access the context and its data from within a component.

For example, let’s say you have a shopping app with a component that shows a user’s shopping cart, and another component that shows the user’s order history.

With Context API, you can create a “context” that holds the user’s shopping information, like their cart and order history. Then, you can use that context in both the shopping cart and the order history component, without having to pass the information down through props.

In the example given, the provider will create the context that holds the user's shopping information, while the consumer components (shopping cart and order history) will access that context to retrieve the data they need. This avoids the need to pass the information down through props, making your code more efficient and easier to manage.

### Create a context object

First, you need to create a context object using the createContext function from the 'react' library. This context object will hold the data that you want to share across your application.

### Wrap Components with Provider

Once you've created a context object, you need to wrap the components that need access to the shared data with a Provider component. The Provider component accepts a "value" prop that holds the shared data, and any component that is a child of the Provider component can access that shared data.

It's important to note that the Provider component should be wrapped around the top-level component in an application to ensure that all child components have access to the shared data.

### Consume the Context

Now that we've created the provider component, we need to consume the context in other components. To do this, we use the "useContext" hook from React.

### Use Cases of Context API

Here are some real-world use cases of Context API.

    Theming: You can use Context API to store the current theme of your application and make it available to all components. This way, whenever the user switches the theme (such as enabling dark mode), all components will be updated with the new theme.

    User Authentication: You can also use Context API to store a user's authentication status and pass it down to all the components that need it. This way, you can easily restrict access to certain parts of your application based on the user's authentication status.

    Multilingual Support: You can store the current language of your application in the context and pass it down to all the components that need it. This way, you can easily switch between different languages without having to pass the language down as props to all the components.
    Accessing data from external sources: Finally, you can use the

    Context API to store data retrieved from external sources such as APIs or databases and make it available to all components. This can simplify your code and make it easier to manage data across your application.

Overall, Context API provides a flexible and efficient way to manage state data across your application, and it can be particularly useful for managing global data that needs to be shared between multiple components.

### Best Practices fro Context API

As with any tool, there are best practices and common pitfalls to keep in mind when using the Context API in your projects. Here are some tips for effective use of the Context API:

1.Use a separate file to define your Context: It's a good practice to define your context object in a separate file to keep your code organized and easy to maintain.

2. Keep Context API limited to global state management only: It's best to use the Context API for managing state that needs to be accessed across multiple components in your application. Avoid using it for state that only needs to be accessed within a single component, as it can lead to unnecessary complexity and performance issues.

3. Use context providers sparingly: While context providers can be a powerful tool for managing global state, it's generally a good idea to use them sparingly. Instead, consider using props to pass data down through your component tree whenever possible.

4. Use default values: When creating a new context, it's a good idea to provide a default value that will be used if no provider is present. This can help prevent unexpected errors and make your code more robust. Note that, for the project we did above, we used an empty string as the default value for the context object.

### Using Context to implement light/dark mode theme

[light-dark mode](https://github.com/dboatengg/context-api-tutorial)

## Further Reading

- https://www.freecodecamp.org/news/react-budget-tracker-app/
- https://www.freecodecamp.org/news/using-the-react-context-api-getting-started-2018/
- https://www.freecodecamp.org/news/how-to-build-a-redux-powered-react-app/
- https://www.freecodecamp.org/news/redux-for-beginners-the-brain-friendly-guide-to-redux/
- https://www.freecodecamp.org/news/how-to-learn-redux-from-a-functional-programming-perspective-720892f704c6/
- https://www.freecodecamp.org/news/redux-get-the-ball-rolling-in-10min-9d9551ff4b3c/
- https://www.freecodecamp.org/news/clever-react-context-tricks-using-typescript-not-redux-7e2b9c7e5bf6/
