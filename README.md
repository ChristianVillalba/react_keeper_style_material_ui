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
* Floating Action Button
* Zoom Component
* Createing Effects: Conditional Rendering
* Icon in Header
* Background Image: using [Transparent Textures](https://www.transparenttextures.com/) 

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
```javascript
import Add from "@material-ui/icons/Add";
```
We use the new imported Add Component (the icon) inside our button.
```javascript
        <button onClick={submitNote}>
          <Add />
        </button>
```

#### Material-UI Buttons
Now notice how in the final version this Add Buttoon is a lot fancier:    
Hover over functionality, animations...
Instead of using our own button, we can use the **Floating Action Button (FAB)** that comes from the material UI package.

We use the import statement in our CreateArea.jsx
```javascript
import Fab from "@material-ui/core/Fab";
``` 
and now we can use the new imported Fab Component (Floating Action Button)
```javascript
        <Fab onClick={submitNote}>
          <Add />
        </Fab>
```

#### Zoom Component
The Floating Action Button animating onto the screen as an expanding piece of material.     
this is done using a Zoom transition.       
Checking out the code, this is done just wraping the Fab inside a **Zoom Component**

We use the import statement in our CreateArea.jsx
```javascript
import Zoom from "@material-ui/core/Zoom";
``` 
and now we can use the new imported Zoom Component with this **in** Prop.     
This is a True or False Boolean
```javascript
        <Zoom in={true}>
          <Fab onClick={submitNote}>
            <Add />
          </Fab>
        </Zoom>
```

#### Effect: Conditional Rendering

We will create an effect: starting out with just the **textarea** as a **single line**,          
and then when you click on it, it shows the title and the button also only zooms in when that state is set to true.     

The first thing we need to do is hold the state of whether if CreateArea is expanded.
```javascript
  const [isExpanded, setExpanded] = useState(false);
``` 
I want my `isExpanded` constant to be set to `false` because I don't want it to be expanded     
and it will be expanded only when the **textarea** gets clicked on...     
so lets add, on **textarea**, an `OnClick` with a method called `expand` (or any name).
```javascript
<textarea onClick={expand} ... />
``` 
And we will define that method:
```javascript
  function expand() {
    setExpanded(true);
  }
``` 

So when this method `expanded` is called (onClick), we're going to set the it to `true`.      
We can now listen for that in ordedr to render the **input**.        
Lets put **input** into [Conditional Rendering Statement (using && in React)](https://github.com/ChristianVillalba/react_conditional_rendering)
```javascript
        {isExpanded && (
          <input
            name="title"
            onChange={handleChange}
            value={note.title}
            placeholder="Title"
          />
        )}
```
This Statement shows the **input** only when we click on the textArea (otherwise : null)      

The second thing we mentioned is that we want to change this rows to one to start off with      
and only turn it to three when it's expanded. 
```javascript
        <textarea ...
          rows={isExpanded ? 3 : 1}
        />
```

The final thing to address is our fab button:       
We only want it to show up and zoom in when it shows up only when it's expanded.      
So instead of hard coding Zoom is true `<Zoom in={true}>`,      
we're going to use that isExpanded property again:
```javascript
        <Zoom in={isExpanded}>
```

#### Icon in Heading

We want to use the highlight component in our header
```javascript
import HighlightIcon from "@material-ui/icons/Highlight";
```
And now we can use `<HighlightIcon />` in our `<H1>`

#### Background Image

We can we a website called [Transparent Textures](https://www.transparenttextures.com/)     
and you can scroll through all of these textures to find one that you like.     
And in order to use it, we can simply click on it and now we have that pattern saved as a URL.      
If we go ahead and copy this entire URL where we set our background-image into the body of our CSS:     
```css
body {
  background: #eee;
  background-color: #0040e3;
  background-image: url("https://www.transparenttextures.com/patterns/diagmonds-light.png");
  padding: 0 16px;
}
```

## Conclusion: React as Front-End

If we add a couple of notes and then, go ahead and refresh the page, our notes will disappear.      

**React is a front-end library:**
It's responsible for creating these components, creating the functionality and the styling      
but it's not responsible for saving your data.
So if we do want these things to be persisted then we'll have to use a back-end techonlogy

