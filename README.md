# React Router v4 sample code
[Click for preview](https://rawgit.com/thatisuday/react-router-learning/master/dist/index.html)

## Medium blog with explaination
[https://medium.com/@thatisuday/basics-of-react-router-v4-336d274fd9e0](https://medium.com/@thatisuday/basics-of-react-router-v4-336d274fd9e0)

*******
Route
automatically passes some props to the component it’s
rendering out of which three are the important ones.
prop is
location
 a object which contains some information about current browser URL
match
is currently matched path information and parameters in the
URL. We will talk about URL parameters in a bit.
prop is the
history
history API which is used to navigate user to other view
programatically, which are are going to do in a bit.
En el componente  <route>  ponemos recuperarlo, como ${props.match.url} en
<Route path={ `${props.match.url}/:location(india|us)` }
component={ ContactInfo }/>
Es lo mismo un shorcut de:
<Route path={ `${props.match.url}/india` }
 component={ ContactIndia }/>
 <Route path={ `${props.match.url}/us` }
 component={ ContactUs }/>

*******

-Se puede poner un console.log(this.props)en el componente en question y ver todas las props enviadas cuando se hace click en NavLink- ver console.log of props en contact et imagen explicativa (resultado de la console).cuando es arrow function no se pone this
*******

-Dinamy parameter(:location) con dos puntos indica una variable

*******

-NavLink va anadir la clase active, Link no

*******

-In ContactInfo <Route path={ `${props.match.url}/:location` }
component={ ContactInfo }/> can also resolve /contact/japan. Because of that we use a parameter (india|us)
-inline component abajo: instead passing a component, you can write inline functional component to render.Error page:You need to wrap all your routes inside
component so that
Switch
React Router will render component when a match is found and stops
further rendering.
Hence last route will be rendered only if URL does
not match any route paths, like when URL path is
, try it out.
<Route render={ () => <h1>404 Error</h1> } />
*******

-exact prop on NavLink tells NavLink component to add active class only if URL in the browser matches exactally  to the to prop value. This is necessary because by default, React Router matches links and views with starting match of the URL. Hence / will match everything including & others while /contact will match /contact ,
, etc. (same for route)
<NavLink exact to="/" className="link" activeClassName="active">Home</NavLink>
<Route exact={ true } path="/" component={ Home }/>
# react-router-learning
