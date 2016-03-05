#Simple CSS guide 


Simple recommendation to follow that will make your css easy to maintain alone or as a team


- Never use id for styling
- Keep specificity as flat as possible 
- Use Js-hook
- Avoid !important
- Avoid styling on a native tag
- Prefer multiline css than monoline
- Think modularity
- Improve readability with "/"
- Consider using BEM or SUIT 


#### Never use id for styling
Not reusable and the specificity is too strong. Only using class narrow down the whole css to only one level.


#### Keep specificity as flat as possible
For performance and maintainability purpose.

Performance : Selectors are read from right to left. The flater the rule is, the less DOM Walking the browser has to do.
https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Writing_efficient_CSS

Maintainability : 
```
.container .column .bloc .text .paragraph{
	font-size:12px;
}
```
font-size property is now hard to overwrite and
also too dependent meaning easy to break...


#### Use Js-hook
If the class is created without intention of styling then it is better to prefix the class with "js-". 
By doing this, we lower the chance to break functionality during css refactoring for example.
One golden rule is to NEVER style this class.
```
<a href="#" class="btn btn js-open-menu">Open</a> 
```
btn is use in for styling.
js-open-menu trigger the function opening the menu


#### Avoid !important
Try to not use !important. Beside exception, the use of this property is usually selfish. It remove the css power of specifiy.
If there is workaround to not use !important then it is better to spend time on it.


#### Avoid styling on a native tag
Better create a class and affect the style to it. This way the tag can be changed without having to touch any css files.
Also in terms of performance, a class selector is faster than a tag selector.

```
HTML
<div class="card">
	<h1 class="title">TITLE</h1>
</div>

CSS
.card h1{} //tag dependant
.card .title{} //tag not dependant

```


####Prefer multiligne css than monoline
Even if it is true that monoline css make the css file lighter and give the impression to have all the property in a glance. It become quickly very hard to read when it has more than 3-4 property (even worse when it involve browser prefix ).
Minification plugin will make the file in one line anyway.
```
.title{font-size:12px; font-weight: bold; height:20px; width:100%; border-bottom: 1px solid #CCC; }

.title{
	font-size:12px; 
	font-weight: bold; 
	height:20px; 
	width:100%; 
	border-bottom: 1px solid #CCC; 
}
```


####Order the property alphabeticaly
Everyone can do aphabetical order. This will make the property order consistent.


####Modularity
When writing css, it is good to keep in mind and make the component modular. Meaning moving it from a layout to another should not break its style.


####Improve readability with /
With the combination of library like bootstrap and/or js-hook, the class list can be hard to read. Spliting them with a simple '/' improve the readability and force to structure.
```
Instead of
<a class="open-menu btn btn-default js-open-menu btn-lg btn-block ">

Prefer
<a class="open-menu / btn btn-default btn-lg btn-block / js-open-menu">
```


#### Consider BEM or SUIT like convention name
https://css-tricks.com/bem-101/
https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md#ComponentName-descendentName
They both are good solution
It keep the css flat.
It makes the css not tag related.
Component and its hierarchy are easier to identify.
