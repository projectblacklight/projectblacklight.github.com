# projectblacklight.org

Source of the projectblacklight.org site

## To Debug the Site

 1. `jekyll serve`


## Some Things to Note

 * Much of the site data is in the YAML files in `_data/` make edits there.
 * Site level variables are set in  `_config.yml`.

## Adding a Tile to the Examples showcase

### Self-Service

1. Add an entry to the YAML file under `./_data/showcase.yml` with the following format:

  ```ruby
  - name: Example Project
    id: example-project
    img_url: images/showcase/example-project.png
    desc:
    - >
      Brief (max. ~30-50 words) description of your project here.
    url: http://my-url.edu/

  ```

2. Create a 500 x 500 pixel PNG (or JPEG or GIF) image named `example-project.png` that represents "Example Project" and add it to the `images/showcase` directory.

### Full Service

1. Create a 500 x 500 pixel thumbnail for your site. Try to capture a screenshot of something visually interesting and/or unique to your site.
2. Create [a new issue](https://github.com/projectblacklight/projectblacklight.github.com/issues/new) in this project, and include a title, URL for your site, and the thumbnail.
