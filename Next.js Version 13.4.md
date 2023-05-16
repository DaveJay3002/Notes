## File and Folder Structure
### App Folder
The app folder is the folder that gets rendered on the server side so all the components inside this folder are server-side rendered. So by default the layout and the home page are rendered on the server side making SEO better. 
To make a component inside app folder to client side rendering "use client" at the top of your code.
- Layout.tsx
	The main entry point of our application and every components are wrapped within it as its children and every thing here will be displayed in every route in the entire application.
	Mostly we are going to add teh navbar and footer here.
	If we want to add something that stays consistent over the entire app add it here.
- Page.tsx
	This the home page route of the application.
- globals.css
	This file contains the global CSS files of the application.

## Routing in Next.js
Just create a folder corresponding to the desired route in the app folder. And in that folder create a page.js file and this would be accessed at the /foldername route and it is as simple as that.
### Nested Routing
Just create a folder inside the folder and it will create a nested route.

### Dynamic Routing
Create a new folder with [folderID] around it and inside it we wil be able to access the folderID variable and render data dynamically.

### Layouts in different routes
We can have a seperate layout file for every route as well to render components using the dynamic routing variable.
We can also have a loading.js file in every folder to show the loading page while the other route is loaded.
We can also have error.js file to handle errors.

## When to use client side components
Whenever using interactivity and event listeners like onClick(), onEvent(), onChange().
Also when using states and lifecycle effects like useState(), useReducer(), useEffect().
While using custom hooks that use browser only APIs.