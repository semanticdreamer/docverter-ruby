# Docverter

This is the official Docverter Ruby API.

## Installation

Add this line to your application's Gemfile:

    gem 'docverter'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install docverter

## Usage

First, install [Docverter Server](https://github.com/docverter/docverter). 

Set your base url before using any of the rest of the library:

    Docverter.base_url = <BASE-URL>

In a Rails project, put this in an initializer.

A few example conversions:

    Docverter::Conversion.run("markdown", "html", "Some Content")
    # => "<html><body><p>Some Content</p></body></html>"

    Docverter::Conversion.run do |c|
      c.from    = "markdown"
      c.to      = "html"
      c.content = "Some Content"
      c.stylesheet = "stylesheet.css"
      c.add_other_file "stylesheet.css"
    end
    # => '<html><head><link rel="stylesheet" media="print" href="stylesheet.css"></head><body><p>Some Content</p></body></html>'
    
See the documentation for `Docverter::Conversion` for more details.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
