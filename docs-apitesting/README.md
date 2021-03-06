# TestStudio for APIs Documentation

This repository contains the common infrastructure for building markdown documentation with [Jekyll](http://jekyllrb.com/).

## Deploymnet and Testing

 - When a new commit is pushed to this repository, a webhook starts this Jenkins job: [Deploy.Apitesting.Documentation](http://ts-bpc01.telerik.com/job/Deploy.Apitesting.Documentation/)
 - The Jenkins job pulls the latest version of the documentation on the slave machine, builds the documentation, creates a deployment package and initiates deployment of this package on the Test encironment.
 - You can see the deployment environments here: [http://deploy.telerik.com/web/dashboard/documentation/stacks/teststudioapis.docs](http://deploy.telerik.com/web/dashboard/documentation/stacks/teststudioapis.docs)
 - Once the deployment on the Test environment is completed, you can test it against: [http://testdocs.telerik.com/teststudio-apis/](http://testdocs.telerik.com/teststudio-apis/)
 - Once testing against Test is completed, you can trigger on demand promotion to the Live environment using the [deploy tool's user interface](http://deploy.telerik.com/web/dashboard/documentation/stacks/teststudioapis.docs).

## Installation

1. Add a new git remote to the documentation repository
2. Install Ruby 2.3.x - http://rubyinstaller.org/downloads/ -  x86 platform select add to Path Variables 
3. Download Ruby DEVELOPMENT KIT - http://rubyinstaller.org/downloads' and follow the instructions
at 'http://github.com/oneclick/rubyinstaller/wiki/Development-Kit'  x86 platform
3. Run it to extract it somewhere (permanent). Then cd to it, run **ruby dk.rb init**, **ruby dk.rb install** and **devkitvars.bat** to bind it to ruby installations in your path.
6. Install [Visual Studio Code](https://code.visualstudio.com/Download) to edit markdown documents 
7. Open a cmd terminal.
8. `cd` to the directory where your markdown documentation repository is.
9. Open the "_config.yml" file and set the `baseurl` and `url` attributes. The first is used for resolving the path to images and hyperlinks. The second is the online URL of the documentation and is used for creating `sitemap.xml`.
         
         url: "http://docs.telerik.com/"
         baseurl: "/teststudio-apis"

10. Create a Google Custom Search Engine (or ask one to be created for you). Set the `google_custom_search` attribute in "_config.yml". If you forget this step the search results will be from the Kendo UI documentation.
11. Run `build.cmd` and then `run.cmd` (from CMD, not with double-click on the bat files). After a while jekyll build the documentation and start a web server at `http://<Your Computer Name>:801/teststudio-apis/`. You can now view the documentation in your browser.
12. If you want your documentation to be indexed much faster - submit your urls here - https://www.google.com/webmasters/tools/submit-url


Jekyll builds a static HTML site in the `_site` directory. This contents of this directory can be deployed on a live server. 

> Important: Jekyll creates .html pages by default. However the documentation creates links without .html extension. 
 A `web.config` with rewrite rules is included out of the box. 

## Configure documentation in IIS Server 
1. Install [URL Rewrite Module 2.0 for IIS (x64)](https://www.microsoft.com/en-us/download/confirmation.aspx?id=47337)
1. Create application **Documentation** under **Default Web Site**
2. Set **Physical Path** to  **<Documentation Repository>\_site** folder
3. You can browse the **documentation** at `http://<Your Computer Name>/documentation/`

## Some Jekyll info

Jekyll is a tool for creating static html web sites. It supports markdown which makes it a good fit for our needs. It is also highly customizable which makes delivering new documentation features a breeze.

[Command References](http://guides.rubygems.org/command-reference/)

### Jekyll Directory structure

#### _assets

Contains CSS and JavaScript files.

#### _includes

Contains common include files used by the layout pages. Not included in the final output in the `_site` directory.

#### _layouts

The layout pages used by the documentation site. They define the common HTML which contains navigation, search and other common UI. Not included in the final output.

#### _plugins

Contains [Jekyll plugins](http://jekyllrb.com/docs/plugins/) (Ruby classes) which are needed for producing the final output. Not included in the final output. 

#### images

Contains images used in the web site.

#### fonts

Custom fonts used in the web site.

The following plugins are currently available:

* breadcrumb.rb - renders breadcrumb navigation
* markdown_processor.rb - creates HTML from Markdown using [html-pipeline](https://github.com/jch/html-pipeline). We are not using the default markdown conversion as we need to tweak the output to our needs.
* navigation_generator.rb - creates a JSON TOC file used for the left-hand treeview navigation.
* redirect_generator.rb - creates IIS redirect rules in the `web.config` to handle the `previous_url` attribute. 
* sitemap_generator.rb - creates sitemap.xml which is used by search engines for crawling.
* slug.rb - gets the URL of a help article from its slug.

#### assets

Contains CSS, JavaScript and image files used by the documentation. Included in the final output.

### Which files from the common documentation repository can be changed?

Any file can be changed per your requirements. However you will have to handle merge conflicts once you need to update to the latest documentation base changes. The following files are likely to be customized:

* _layouts/index.html
* _layouts/page.html
* assets/css/styles.css
* _config.yml

## Writing markdown documents

### Files and directories

You can organize your help topics in directories. The directory and filename will determine the final url of your topic. For example `getting-started/introduction.md` will lead to `getting-started/introduction`

### Markdown content

#### Front matter (headers)
Your markdown file must start with the so called "front matter". This is some metadata used by jekyll and the documentation. Here is an example.

         ---
         title: Getting started
         page_title: Getting started with Kendo UI
         description: Installation and getting started instructions for Kendo UI
         position: 0
         slug: getting-started
         previous_url: /introduction/start
         ---

The supported attributes are:

##### title (required)

Determines the text displayed in the TOC navigation (the treeview in the left).

##### page_title (optional but recommended)

The contents of the `<title>` in the final output. If `page_title` is not set the value of `title` is usded. Blade name was `meta_title`.

##### description (optional but recommended)

Used to set the contents of the `<meta name="description">` in the final output. Improves SEO. Blade name was  `meta_description`.

##### position (optional)

The position this document will appear at in the TOC navigation. Blade name was `ordinal`.

##### slug (optional)

The optional unique identifier of the page. Can be used to link to the current page `[Getting-started]({% slug getting-started%})`

##### previous_url

The previous URL of this page. Used to create IIS redirect rules in `web.config`. Supports comma separated values if there is more than one previous url `previous_url: /foo/bar, /bar/foo`.

#### Content

You can write markdown, plain text or html as a content. If you include code snippets use the following syntax for sleek looks:

{% highlight `language` %}
...put your code in here....
{% endhighlight %}

tested language types include : c#, html, sql, xml, ruby

### Customizing the TOC

The TOC displays an entry for all directories and files. 

#### Files

The the `title` attribute of the markdown file determines the text displayed for that file in the TOC. The `position` attribute determines its position in the TOC. If `position` is not set the file will appear in its alphabetical order after all directories.

#### Directories

By default directories come before the files which don't have `position` set. The directory name determines the text displayed in the TOC. To change it you have to add an entry in `_config.yml` under `navigation`.

For example we want the `introduction/getting-started` directory to appear as `Getting Started` in the TOC. Open `_config.yml` and find the `navigation` attribute. Add a new item:

```
navigation
-
   introduction/getting-started
       title: Getting Started
```

Directories appear alphabetically sorted by default. You can change their position again from `_config.yml`.
```
navigation
-
   introduction/getting-started
       title: Getting Started
       position: 0
```