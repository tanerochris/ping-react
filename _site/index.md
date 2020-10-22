n## Integrate Payment with Flutterwave with React.
Hey there you have gone through the [react](url) documentation and some resources here and there and you are ready to put this knowledge to use. In this tutorial we are going to apply react knowledge by integrating payment into a react application. So I built [spyo.com](url), a campaign platform where brands get support from their fans in a bid to grow. Spyo was built using [NextJs](url) -  A framework for building react applications, MongoDB a NoSQL database on documents and Bulma react UI library kit and uses [Flutterwave](https://www.flutterwave.com/) - An african payment solution provider to make and accept payments from customers anywhere in the world.  By the end of this tutorial you should have build some part of Spyo, and learned the underlaying react concepts. The tutorial will cover authentication with Facebook, and the integration of payment with Flutterwave. 

## Lets get started
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
In your browser go to the url **http://localhost:3000**, you should see the base interface we shall be building with. To focus only on the essential react concepts to be presented in this writeup we have setup the application with some design and functionality already. To run the application in production mode, you first build the app for optimizations by NextJS framework then run app.

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

## Let's start building
We are going to look at the struture of the app, where each item will fit in, some screen shots at the output we wish to obtain. 
### Structure of the application
```
|-- README.md
|-- node_modules
|-- package.json
|-- pages
|   |-- _app.js
|   |-- api
|   `-- index.js
|-- public
|   |-- favicon.ico
|   `-- vercel.svg
|-- styles
|   |-- Home.module.css
|   `-- globals.css
`-- yarn.lock
```
NextJs is opinionated and comes with the following directories. The pages directory will hold the different web pages of our application, and api endpoints which will go under the pages/api directory. NextJs uses a file name pattern for url routing where each page or api is associated to a route based on its file path from the pages folder. The public directory hosts static assets such as images, fonts just to name a few. To this directory structure we are going to add three more folders, a folder component folder to hold ui or page components such as partials and theme, a models folder to hold data models for the MongoDB, equally helper folder to hold utility functions, a middlewares folder to hold api routes middleware functions, and finally an app.properties file to hold links to external resources or services that will be used by our application. Below is the new structure of the application. You should create the folders accordingly.

```markdown
|-- README.md
|-- app.properties
|-- components
|-- helpers
|-- middlewares
|-- models
|-- node_modules
|-- package.json
|-- pages
|-- public
|-- schemas
|-- styles
```
We are good to go now, but before then if you have been following the tutorial from the beginning you can clone or pull the base application from github repo [spo-tuto](), since the main purpose of this tutorial is to demonstrate how I used React to build [Spyo](), there are details about getting the application configured for routing and database connection that cannot however be covered in this tutorial. In the next sections we shall be buiding the following pages for application, the index, login, register, and campaign pages for the application.

### Building the index page
Below is a result we wish to achieve. When creating the index page we are going to create re-usable components we will use accross the app. The concept of componenents supported by react prevents code duplication, thus facilates maintainance and theming. Essentially a component is an independent item of our application which will contain   


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
