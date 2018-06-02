# cyberatuc.org

New Cyber@UC website built using Jekyll.

## Installation
You should be able to build and run this site on any OS (though I have not tested with Windows—you'll want to see [this guide](https://jekyllrb.com/docs/windows/)).

### Dependencies
You need to install these before you try to install the site itself:

* **Ruby** (version 2.x) ([instructions](https://www.ruby-lang.org/en/documentation/installation/))
* **Rubygems** (This usually comes with Ruby, so check if the `gem` command already exists. If it doesn't, use [these instructions](https://rubygems.org/pages/download).)
* **Bundler** (`gem install bundler`)
* **ImageMagick** (Your package manager probably has it as either `imagemagick` or `ImageMagick`, or else get it [from their website](https://www.imagemagick.org/script/download.php).)

Here's an easy install script for macOS (assuming you already have [Homebrew](https://brew.sh)):
```
brew install ruby imagemagick
gem install bundler
```

### Building and testing
Once you've got all that installed, just clone the repository and run the install command for dependencies:
```
git clone https://github.com/UCyber/cyberatuc.org.git
cd cyberatuc.org
bundle install
```

To run a web server for local testing, do: `bundle exec jekyll serve`. When the web server is running, the site available at http://localhost:4000/. The web server will automatically rebuild any pages you modify, so you don't need to restart the server all the time—just save your edits and refresh. (N.B. Changes to `_config.yml` do require a server restart.)

If you just want to build the site without running a test server, do: `bundle exec jekyll build`. This will generate all necessary site pages in the `_site/` directory.

For reference, here is the script I use to rebuild the site on my web server every time I commit a new update:
```
#!/usr/bin/env bash
export JEKYLL_ENV=production
cd cyberatuc.org/
git pull
bundle install
jekyll build
```

## Contributing
This site is deliberately set up to be easy to hack on. If you know how to write in Markdown and make commits in Git, you can probably contribute to this website.

To get started, you'll first want to go through the installation process above, and make sure you can build and test the site and that everything loads correctly when you view it in a web browser.

### The basics
See [Jekyll's website](https://jekyllrb.com/) for documentation of the most basic stuff. In particular, the [Directory structure](https://jekyllrb.com/docs/structure/) page is very useful for figuring out where everything is.

One quirk of this project is that we use [jekyll-assets](https://github.com/envygeeks/jekyll-assets) instead of Jekyll's built-in asset management, so if you are embedding an image/script/stylesheet/etc, it might be a little bit different than what Google will tell you. See jekyll-assets' docs at that link (or just look at some of the existing pages and copy from them).

The theme for the site was built from Jekyll's default theme, [minima](https://github.com/jekyll/minima). However, it has been heavily modified to use [Bootstrap 4](http://getbootstrap.com/) (a framework for layout/components/etc). We also use [Font Awesome 5](https://fontawesome.com/) for icons, [jekyll-seo-tag](https://github.com/jekyll/jekyll-seo-tag) for metadata tags, and a couple other plugins for this and that (see the `Gemfile` or the build settings in `_config.yml`). **Be warned:** Bootstrap 4 and Font Awesome 5 are both relatively new versions of that software, so a lot of the info on Google might still be for the previous version.

### Markdown
Blog posts and simple content pages on this site are written in Markdown, a very simple markup language. This is used in Reddit posts, GitHub readmes, etc, and is generally pretty easy and intuitive to figure out. You can find a basic tutorial of how to write in Markdown [here](https://help.github.com/articles/basic-writing-and-formatting-syntax/).

More advanced users might want to know that we are using the GitHub-Flavored Markdown (GFM) dialect, and using [kramdown](https://kramdown.gettalong.org/) to render the HTML, which provides a number of additional features such as table of contents generation, LaTeX math blocks, and more. You might want to check out the [kramdown syntax documentation](https://kramdown.gettalong.org/syntax.html) for info on these advanced features.

### Blog posts
This site uses Jekyll's blog post system, so you may want to read this help page from Jekyll's documentation: [Writing posts](https://jekyllrb.com/docs/posts/).

Basically, blog posts are saved as Markdown files in the `_posts/` directory. At the top of the file is the [YAML Front Matter](https://jekyllrb.com/docs/frontmatter/), which sets a few properties for the page (e.g. title, date, author, etc), and then the rest of the file is just pure Markdown. I recommend simply looking at the existing posts in that folder and copying from them to create new blog posts. Here's a bit of an explanation for each of the properties in the front matter:

* `layout`: This defines what type of page this is; this should always be `post`.
* `categories`: The categories show up as part of the page's URL, so please do not change this value from `blog`.
* `title`: The title for this post that shows up at the top of the page and in the browser's tab name. It's pretty self-explanatory.
* `author`: Username of the author. If this is your first time writing a blog post for the site, you'll need to add an entry for yourself in the `_data/authors.yml` file (see the comment at the top of that file for more info).
* `date`: Should be the approximate time you plan to publish the post (but don't set it in the future—some RSS readers might be freaked out by that)

### Meetings
Unique to the Cyber@UC is the `_meetings` folder, which stores the pages for every meeting in the meetings archive. Meetings are implemented as a Collection in Jekyll, which you can read more about [here](https://jekyllrb.com/docs/collections/).

To create a new meeting page, create a new Markdown file in the `_meetings/` folder and format it just like the other `<number>.md` files there. Put the slides PDF at `files/slides/meeting_001.pdf` (replace 001 with your meeting number). If there are no slides for whatever reason, add `meeting_slides: false` on a new line in the [YAML front matter](https://jekyllrb.com/docs/frontmatter/) in your .md file.

## License
MIT License

Copyright (c) 2018 Hayden Schiff

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
