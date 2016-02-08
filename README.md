#Simple CSS guide 

Short recommendation to follow that will make your css easy to maintain

### Never use id for styling
It is not reusable and the specificity is too strong.

### Use Js-hook
Prefix class with "js-" if it is used in js file. It is good practice to not have a class use for both css and js files.
ie: btn brnjs-open-menu. btn is use in for styling. js-open-menu trigger the function that open the menu

### Avoid !important
Try to not use !important. The use of this property is selfish. It remove the css power of specifiy. If there is workaround to not use !important then it is better to spend time on it. You and your teamate will thank you in a coming future.

### Avoid styling on a native tag
Rather create a class and affect the style to it. This way the markeup can be changed without having to touch any css files.

### Keep specificity as flat as possible
The less specifity the easier the css will be to maintain.

###Prefer multiligne css than monoline
Even if it is true that monoline css make the file less long and give the impression to be able to read all the property in a glance. It become quickly very hard to read when it has more than 3-4 property (even worse with the browser prefix one).
Better to make it multiline, easier for developer to read. Mification plugin will make the file in one line anyway.

###Component base
When writing css, it is good to ask yourself if the component has to move from one layout to another, will the style be broken ?

###Improve readability with /
With the combination of library like bootstrap and/or js-hook, the class list can be hard to read. Spliting them with a simple '/' improve the readability and force to structure.


BEM is a good solution methodology
It keep the css flat.
It makes the css not tag related.
Component or its elements is easily identifiable thanks to the naming methodology.



