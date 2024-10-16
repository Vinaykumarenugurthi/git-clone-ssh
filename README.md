Creating Simple "Hello World" Program using HTML :-
------------------------------------------------
 <h1>Hello World!</h1>

Creating Simple "Hello World" Program using JavaScript :-
------------------------------------------------------

    <script>
        const heading = document.createElement("h1");
        heading.innerHTML = "Hello World from JavaScript";

        const root = document.getElementById("root");
        root.appendChild(heading);
    </script>

Creating Simple "Hello World" Program using React :-
------------------------------------------------------

const parent = React.createElement("div",{id:"parent"},[
        React.createElement("div",{id:"child1"},[
            React.createElement("h1",{},"I'm an H1 Tag"),
            React.createElement("h2",{},"I'm an H2 Tag")]),
        React.createElement("div",{id:"child2"},[
            React.createElement("h1",{},"I'm an H1 Tag"),
            React.createElement("h2",{},"I'm an H2 Tag")])]);

const heading = React.createElement("h1",{ id:"heading", xyz:"abc"},"Hello World from React!");

const root = ReactDOM.createRoot(document.getElementById("root")); 

root.render(parent);

 1) What is CDN links ?
 2) What is crossorigin ?
 3) Why didn't react create a single file for React and ReactDOM instead of two seperate files ?

 4) What is React.createElement and it's use ?
 A:- with "React.createElement" we can create react element and end of the day it is an javascript object.when we render this element onto DOM it'll become HTML element. it has something known as "props", props are children and attributes that we pass it. 

 5) What is the job of root.render ?
 A:- It basically takes the object and creates the Tag(h1) which the browser understands and put that up insdie the root element. 


Pushing a code into GitHub :-
--------------------------
NOTE :- GitHub is client/place which can host git repositories. when you create a new repository github gives you all these steps/commands to you.
 
1) Go to GitHub.com to create a New Repository.
2) Click on 'New Repository', give a 'Repository name' and keep it 'Public'.
3) New Repository will be created and you need to configure this 'remote Repository' to our 'local Repository'.
4) To make 'Local Repository' as Git Repository you have to do "git init", Then it'll become git Repository.
5) Check the branch if it is 'master', do "git branch -M main" to change it to 'main' and the default branch name is "main".
6) To add all the code files into github, you need to do "git add.".
7) To give a message to this repository, do "git commit -m "episode-01". Here 'episode-01' is the message what we gave to the repository.
8) To setup our local to remote repository and "add origin" we have to do this step "git remote add origin git@github.com:namastedev/namaste-react.git". we have to do this step for only once.
9) Once you add the origin, you can push all the code into remote with this command "git push origin main".

When you do this steps you might phase some issues while doing SSH or it will ask you username,password. to avoid it we have to configure git & github.
These are the steps/commands which you have to follow to create a new repository.

What should have done to push the code into production ?

We have to do a lot of processing in your local like minify,bundle,compress,chunking,code splitting,image optimization,removing comments before push the code into production.

NOTE :- We required alot of other packages, libraries to make our app fast and production ready. React can't do production ready app alone.


NPM :- NPM manages the packages, and it's not stands for node package manager. it is a standard repository for all the packages and all packages are hosted here. we can get any package or library or utility from NPM.
When you create a 'create react app' it automatically has npm inside it, you don't have to configure it. behind the scenes it uses the bundler(webpack) and babel.

To make our project use npm --> "npm init" ->we have to give 'package name,version,description,entry point, test command,git repository,keywords,author,license' after giving all these details it will create a package.json file. 
This package.json file is configuration for our npm.
Our project is depedent on alot of other packages and these packages are also known as "Dependencies".
NPM will take care of what is the versions of that packages.

We need the most important package is called "Bundler". this bundler helps you to  do all these things minification,bundling,compressed,cleaned,cached.
EX:- webpack,parcel,veet.

