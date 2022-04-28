# tisane-docs

TODOs:

 - [x] Fill out outline in `_about/research.md`
 - [x] Expand blurb in `_about/index.md`
 - [ ] Reorganize some of the material from install to tutorial
 - [ ]
 - [ ] Create layout for Tisane team members
 - [ ] Investigate a way to embed jupyter notebooks (at least as a patch for writing up more examples lol)


Site structure (pages that have yet to be created have `()` after their relative URL):

 - [x] `/` (`index.md`):
 - [x] `/about` (`_about`)
   - [x] `/about/home/` (`/_about/index.md`): landing page for the About section
   - [ ] `/about/team/` (`/_about/team_members.md`): short bios for all the Tisane developers
   - [x] `/about/research/` (`/_about/research.md`): about the formal research that has been done/will be done/maybe future work, as well as how to cite the project
 - [x] `/docs`: this is actually hosted in the tisane repo
 - [ ] `/install/` (`/_pages/install.md`): detailed installation instructions
 - [ ] `/tutorial/` (need to make into its own section): detailed tutorial
   - [ ] `/tutorial/home/` (`/_tutorial/index.md`): landing page for the Tutorial section, explaining the options
   - [ ] `/tutorial/cli/` (`/_tutorial/cli.md`): tutorial for using Tisane from the command line
   - [ ] `/tutorial/notebook/` (`/_tutorial/notebook.md`): tutorial for using Tisane with Jupyter notebooks
   - [ ] `/tutorial/pigs/` (): the pigs example

## Important files

Here's a mapping of the important top-level files:

 - `_config.yml`: this is where a lot of the metadata for the site lives. Can also configure parts of the website here, define constants used in jekyll, etc.
 - `_data/navigation.yml`: defines which tabs are listed in the top navigation bar. The `sectionid` should be the same as in `_config.yml`
 - `_pages/install.md`: where the installation instructions will go

Files that are grouped into sections are covered in the following sub-sections.

### About pages
The layout of the about pages is determined by `_layouts/about.html`, which also relies on `_includes/about_nav.html`. The latter file creates an accordion-style side navigation bar. The contents of this bar is specified in `_data/about.yml`, in the `nav` object.

The `_data/about.yml` also contains a `team` object, that will be used in the layout of all of the team members' bios. (I have not currently set up the actual little bio template.) The team members will be listed in the `about/team` page (which is specified by the `_about/team_members.md`) file.


## Jekyll basics (because I always forget how to use Jekyll)
Terms:

 - "front matter": a YAML-style dictionary that is contained between `---` and `---` on `.html` and `.md` files. This can be used to set some constants that will be used for the page, such as the title of a page, or use the jekyll redirect-from plugin to make sure that pages have canonical URLs.

To access the yml files in `_data`, use `site.data.<name of yml file without .yml>`.

The files in `_layouts` provide template layouts for other files. The contents of a file using a template will be inserted wherever the `{{ contents }}` directive is in the layout. Layouts are used by specifying `layout: <my layout without .html extension>` in the "front matter" of a page.





# Jekyll Doc Theme

