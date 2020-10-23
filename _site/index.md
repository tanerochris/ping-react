## Integrate Payment with Flutterwave with React.
Hey there you have gone through the [react](url) documentation and some resources here and there and you are ready to put this knowledge to use. In this tutorial we are going to apply react knowledge by integrating payment into a react application. So I built [spyo.com](url), a campaign platform where brands get support from their fans in a bid to grow. Spyo was built using [NextJs](url) -  A framework for building react applications, MongoDB a NoSQL database on documents and Bulma react UI library kit and uses [Flutterwave](https://www.flutterwave.com/) - An african payment solution provider to make and accept payments from customers anywhere in the world.  By the end of this tutorial you should have build some part of Spyo, and learned the underlaying react concepts. The tutorial will cover authentication with Facebook, and the integration of payment with Flutterwave.

### React concepts
In this tutorial we are going to cover the following react components or concepts.shall cover in this tutorial.
- React funtional components
- Props
- Hooks
- Ref
- Suspense
- Lazy loading

## Lets get started
### Installing required applications to run application
The first step to this tutorial will be installing all relevant dependencies. Make sure you have the following installed [Node Js](https://nodejs.org/en/download/) for running the base application we shall be building on, [Mongo](https://docs.mongodb.com/manual/installation/) for application database, [git](https://git-scm.com/downloads) to clone the base app repository. After installing all dependencies required to run the app, the next step is to clone the application.

### Cloning base app repo
Open your terminal and change to the directory on your PC you wish to clone the app and run the git clone command.
```markdown
git clone --recursive https://github.com/tanerochris/spo-tuto-base.git
```
Install dependencies with yarn
```markdown
yarn install
```
### Running the app
When you are done cloning, the name of application folder will be spo-tuto-base. Change to the spo-tuto-base directory and run yarn to start the application. We will start by running the application in developer mode.
```markdown
    cd spo-tuto-base
    yarn dev
```
In your browser go to the url **http://localhost:3000**, you should see the base interface we shall be building with. To focus only on the essential react concepts to be presented in this writeup we have setup the application with some design and functionality already.

<img src="{{site.url}}/images/index.PNG" style="display: block; margin: auto;" />

To run the application in production mode, you first build the app for optimizations by NextJS framework then run app.

```markdown
    yarn build
    yarn start
```

NextJS comes with react installed. To check for the version of react installed, open a new terminal session
```markdown
    yarn list --pattern --depth=0 "^react*"
```
You should see the version of react installed together with other react packages. In my own case the above command produces the following output at the terminal. Notice we are working with version 16.13.1 of the react library which is currently the [latest](https://reactjs.org/versions/) at the time of this writing.
 
```markdown
    $ yarn list --pattern --depth=0 "^react*"
    yarn list v1.22.4
    warning Filtering by arguments is deprecated. Please use the pattern option instead.
    ├─ react-dom@16.13.1
    ├─ react-is@16.13.1
    ├─ react-refresh@0.8.3
    └─ react@16.13.1
    Done in 1.67s.
```

### Structure of the application
We are going to look at the struture of the app, where each item will fit in, some screen shots at the output we wish to obtain.

```
.
|-- LICENSE // hello
|-- README.md
|-- app.properties
|-- components
|   |-- partials
|   `-- theme
|-- helpers
|-- middlewares
|   |-- Database.js
|   |-- Session.js
|   `-- index.js
|-- models
|   `-- user
|-- node_modules
|-- package.json
|-- pages
|   |-- _app.js
|   |-- api
|   `-- index.js
|-- public
|-- schemas
```
NextJs is an opinionated  framework, it requires the pages and public folders to be present in the directory structure and located at the root level. We will add other directories to hold specific items of our application. Below is a summary detail of what each directory should contain. Note this is not specific to react or NextJS so you can define your own structure.

- The _pages_ directory will hold the different web pages of our application, and api endpoints which will go under the pages/api directory. NextJs uses a file name pattern for url routing where each page or api is associated to a route based on its file path from the pages folder.
- The _public_ directory hosts static assets such as images, fonts just to name a few. The component folder holds application ui or page components such as partials and theme.
- The _models_ folder to hold MongoDB data models the application data.
- A _helper_ folder to hold utility functions.
- A _middlewares_ folder to hold api routes middleware functions.
- An _app.properties_ file to hold variables that will be used across the app.

## Let's start building with react
### Building the login and Signup page
In react application is broken down into components were each component can be seen as an independent re-usable piece of code.

```markdown
Syntax highlighted code block

# Header 1
## Header 2 
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/tanerochris/ping-react/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
