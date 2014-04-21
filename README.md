# Pelican-iliork

Pelican-iliork is a single-column theme for [pelican][], targeting at blog writing. The primary goal of pelican-iliork is to provide simplicity and readability.

Pelican-iliork is built on [Bootstrap][] version 3.0. Some notable features are:

- Support for bootstrap theme, checkout [Screen Shots][] below
- Support for css overwriting
- Support for nestable menu items
- Support for Google custom search
- Support for multi-author

You can get a live demo at [iliork][], using [flatly][], mainly in Chinese. For more demos, see [Screen Shots][] below.

# Why did you fork it?

As far as I can tell, there is nothing in the current version of Pelican that allows you to override a specific part of the theme. Additionally -- I assume (?) because it was originally intended for use on Chinese language websites, pelican-iliork contains the following line:

	p {
		word-break: break-all;
		/*hyphens: auto;*/
		/*-ms-hyphens: auto;*/
		/*-webkit-hyphens: auto;*/
		/*-moz-hyphens: auto;*/
	}

Making it impossible to read any text on the site I'm using this in. So, much to my chagrin, I had to fork the original and hack on it in order to comment out a single line.

Additionally, I'll probably add some site-specific templates.

# Features

## Use Bootstrap Theme

You can change the default appearance of Bootstrap to any Bootstrap theme you like. `BS3_THEME` defines the url of the theme's css file; `BS3_THEME_NAME` and `BS3_THEME_HOMEPAGE` define the name and url of bootstrap theme, which are used in the footer text.

See [Screen Shots][] for demos. For more theme to choose from, have a look at [Bootswatch][].

    # using flatly of bootswatch.com
    BS3_THEME = 'http://bootswatch.com/flatly/bootstrap.min.css'
    BS3_THEME_NAME = 'Flatly'
    BS3_THEME_HOMEPAGE = 'http://bootstrap.com/flatly'

## Use CSS Overwriting

You can use your own css file for code highlight. If you do not provide this value, pelican-iliork will the default css file, `code.css`.

Pelican-iliork provides a easy to way to overwrite the css style of pelican-iliork by providing `CODE_HIGHLIGHT` and `CSS_OVERWRITE`. When switching Boostrap themes, you may find these useful.

For example, if you want to use your preferred code highlight css, set the following option in your `pelicanconf.py`

    CODE_HIGHLIGHT = 'url to your favorite code highlight css'

If you want to overwrite the css style of pelican-iliork iteself, use

    CSS_OVERWRITE = 'url to your css'

## Nestable menu items

Menu items in pelican-iliork is nestable. `MENUITEMS` are rendered as a top navbar. Nested menu items are rendered together as a drop-down button on the top navbar. But only 1-level nesting is allowed; it's clumsy, and perhaps wrong, to nest too much items in the menu. Here's a example.

    MENUITEMS = [
        ('Home', '/'),
        ('Archives', [
            ('Tags', '/tags.html'),
            ('Categories', '/categories.html'),
            ('Chronological', '/archives.html'),
            ]),
        ('Social', [
            ('Email', 'url to your email'),
            ('Github', 'url to your github'),
            ('Facebook', 'url to your facebook'),
            ]),
        ]

## Google custom search

Put following in your MENUITEMS to have a Google custom search box on top navbar. 'Search' is the key, mandatory.

    MENUITEMS = [
        ('Search', 'your Google custom search value'),
        ]

## Favicon

To use your favicon, set following option in `pelicanconf.py`

    FAVICON = u'url to your favicon'

## Multi-author
You can direct the author link to whichever you want. It's not hard-coded in the theme.

    AUTHORS = {
        u'jack': '/about.html',
        u'mary': 'http://mary.info',
        u'tony': 'http://tony.me',
    }

# Screen Shots

pelican-iliork with default boostrap theme

![default](./screenshot/default.png)

pelican-iliork with [amelia][]

![amelia](./screenshot/amelia.png)

pelican-iliork with [cosmo][]

![cosmo](./screenshot/cosmo.png)

pelican-iliork with [superhero][]

![superhero](./screenshot/superhero.png)

pelican-iliork with [united][]

![united](./screenshot/united.png)

[pelican]: https://github.com/getpelican/pelican
[pelican-elegant]: https://github.com/talha131/pelican-elegant
[Bootstrap]: http://getbootstrap.com
[KISS]: http://en.wikipedia.org/wiki/KISS_principle
[DRY]: http://en.wikipedia.org/wiki/Don%27t_Repeat_Yourself
[iliork]: http://blog.iliork.com
[Bootswatch]: http://bootswatch.com
[flatly]: http://bootswatch.com/flatly/
[amelia]: http://bootswatch.com/amelia/
[cosmo]: http://bootswatch.com/cosmo/
[superhero]: http://bootswatch.com/superhero/
[united]: http://bootswatch.com/united/
[Screen Shots]: #screen-shots