To get/install any package into our project we use this command -> npm install "package name"
to get the bundler(parcel) into our app -> "npm install -D parcel" -> it'll create two files "node_modules,package-lock.json".
There are two types of dependencies which are app can have
1) Dev dependencies -> these are needed when we develop our app
2) normal dependencies -> these are needed in prooduction time
^ -> known as caret -> used for minor updates/changes (next versions like 2.8.3 to 2.8.4)
~ -> known as tilde -> used for major updates/changes (next versions like 2.8.3 to 3.0.0)

npm install -> creates node_modules file. 

Every dependency has a 'package.json file'.'
Every package/dependency is dependent on other dependencies those dependencies depends on other dependencies, these dependency tree is called "Transitive dependencies".
we put 'node_modules', '.parcel-cache', 'dist' files in "gitignore" folder. because we can regenerate/recreate these files automatically.
we put package.json & package-lock.json inside github.

To ignite our app/ to create a server for our app -> "npx parcel index.html" -> and npx means we're executing npm package, parcel and we give a source file as index.html. it'll host our code on 'localhost:1234'. it is used to start our server/app on localhost:1234.

npm -> to install a package
npx -> to execute a package
parcel will build a development build for our app and host it on localhost:1234
To install react & react-dom from npm -> npm install react,npm install react-dom
we install react & react-dom as a normal dependencies.
x
NOTE :-
-> Once we install any package from npm we need to import them in our code file, otherwise it'll throw an error. ex:- "Uncaught ReferenceError: react is not defined"
-> Again we get an error about the import keyword that "Browser scripts cannot have imports or exports. we have to declare that the script tag as 'module' -> " <script type="module" src="./app.js"></script> ".

-> If you do any changes in the code and once you click the save, and it automatically will change/refresh the code. this is done by parcel. it is doing HMR(hot module replacement) with the help of "File watching" algorithm and it is written in C++.  
-> parcel gives you "Faster Builds" because it is doing 'caching'. parcel took some place which is the folder called ".parcel-cache" for caching everything that you do.
-> Everytime when you save the code, parcel builds our app and starts again and takes less time by doing caching.
-> Parcel will do Image-Optimization, Minification, Compress our code, Consistent Hashing, Code Splitting, Differential Bundling - support older browsers, Diagnostic, Error Handling, HTTPs, Tree Shaking - remove unused code, Different dev and production bundles.

->  "npx parcel build index.html" -> it'll build production ready app 
-> It'll add all the development files into 'dist' folder.
-> "Browserslist" -> it is an npm package and it needs configuration in package.json. It is used to make our compatible for older browsers.   
ex:- "browserslist": [
    "last 2 chrome versions",
    "last 2 firefox versions"
]

-> These commands are different for development build and production build. To make our life easier what we do, we create a script, that'll build our project Instead of writing these commands again and again.
-> It is an npm script, you need to create that script in your package.json file. We can create a different types of scripts. 
-> EX:- 1) To create dev build (for development) - parcel index.html
        2) To create prod build (for production) - parcel build index.html
NOTE:- Once we have created these scripts, we no longer have to write the "npx parcel index.html", 
instead we do "npm run start/npm start","npm run build".

-> HTML elements are DOM elements, in react we have react elements which are kind of equilent to DOM elements.
-> " JSX is a javascript syntax which is easier to create react elements".
-> JSX and React both are different. we can write react without JSX, but JSX makes developers life easy. JSX is a convention where we kind of merge these html and js together. 
-> JSX is not like html inside javascript. JSX is a html like syntax.
EX:- const jsxHeading = <h1 id="heading">Namaste React using JSX </h1>;  
=> JSX-> Babel transpiles it to React.createElement -> ReactElement - jsObject -> HTMLElement(render)

