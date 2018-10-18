### ohm
---
.js
https://github.com/harc/ohm

.rb
[!link]


```js
npm install ohm-js
var ohm = require('ohm-js');
var myGrammar = ohm.grammar('MyGrammar { greeting = "Hello" | "Hola" }');

var fs = require('fs');
var ohm = require('ohm-js');
var contents = fs.readFileSync('myGrammar.ohm');
var myGrammar = ohm.grammar(contents);

var userInput = 'Hello';
var m = myGrammar.match(userInput);
if(m.succeeded()){
  console.log('Greetings, human');
}else {
  console.log("That's not a greeting!");
}


```

```html
<script src="ohm.js"></script>

<script type="text/ohm-js">
  MyGrammar {
    greeting = "Hello" | "Hola"
  }
</script>
<script>
  var myGrammar = ohm.grammarFromScriptElemen();
</script>

```

```sh
git clone https://github.com/harc/ohm.git
cd ohm
npm install


```
---
.rb
https://github.com/soveran/ohm

```

```

```ruby

```


```

```


