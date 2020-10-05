## A Tutorial that shows you how to build a full react application using component Re-use.

Hey there you have gone through the [react](url) documentation and some resources here and there and you are ready to put this knowledge to use, you are not on yet "another tutorial" on react. Ping react is a practical tutorial that gets your hands dirty with building a full react application. In this tutorial I am going to show you how I built [spyo.com](url), a campaign platform where brands get support from their fans in a bid to grow Spyo was built using [NextJs](url) -  A framework for building react application, MongoDB a NoSQL database on documents and Bulma react UI library kit. By the end of this tutorial you should have build your own Spyo, and leaned the underlaying react concepts. 

## Lets get started
The first step to this tutorial will be installing the different tools required to build our application. We will start with NextJS which is a React framework which allows server site rendering and static site generation. I have been longtime fanboy of Express, I wanted to experiment with something new and I had read and heard alot about NextJs, so I went for it considering its seling points such as speed, I chose NextJs becausee of its speed, server side rendering and also good suport for SEO which was what I was looking for at the time.
### Installing NextJs
Before you install NextJs make sure you have [Node Js](https://nodejs.org/en/download/) installed for your specific environement. Having trouble installing Node? Checkout this [tutorial](http://www.w3big.com/nodejs/nodejs-install-setup.html). Once Node Js installed it comes with `npm` which you will use to install NextJs, you can equally use `yarn` in the place of npm. Here I use yarn to install NextJs. In your terminal run the following command. A boilerplate code or template will be downloaded together with dependencies.

```markdown
    yarn create next-app spo-tuto
```

When you are done. Run the newly created react app. Change to the next-app directory and run the command.
```markdown
    cd spo-tuto
    yarn dev
```
In your browser open type and follow the url **http://localhost:3000**, the rendered page contains links to NextJs documentation, you have follow the links and have a look. I wish to mention that you can create NextJs with different [templates](https://github.com/vercel/next.js/tree/master/examples).

### NextJs folder structure

### 

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

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
