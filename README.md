
# Cake Wallet Guides

[Read the guides](https://guides.cakewallet.com)!

Forked from Just the Docs. MIT licensed.

## Contributing

Contributing is encouraged! You can contribute in the simple markdown format.

Please follow these guidelines:

1. Be polite!
2. Make the changes clean and simple.
3. Reuse existing images wherever possible.
4. Use clear instructions.

### Data locations

Pages are located under `\docs`. Images are located under `\assets\images\`

### Linking images

When linking images, follow a format like this:

`[![Image name](/images/image.jpg){:width="32%"}](/images/image.jpg)`

This will format the image to 1/3 of the width of the screen, and it will allow a user to click on the image to get a full-screen view.

In select circumstances (such as short, wide images), it's better to make the image full-width. To do this, delete `{:width="32%"}` from the formatting above.

### Linking videos

When linking videos on YouTube, follow a format like this:

`[![Video name](https://img.youtube.com/vi/pbQD7McNTxc/maxresdefault.jpg)](https://www.youtube.com/watch?v=pbQD7McNTxc)`

Replace both instances of `pbQD7McNTxc` with the video you need to add. This will display the YouTube thumbnail of the same video, which a user can click on to open the video.

## Cake Wallet community

Join the Cake Wallet community! https://t.me/cakewallet

---

## Updating

Simply edit the relevant line(s) in the `Gemfile`.

You will need to have Ruby installed locally, and then run `bundle install` in the folder.

## Adding a plugin

The Just the Docs theme automatically includes the `jekyll-seo-tag` plugin.

To add an extra plugin, you need to add it in the `Gemfile` *and* in `_config.yml`. For example, to add `jekyll-default-layout`:

- Add the following to your site's `Gemfile`:

  ```ruby
  gem "jekyll-default-layout"
  ```

- And add the following to your site's `_config.yml`:

  ```yaml
  plugins:
    - jekyll-default-layout
  ```

## Building and previewing your site locally

Assuming Jekyll and Bundler are installed on your computer:

1.  Change your working directory to the root directory of your site.

2.  Run `bundle install`.

3.  Run `bundle exec jekyll serve` to build your site and preview it at `localhost:4000`.

    The built site is stored in the directory `_site`.

## Licensing and Attribution

This repository is licensed under the MIT License. You are generally free to reuse or extend upon this code as you see fit; just include the original copy of the license.