Go to [the website](https://aksakalli.github.io/jekyll-doc-theme/) for detailed information and demo.

## Running locally

You need Ruby and gem before starting, then:

```bash
# install bundler
gem install bundler

# clone the project
git clone https://github.com/aksakalli/jekyll-doc-theme.git
cd jekyll-doc-theme

# install dependencies
bundle install

# run jekyll with dependencies
bundle exec jekyll serve
```

### Theme Assets

As of the move to support [Github Pages](https://pages.github.com/) a number of files have been relocated to the `/asset` folder.
- css/
- fonts/
- img/
- js/
- 404.html
- allposts.html
- search.json

## Docker

Alternatively, you can deploy it using the multi-stage [Dockerfile](Dockerfile)
that serves files from Nginx for better performance in production.

Build the image for your site's `JEKYLL_BASEURL`:

```
docker build --build-arg JEKYLL_BASEURL="/your-base/url" -t jekyll-doc-theme .
```

(or leave it empty for root: `JEKYLL_BASEURL=""`) and serve it:

```
docker run -p 8080:80 jekyll-doc-theme
```

## Github Pages

The theme is also available to [Github Pages](https://pages.github.com/) by making use of the [Remote Theme](https://github.com/benbalter/jekyll-remote-theme) plugin:

**Gemfile**
```
# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
gem "github-pages", group: :jekyll_plugins
```

**_config.yml**
```
# Configure the remote_theme plugin with the gh-pages branch
# or the specific tag
remote_theme: aksakalli/jekyll-doc-theme@gh-pages   
```

### Theme Assets

Files from your project will override any theme file with the same name.  For example, the most comment use case for this, would be to modify your sites theme or colors.   To do this, the following steps should be taken:

1) Copy the contents of the `aksakalli/jekyll-doc-theme/asset/css/main.scss` to your own project (maintaining folder structure)
2) Modify the variables you wish to use prior to the import statements, for example:

```
// Bootstrap variable overrides
$grid-gutter-width: 30px !default;
$container-desktop: (900px + $grid-gutter-width) !default;
$container-large-desktop: (900px + $grid-gutter-width) !default;

@import // Original import statement
  {% if site.bootwatch %}
    "bootswatch/{{site.bootwatch | downcase}}/variables",
  {% endif %}

  "bootstrap",

  {% if site.bootwatch %}
    "bootswatch/{{site.bootwatch | downcase}}/bootswatch",
  {% endif %}

  "syntax-highlighting",
  "typeahead",
  "jekyll-doc-theme"
;

// More custom overrides.
```

3) Import or override any other theme styles after the standard imports

## Projects using Jekyll Doc Theme

* http://teavm.org/
* https://ogb.stanford.edu/
* https://griddb.org/
* https://su2code.github.io/
* https://contextmapper.org/
* https://launchany.github.io/mvd-template/
* https://knowit.github.io/kubernetes-workshop/
* https://rec.danmuji.org/
* https://nethesis.github.io/icaro/
* http://ai.cs.ucl.ac.uk/
* http://tizonia.org
* https://lakka-switch.github.io/documentation/
* https://cs.anu.edu.au/cybersec/issisp2018/
* http://www.channotation.org/
* http://nemo.apache.org/
* https://csuf-acm.github.io/
* https://extemporelang.github.io/
* https://media-ed-online.github.io/intro-web-dev-2018spr/
* https://midlevel.github.io/MLAPI/
* https://pulp-platform.github.io/ariane/docs/home/
* https://koopjs.github.io/
* https://developer.apiture.com/
* https://contextmapper.github.io/
* https://www.bruttin.com/CosmosDbExplorer/
* http://mosaic-lopow.github.io/dash7-ap-open-source-stack/
* http://www.vstream.ml/
* http://docs.fronthack.com/
* https://repaircafeportsmouth.org.uk/
* http://brotherskeeperkenya.com/
* https://hschne.at/Fluentast/
* https://zoe-analytics.eu/
* https://uli.kmz-brno.cz/
* https://lime.software/
* https://weft.aka.farm
* https://microros.github.io/
* https://citystoriesucla.github.io/citystories-LA-docs
* http://lessrt.org/
* http://kivik.io/
* https://www.iot-kit.nl/
* http://justindietz.com/
* https://universalsplitscreen.github.io/
* https://docs.oneflowcloud.com/
* https://actlist.silentsoft.org/
* https://teevid.github.io
* https://developer.ipums.org
* https://osmpersia.github.io (right-to-left)
* https://ecmlpkdd2019.org
* https://idle.land
* https://mqless.com
* https://muict-seru.github.io/
* https://www.invoice-x.org
* https://www.devops.geek.nz

## License

Released under [the MIT license](LICENSE).