NOTE:- js engine understands js code and Ecmascript, but not jsx code. js engine understands the jsx code with the help of parcel. This jsx code transpiled before it goes to the js engine and then js engine receives the code that browsers can understand. Parcel gives the responsibility of this transpilation to a package which is known as 'Babel'. Babel is a normal javaScript package/open source javascript compiler. It is also called as a "transpiler". Parcel installs the Babel into our project. It basically takes your jsx and converts it into the code that browser/js engine understands. Babel converts jsx into react.createElement. Some older browsers don't understand ES6 version of javascript code, Babel will tranfiles that es6 code into browsers understandable code.
-> In JSX, we declare Class as "className". while declaring attributes in JSX we have to use camelcase.
-> If you write your jsx code into multiple lines of code then you have to wrap that code in paranthesis. Because babel needs to understand where jsx is starting and where jsx is ending. If you write it in single line you don't need to wrap it inside the paranthesis.
 
REACT COMPONENTS :-
Everything is a component in react. There are two types of components.
1) Class Based Components - Old way of writing code - it uses javscript classes
2) Functional Components - new way of writing code - it uses javascript functions
-> React functional component is just a normal javascript function which returns some piece of jsx. whenever yo are creating a functional component or any react component, name it with a capital letter. Otherwise y'll get an error.

EX:-
1) const HeadingComponent = () => {
    return <h1>Namaste React Functional Component </h1>
};
2) const fn = () => true ;
   const fn2 = () => {
    return true ;
}; 
Here, fn & fn2 both are same.

React Element :-
--------------
const Title = () => (
    <h1 className="head" tabIndex="5">
    Namaste React using JSX</h1>
);



EPISODE 03 :-
----------

-> Way of putting elements inside other elements :-

EX:- const elem = <span>React Element</span> -> (Element)

     const HeadingComponent = () => (
        <div id="container">
        <h1 className="heading">Namaste React Functional Component</h1>
        </div>  -> (Component)
     );

     const title = (
        <h1 className="head" tabIndex="5">

        {elem}  -> (Element)

        Namaste React using JSX -> (normal text)

        <HeadingComponent />  -> (Component)
        </h1>
     );

-> Multiple ways of putting components inside other components :-

   1) const AppLayout = () => {
      return (
        <div className="app">
        <Header/>
        </div>
       )
    }
Here, AppLayout & Header are components and we kept the Header component inside AppLayout component like nested.

   2) 2nd way :-
      <Header></Header>

   3) 3rd way :-
      {Header()}   

-> Way of putting any javascript code inside a JSX code/ Component :-
    
 EX:-  const number = 1000;
       const HeadingComponent = () => ( 
         <div id="container">

          {number}
          <h2>{number}</h2>  -> these are js codes
          {100 + 200}

          <h1 className="heading">Namaste React Functional Component </h1>
          </div>
       );

 
Episode 04 :-
----------
-> Inline CSS :-
   EX:- <div id="root" class="root" style="width: 100px"></div>  
-> Way Of Writing CSS in JSX Code :-
   EX:- const styleCard = {
           backgroundColor: "teal"
         } 
      This is a JavaScript Object.
    <div className="res-card" style={styleCard}></div>

This is the way to add a JavaScript code inside a JSX code using curly braces. this inline style is not a preferred way. We can also write like this instead of creating a js variable.

EX:- <div className="res-card" style= {{backgroundColor: "gray"}}>
-> Here, first curly bracket is telling there is some peice of js code inside it and second bracket is refers to js object.

 PROPS :-
 -----

  It is a short form for Properties. so properties are something which you can pass to the component. Suppose if we want to dynamically pass data to some component, then we can use this props to pass the data. Functional component at the end of the day is normal js function. Similarly props are just normal arguments to a function.

  Simply passing a prop to a component is just like passing an argument to a function.

EX:- 
const Body = () => {
    return (
        <div className="body">
        <div className="search">Search</div>
        <div className="res-container">
        1) <RestaurantCard resName="Meghana Foods" cuisine="Biryani, North Indian, Asian"/>
        2) <RestaurantCard resName="KFC" cuisine="Burger, Pizza"/>
    )
};
Above two examples are props.

