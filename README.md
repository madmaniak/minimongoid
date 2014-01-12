#minimongoid

## Installation

Download [minimongoid.coffee](https://github.com/madmaniak/minimongoid/blob/master/minimongoid.coffee) and place it in ```lib/```into your Meteor app.

Dont forget to install the `coffeescript` package:

```sh
meteor add coffeescript
```

## Usage

```coffeescript

class User extends Minimongoid
  isValid: ->
    @attributes.name.length >= 3

# Haters gonna hate!
User.new(name: 'Bob').save()

User.create name: 'Bob' # => User
User.create name: '' # => false

User.where(name: 'Bob').toArray() # => [User]

User.count() # => 1
```

Be sure to checkout the [implementation](https://github.com/haihappen/minimongoid/blob/master/minimongoid.coffee) for the full API.

## Testing

For now, you can test it using the meteor packages test suite. Copy the whole folder to your `/local/copy/of/meteor/packages` folder, and then run `../../meteor` from inside the `minimongoid` folder. Visit [localhost:3000](localhost:3000) to run the test suite. (Running the whole Meteor test suite isn't supported, cause minimongoid is implemented in CoffeeScript.)

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
