---
title: "How To Change Background Color Using JavaScript? Small Project"
seoTitle: "Change Background Color with JavaScript"
seoDescription: "Learn how to create a background color changer using JavaScript, HTML, and CSS in this simple step-by-step guide"
datePublished: Sun Dec 17 2023 05:48:25 GMT+0000 (Coordinated Universal Time)
cuid: clq92gdjo000008l3bbxcfbag
slug: how-to-change-background-color-using-javascript-small-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1723036919458/f5c2e069-e61d-419a-a59e-8782cbc6e3b4.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1702765467538/9e056c9c-7f8a-49be-af7e-37e0db5def33.png
tags: css3, javascript, html5

---

If you're looking for a simple JavaScript project to practice and test your skills, then you're at the right place. This article will help you build a small background color changer. Here we are going to learn how to change the background color using JavaScript after clicking a button.

## What are we going to build? Let's have a look!

This will be the project that we are going to build. In this project, we will create this simple slick background color changer and understand DOM manipulation using JavaScript.

%[https://codesandbox.io/embed/9jmnrw?view=preview&module=%2Findex.html] 

The whole code is available in the code sandbox. Click [here](https://codesandbox.io/p/sandbox/bg-color-changer-9jmnrw) for the source code!

## Prerequisites

Basic knowledge of HTML, CSS, and JavaScript

## Project Setup

* Create a folder for this project and name it as per your preference. I named it *bg-color-changer.*
    
* Now open the folder in your Favorite code editor. I will suggest using [VSCode](https://code.visualstudio.com/download)
    
* Create an index.html file in it and open it in your browser.
    

![Empty index.html file opened in chrome browser](https://cdn.hashnode.com/res/hashnode/image/upload/v1702755613206/a292e26e-83d7-41f7-a991-90b7b65ca810.png align="center")

Now we are good to start writing code!

> If you're using Vs code then download the live server extension and run the project.

## Add Basic HTML To The Project

This project will have four buttons inside a parent div. Let's build the basic HTML markup for our project.

### Add HTML boilerplate code to our index.html file

We will start our project with the HTML boilerplate code. Just copy and paste it into your index.html file and save it.

```xml
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Background Color Changer</title>
  </head>
  <body>
    <h1>Hello Developers!</h1>
  </body>
</html>
```

> If you are using Vs code then just click the exclamatory mark(!) on the empty index.html file this will suggest the above HTML boilerplate code.

Now you can see something like this in your browser!

![html boilerplate code is running in chrome browser and showing a heading called hello developers](https://cdn.hashnode.com/res/hashnode/image/upload/v1702756205839/07c79093-4212-478c-af55-3171248edc86.png align="center")

> Make sure to always save the index.html file and refresh the browser tab if you are not using auto-refresh tools like the live server in vs code

### Create a parent div of four buttons

In this project, we are showing four buttons inside a div in the middle of the screen.

So here we will create a div of class *container* and four buttons with class *btn.*

Here we will add a unique *ID* to each button to identify them. For simplicity here I added the color names that they represent.

```xml
 <div class="container">
        <button class="btn" id="red">Red</button>
        <button class="btn" id="blue">Blue</button>
        <button class="btn" id="green">Green</button>
        <button class="btn" id="yellow">Yellow</button>
    </div>
```

![four html buttons shown along with code](https://cdn.hashnode.com/res/hashnode/image/upload/v1702758683433/aa3fe6d2-1432-4056-ae37-30cb95d4d36b.png align="center")

> You can use a shorthand-like button.btn\*4 to create four buttons in a single command. Here "." is used for class and "\*" is used for how many elements you want.

## Add styles to the document

For this project, I used simple CSS. You can modify it as per your creativity.

You can create a specific file and link it to the index.html to write CSS. This is a small project so I wrote internal CSS.

Add a *style* tag inside the *head* of the document and implement these styles.

```css
  <style>
        *{
            background-color: black;
            margin: 0;
            padding: 0;
        }
        body{
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .container{
          padding: 20px;
          background-color:darkgrey;
          border-radius: 10px;    
        }

        .btn{
            padding: 10px 20px;
            border-radius: 10px;
            cursor: pointer;
        }
        #red{
            background-color: red;
        }
        #green{
            background-color: green;
        }
        #blue{
            background-color: blue;
        }
        #yellow{
            background-color: yellow;
        }
    </style>
```

Now our project will look something like this!

![html buttons are styled with css](https://cdn.hashnode.com/res/hashnode/image/upload/v1702759276429/224381c9-c939-4d52-9a28-5c1dfe842eb4.png align="center")

## Let's add functionality to our project

So here comes the fun part of the project. Here we are going to implement the JavaScript code and make this project functional.

Let's add a script tag inside our index.html file below the body tag.

Here our primary focus is to change the background color of the body. Here the body is given a class of 100vh and now it's inheriting the black color from the universal selector(\*).

Let's grab the body inside a variable called *body .*

```javascript
const body = document.querySelector('body');
```

We need to store all buttons in a variable to add event listeners

Let's store all buttons in a variable called buttons. Here we will select all buttons by their class *'btn'* using querySelectorAll.

```javascript
const buttons = document.querySelectorAll('.btn')
```

Let's now console log *buttons* and see what *querySelectorAll returning to us!*

```javascript
console.log(buttons)
```

![nodelist foreach method](https://cdn.hashnode.com/res/hashnode/image/upload/v1702760609246/576ad245-3f97-4229-80cc-300025c53023.png align="center")

Now here we can see *querySelectorAll* is returning us a *NodeList* where we can perform forEach loop over *buttons. Let's perform a forEach loop over buttons.*

```javascript
 buttons.forEach((button)=>{
        
     })
```

Now we have access to each button, so let's add mouse click event listeners to each button.

```javascript
 buttons.forEach((button) =>{
        button.addEventListener('click',(event) =>{
            

        })
    })
```

Now from each event we can access the id of the element if any mouse click event occurs.

If the user clicks on a specific button we can access that button's id.

Let's write a switch case loop for each id and store the background color in a variable.

colorName is a variable that will store the color of our body.

```javascript
 buttons.forEach((button) =>{
        button.addEventListener('click',(event) =>{
            console.log(event.target.id)
            let colorName;
            switch(event.target.id){
                case 'red':
                    colorName = 'red';
                    break;
                case 'green':
                    colorName = 'green';
                    break;
                case 'yellow':
                    colorName = 'yellow';
                    break;
                case 'blue':
                    colorName = 'blue';
                    break;
                default:
                    colorName = 'purple';
                    break;
            }

        })
    })
```

Here the switch case loop returns a color for each element id.

Now we have our variable ready as per the mouse click event. Let's update the background color of the body as per the button click.

```javascript
 buttons.forEach((button) =>{
        button.addEventListener('click',(event) =>{
            console.log(event.target.id)
            let colorName;
            switch(event.target.id){
                case 'red':
                    colorName = 'red';
                    break;
                case 'green':
                    colorName = 'green';
                    break;
                case 'yellow':
                    colorName = 'yellow';
                    break;
                case 'blue':
                    colorName = 'blue';
                    break;
                default:
                    colorName = 'purple';
                    break;
            }
            body.style.backgroundColor = colorName

        })
    })
```

Wow! We just completed our background color changer project using HTML, CSS, and Javascript.

Just Have a look here!

%[https://codesandbox.io/embed/9jmnrw?view=preview&module=%2Findex.html] 

[Here](https://codesandbox.io/p/sandbox/bg-color-changer-9jmnrw) is the source code of this project

## Conclusion

This is a simple project on basic JavaScript. I hope this small project on how to change the background color using JavaScript might help you. If you have any doubts or suggestions please feel free to contact me. Thanks for reading this article. Let's Connect!