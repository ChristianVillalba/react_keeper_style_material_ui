# React: Keeper App - Dependecies and Style

Created with [CodeSandbox](https://codesandbox.io/)  
Notes from: React module  
[The Complete 2021 Web Development Bootcamp](https://www.udemy.com/course/the-complete-web-development-bootcamp/)  
Instructor: Dr. Angela Yu 

## Description

A note-taking application.      
It allows us to take notes, share them with others, and access them from different devices. 

The functionality is ready,     
In this module, we are going to work in the apparence.

## What I have learnt with this project

* Adding dependencies
* Material UI
* Installing Material UI
  * CodeSandbox: "Add Dependencies" Button > [@material Ui/core](https://codesandbox.io/examples/package/@material-ui/core)  
  * Locally - NPM:  [Material UI - core](https://www.npmjs.com/package/@material-ui/core)  
* Material UI - Icons
* Expanding features for our outputs
* Material UI - Buttons


---
---
# Notes:

Some functionlaity may be lost due depreciation:

Starting from the the sandbox: [Starting Point - CodeSandbox](https://codesandbox.io/s/keeper-part-3-starting-s13gn?fontsize=14&hidenavigation=1&theme=dark)      
We click on the "Add Dependency Button" and serch for Material UI     
We need:
* @material Ui/core 
* @material Ui/icons

## Installing Material UI:
* CodeSandbox: "Add Dependencies" Button > [@material Ui/core](https://codesandbox.io/examples/package/@material-ui/core)  
* Locally - NPM:  [Material UI - core](https://www.npmjs.com/package/@material-ui/core)  

### Material UI
Material-UI are basically pre-built React Components that we can customize and get hold of some of the functionality     
so that we can create our own apps much faster using Google's design concept which is called Material Design.

#### Material UI - Icons
After installing Material UI core & icons,    
we can just import the icons and use them as any other React Component


#### Changing Delete Button:
We can find the full list of icons in their search page: [Material UI - Icons](https://mui.com/components/material-icons/)  
We search for something to do with "Delete",     
We select the icon we want to use and just copy its line of code:
```javascript
import DeleteIcon from '@material-ui/icons/Delete';
```
And now we can paste the import statement in our Note.jsx,      
and use DeleteIcon as Component
```javascript
<DeleteIcon />
```

The benefit of using React Components over other option such as bootstrap or fav icons     
is that in React we have our JS, CSS and HTML combined into one in each of these Components.      
So we can even add Components that actually have functionality that we didn't even have to code up.

#### Changing Add Button:
Change the Add button so that instead of saying the word "Add" I want to use an Add Icon from material icons:
We search for the icon,
We copy the import Statement and we paste it in our CreateArea.jsx
We use the new imported Add Component

Now notice how in the final version this add is a lot fancier:    
Hover over functionality, animations...
We can achieve this with floating action button that comes from the material UI package, instead of using our own button.

#### Material-UI Buttons

