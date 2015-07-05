Petroglyph
==========
[![Build Status](https://travis-ci.org/polybuildr/petroglyph.svg?branch=master)](https://travis-ci.org/polybuildr/petroglyph)
***
Petroglyph is a Python-based static blog generator. (Tested on 2.7.6).
***
## Setting up a blog

1. Create a new directory for your blog.

  ```sh
  $ mkdir awesomeblog
  ```
2. Inside this new directory, run `petroglyph init` and fill in the details.

  The default theme is `monoblue`. If you want to use a different skin (`monogreen`, `monopurple` and `monored` included by default), run `petroglyph init --skin SKIN`.
  ```sh
  $ cd awesomeblog
  $ petroglyph init --skin monopurple
  Copying skin 'monopurple'...
  Creating posts directory...
  Configuring settings...
  Blog title: Awesome Blog
  Blog author: John Doe
  Blog description: The awesome blog!
  Saved configuration in config.yaml.
  Petroglyph initialized.
  ```
  At any point if you want to replace your skin or change the configuration, run `petroglyph init` again.

3. Write a new post in the `/posts` directory with a `.md` extension. (reStructuredText is also supported, give the file an `.rst` extension.) Each post's filename will be used as the post's slug when the blog is generated. Markdown support is provided using [Mistune](https://github.com/lepture/mistune). Include post metadata by writing posts as follows:

  ```
  ---
  title: The Post's Title
  tags: some-tag, another-tag
  ---
  Hello, world! **Bold**, _italics_ and `code`.

  This part will be before the 'Read more'.

  <!--more-->This part will come after the read more.
  ```
  > A post title is **required**.

  > Petroglyph uses the last modified time of a file when deciding the post publish date. If you'd like to use a custom date, add it to the metadata in the `YYYY-MM-DD` format.
  ```
  date: 2015-06-07
  ```
4. Dry run petroglyph to see if everything works fine.
  ```sh
  $ petroglyph --dry-run
  Found 1 post.
  1 new post.
  ```

5. Run petroglyph!
  ```sh
  $ petroglyph
  Found 1 post.
  1 new post.
  Generated 1 new post.
  Done.
  ```
  > If you ever want to regenerate all your pages (because of a theme change, for example), run `petroglyph --regenerate`.

6. Your blog is ready to be served in the `blog/` directory.
  ![](https://github.com/ashumeow/petroglyph/blob/gh-pages/screenshot.gif)
