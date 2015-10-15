# Get started with js\_cols #

To get started with the js\_cols library, download the latest version from http://code.google.com/p/jscols/downloads/list
Unzip the file and place the js\_cols folder in the home folder of your application. Include the file js\_cols/base.js in a script tag:


&lt;script src="js\_cols/base.js"&gt;



&lt;/script&gt;



This will define the variable js\_cols in the global name space. All constructors of the js\_cols library are properties of js\_cols. Furthermore, the function js\_cols.require is defined in the base.js file. This function is used to include the desired classes in your html document like this:
```
<script>   
js_cols.require('js_cols.LinkedList'); 
js_cols.require('js_cols.HashMap'); 
</script>
```

**It is important that the calls to js\_cols.require are placed in their own script tag, which should be closed before writing any code that uses the required parts of the library.**

## Correct usage: ##

```
<script src="js_cols/base.js"></script>
<script>   
js_cols.require('js_cols.LinkedList'); 
js_cols.require('js_cols.HashMap'); 
</script>
<script>   
var map = new js_cols.HashMap();
map.insert(something);
..... do work.......
............
</script>
```

By using the `js_cols.require` function, dependencies are managed such that classes on which other classes depend, are automatically included. Furthermore redundant inclusions and circular references are avoided.