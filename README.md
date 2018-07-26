# Jekyll Target Blank

![Jekyll Target Blank Logo](assets/logo.png "Jekyll Target Blank")

Automatically adds a `target="_blank" rel="noopener noreferrer"` attribute to all __external__ links in Jekyll Content. [Read more..](https://keith-mifsud.me/projects/jekyll-target-blank)

[![Gem Version](https://badge.fury.io/rb/jekyll-target-blank.svg)](https://badge.fury.io/rb/jekyll-target-blank)
[![Build Status](https://travis-ci.org/keithmifsud/jekyll-target-blank.svg?branch=master)](https://travis-ci.org/keithmifsud/jekyll-target-blank)

## Installation

Add the following to your site's `Gemfile`

```
gem 'jekyll-target-blank'
```

And add the following to your site's `_config.yml`

```yml
plugins:
  - jekyll-target-blank
```

Note: if `jekyll --version` is less than `3.5` use:

```yml
gems:
  - jekyll-target-blank
```

## Usage

By default all anchor tags and markdown links pointing to an external host, other than the one listed as `url` in jekyll's `_config.yml` will automatically open in a new tab once the site is generated.

This includes pages, posts and collections. __Plain text links are not included__.

### Examples

#### HTML

The following html anchor tag:

```html
<a href="https://google.com">Google</a>
```

will be replaced with:

```html
<a href="https://google.com" target="_blank" rel="noopener noreferrer">Google</a>
```

..unless your website's URL is google.com 😉

#### Markdown

```markdown
[Google](https://google.com)
```

will be generated as:

```html
<a href="https://google.com" target="_blank" rel="noopener noreferrer">Google</a>
```

### Configuration

#### Override the default behaviour

You can override the default behaviour and only force external links to open in new browser if they have a css class name with the same value as the one listed in the Jekyll `_config.yml` file.

To override the automation, add the following entry in your site's `config.yml` file, specifying which css class a link should have for it to be forced to open in a new browser:

```yaml
target-blank:
    css_class: ext-link
```

With the above setting, only links containing the `class="ext-link"` will be forced to open in a new browser.

#### Automatically add additional CSS Classes

You can also automatically add additional CSS classes to qualifying external links. This is useful if say you want to add CSS styling to external links such as automatically displaying an icon to show the reader that the link will open in a new browser.

You can add one or more __space__ separated CSS classes in `_config.yml` like so:

 ```yaml
 target-blank:
     add_css_classes: css-class-one css-class-two
 ```
 
 ####' Override the default rel attributes
 
 For security reasons, the default behaviour adds `rel="noopener noreferrer"` to all the processed external links. You can override adding any of the `noopener` and `noreferrer` values with the following entries in your site's `_config.yml` file. 
  
 __To exclude the `noopener` value:__
 
 ```yaml
target-blank:
    noopener: false
```

__To exclude the `noreferrer` value:__
 
 ```yaml
target-blank:
    noreferrer: false
```

__To exclude both `noopner` and `noreferrer` values:__
 
 ```yaml
target-blank:
    noopener: false
    noreferrer: false
```

 
## Support

Simply [create an issue](https://github.com/keithmifsud/jekyll-target-blank/issues/new) and I will respond as soon as possible.


## Contributing

1. [Fork it](https://github.com/keithmifsud/jekyll-target-blank/fork)
2. Create your feature branch (`git checkout -b my-new-feature)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (git push origin my-new-feature)
4. Create a new Pull Request


### Testing

```bash
rake spec
# or
rspec
```

## Credits

The logo illustration was <a href="http://www.freepik.com">Designed by Freepik</a>. Thank you ❤️


## Legal

This software is distributed under the [MIT](LICENSE.md) license.

&copy; 2018 - Keith Mifsud <https://keith-mifsud.me> and approved contributors.