const RestaurantCard = (props) => {
    console.log(props);
    return (
        <div className="res-card" style={{backgroundColor:gray}}>
        <img className="res-logo" alt="res-logo" src="" />
        <h3>{props.resName}</h3>
        <h4>{props.cuisine}</h4>
        <h4>4.4 stars</h4>
        </div>
    ); 
}
we pass props like this, and instead writing props everywhere we can also write like this ->

const RestaurantCard = ({resName, cuisine}) => {
    return(
        <div className="res-card">
        <h3>{resName}</h3>
        <h3>{cuisine}</h3>
    );
};
This is the direct way of adding data without props and it's called "Destructuring". Here, we are wrapping the data inside a object and it is passing to that function. This is not something in react, this Destructuring is javascript.

This below code and above code both are same :-
const RestaurantCard = (props) => {
    const {resName, cuisine} = props;
    return (
        <div className="res-card">
        <h3>{resName}</h3>
        <h3>{cuisine}</h3>
    );
};

NOTE :- Here, we write the code with props and without props.

Config Driven UI :- 
------------------
Basically it means controlling your "UI" with the help of using data/config and this config comes from Backend. So, according to the data which is coming from backend, your UI is getting changed (the data changes according to the location)

-> In any react application, There is a UI layer which we are developing on the front page and there is a data layer.
Both of the layer makes an application.

-> When you are fetching data through API's from backend and there is an array of data that you need to change as comma seperated values, then you can use -> array.join(", ")
 EX:- <h4>{resData.data.cuisins.join(", ")}</h4>

 Here, cuisine is the array. with the "join method" we can add anything in the data, we can change the data according to the requirement using join method.

-> Optional Chaining :-
--------------------

const RestaurantCard = (props) => {
    const {resData} = props;

    const {cloudinaryImageId,name,avgRating,cuisine,costForTwo,deliveryTime} = resData?.data;  
    return (
        <div className="res-card>
        <h3>{name}</h3>
        <h4>{cuisine.join(", ")}</h4>
        <h4>{avgRating} stars</h4>
        <h4>{costForTwo/100} FOR TWO</h4>
        <h4>{deliveryTime} minutes</h4>
        </div>
            );
};
Here, we use optional chaining to access the nested data.

Using MAP Method To Get Data:-
----------------------------

Instead of Hardcoding the data, we can use MAP method to get the data from Array.

EX:- const Body = () => {
    return (
        <div className="res-container">
        {
             resList.map(restaurant => <RestaurantCard resData={restaurant}/>)
        }
    );
};

Passing Unique KEY For Each Card :-
--------------------------------

const Body = () => {
    return (
        <div className="res-container">
        {
             resList.map(restaurant => <RestaurantCard key={restaurant.data.id} resData={restaurant}/>)
        }
    );
};
With this KEY we can get rid of the Warnings/Errors. This KEY should be unique.

NOTE :- We can also use 'index' as a KEY in MAP method to render the data and it works fine but it's not recommended to use instead of key.

EX:- const Body = () => {
    return (
        <div className="res-container">
        {
             resList.map(restaurant , index) =>(
                <RestaurantCard key={index} resData={restaurant}/>)
        }
    );
};
















SOME OF REACT EXTENSIONS:-
1) prettier - code formatter
2) Bracket Pair Colorization Toggler
3) ESLint
4) Better Comments
Chrome Extension:-
 JSON Viewer 

-> What is package.json & package-lock.json and the difference between them and it's uses?
-> What is integrity (sha512) in package-lock.json ?
-> What is node_modules and it's use ?
-> What is npm and npx ?
-> What are React Elements ?
-> What is JSX ?
-> What is Babel ?
-> Find out the diffterent attributes of different tags that how can we write in JSX ?
-> what is react component ?    
-> What is Component Composition ?
-> What is the difference between nested components and component composition ?
-> What is config driven ui ?
-> What is the use of join method in javaScript ?
-> What is optional chaining ?
-> What is the Unique KEY that we have to give for each card ?