#Simple CSS guide 

Simple recommendation to follow that will make your css easy to maintain alone or as a team

#### Never use id for styling
Not reusable and the specificity is too strong. Only using class means narrow down the whole css to only one "weight". 


#### Use Js-hook
Prefix class with "js-" if it is used in js file. It is good practice to not have a class use for both css and js files.
```
<a href="#" class="btn btn js-open-menu">Open</a> 
btn is use in for styling. js-open-menu trigger the function that open the menu
```


#### Avoid !important
Try to not use !important. Beside exception, the use of this property is usually selfish. It remove the css power of specifiy. If there is workaround to not use !important then it is better to spend time on it. You and your teamate will thank you in a near future.


#### Avoid styling on a native tag
Better create a class and affect the style to it. This way the markeup can be changed without having to touch any css files.
```
HTML
<div class="card">
	<h1 class="title">TITLE</h1>
</div>

CSS
.card h1{} //Markeup dependant
.card .title{} //Markeup not dependant

```


#### Keep specificity as flat as possible
The less specifity the easier the css will be to maintain.
```
.container .column .bloc .text .paragraph{
	font-size:12px;
}
sadly can be only overwrite by having a 6th class level 
```


####Prefer multiligne css than monoline
Even if it is true that monoline css make the file less long and give the impression to have all the property in a glance. It become quickly very hard to read when it has more than 3-4 property (even worse when it involve browser prefix ).
Better to make it multiline, easier for developer to read. Mification plugin will make the file in one line anyway.
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


####Order the property by type
A css rule sometimes contains lots of property. Agreeing on some categorisation can make it more clear :
```
.selector {
	/* Position */
	position: absolute;
	z-index: 10;
	top: 0;
	right: 0;
	margin: 10px;

	/* Box */
	display: inline-block;
	overflow: hidden;
	width: 100px;
	height: 100px;
	padding: 10px;
	border: 10px solid #333;
	background: #000;
	
	/* Text */
	font-family: sans-serif;
	font-size: 16px;
	line-height: 1.4;
	text-align: right;
	color: #fff

	/* Other */
	cursor: pointer;
}
```


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


#### BEM is a good solution ( for Block Element Modifier)
It keep the css flat.
It makes the css not tag related.
Garanty modularity.

https://css-tricks.com/bem-101/

```
HTML
<div class="card card--border">
	<h1 class="card__title">TITLE</h1>
	<p class="card__description">
		<span class="card__description__text">Lorem ipsum</span>
		<a class="card__description__link">Lorem ipsum</a>
	</p>
</div>

CSS
.card{}
.card--border{}
.card__title{}
.card__description_text{}
.card__description_link{}

Explanation
.card is the Block
.card__title, .card__description__text and .card__description__link are .card Element
.card--border is a Modifier. It allow a variation of the bloc/element 
```

Even if the naming looks lengthy to write at first sight. It become a lot more easier with Sass and its &:
```
.card{

	&__title{}

	&__description{
		&__text{}
		&__link{}
	}

	&--border{}
}
```





