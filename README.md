# Activerecord::DatabaseValidations

Add validations to your ActiveRecord models based on your database constraints.

## Installation

Add this line to your application's Gemfile:

    gem 'activerecord-database_validations'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install activerecord-database_validations

## Usage

You can use ActiveModel's `validates` method to define what fields you want
to validate based on the database constraints.

``` ruby
class Foo < ActiveRecord::Base
  validates :string_field, :boolean_field, database_constraints: true
end
```

You can also use `validates_database_constraints_of`:

``` ruby
class Bar < ActiveRecord::Base
  validates_database_constraints_of :my_field
end
```

Validations will be added in these cases:

- For textual fields that have a limit, a `LengthValidator` will be added.
- For NOT NULL fields, a `PresenceValidator` will be added.

## Contributing

1. Fork it ( http://github.com/wvanbergen/activerecord-database_validations/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
