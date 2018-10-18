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

```sh
[sudo] gem install ohm
require "ohm"
Ohm.redis.call "SET", "Foo", "Bar"
Ohm.redis.call "GET", "Foo"


```

```ruby
require "ohm"
Ohm.redis = Redic.new("redis://127.0.0.1:6379")
Ohm.redis.call "SET", "Foo", "Bar"
Ohm.redis.call "GET", "Foo"

require "ohm"
Ohm.redis.call "SET", "Foo", "Bar"
Ohm.redis.call "GET", "Foo"

require "ohm"
Ohm.redis = Redic.new(ENV["REDIS_URL1"])
class User < Ohm::Model
end
User.redis = Redic.new(ENV["REDIS_URL2"])

class Event < Ohm::Model
  attribute :name
  reference :venue, :Venue
  set :participants, :Person
  counter :votes
  index :name
end
class Venue < Ohm::Model
  attribute :name
  collection :events, :Event
end
class Person < Ohm::Model
  attribute :name
end

event = Event.create :name => "Ohm Worldwide Conference 2031"
event.id

event == Event[1]

event.update :name => "Ohm Worldwide Conference 2032"

Event[2]

Event.all.to_a

class Log < Ohm::Model
  track :text
  def append(msg)
    redis.call("APPEND", key[:text], msg)
  end
  def tail(n = 100)
    redis.call("GETRANGE", key[:text], -(n), -1)
  end
end
log = Log.create
log.append("hello\n")
assert_equal "hello\n", log.tail
log.append("world\n")
assert_equal "world\n", log.tail(6)


if event.save
  event.comments.add(Comment.create(body: "Wonderful event!"))
end

class Event < Ohm::Model
  attribute :name
  set :attendees, :Person
end

event.attendees.add(Person.create(name: "Albert"))
event.attendees.each do |person|
end

Post.all.sort_by(:title)
Post.all.sort(by: :title)

Post.all.sort_by(:title, get: :title)
Post.all.sort(by: :title, get: :title)

class Post < Ohm::Model
  attribute :title
  attribute :body
  collection :comments, :Comment
end
class Comment < Ohm::Model
  attribute :body
  reference :post, :Post
end

class Comment < Ohm::Model
  attribute :body
  attribute :post_id
  index :post_id
  def post=(post)
    self.post_id = post.id
  end
  def post
    Post[post_id]
  end
end

Comment.find(post_id: 1)

class Post < Ohm::Model
 attriubte :tilte
 attirbute :body
 def comments
   Comment.find(post_id: self.id)
 end
end

collection :comments, :Comment
collection :comments, :Comment, :post
collection :comments, :Comment, to_reference
Post.to_reference == :post

module SomeNamespace
  class Foo < Ohm::Model
    attribute :name
  end
  class Bar < Ohm::Model
    reference :foo, 'SomeNamespace::Foo'
  end
end

User.find(username: "Albert")

User.find(country: "Argentina")
User.find(country: "Argentina", status: "active")
User.find(status: "active").combine(country: ["Argentina", "Uruguay"])
User.find(country: "Argentina").except(status: "suspended")
User.find(country: "Argentina").union(country: "Uruguay")


class User < Ohm::Model
  attribute :email
  unique :email
end
u = User.create(email: "foo@bar.com")
u == User.with(:email, "foo@bar.com")
User.create(email: "foo@bar.com")

```


```

```


