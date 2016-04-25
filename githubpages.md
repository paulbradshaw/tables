# How to create a webpage using GitHub 

GitHub offers free webpage hosting under the name '[GitHub Pages](https://pages.github.com/)'. 

To create them you just need a normal GitHub account.

## Start by creating a repository (folder)

*If you already have a repository for your project in GitHub, skip this stage.*

The simplest way to get started is to create a 'repository' (also called 'repo'), basically a new project folder. 

To do this, click on the plus icon in the upper right corner of the screen and select **New repository**:

![](https://raw.githubusercontent.com/paulbradshaw/tables/master/Screen%20Shot%202016-04-25%20at%2015.39.51.png)

Or, click on the **Repositories** tab and then click the bright green 'New' button:

![](https://github.com/paulbradshaw/tables/blob/master/reponew.png)

Give your repository a meaningful, but short, name without spaces. This will be used in two ways:

The repository itself will be at an address which is GitHub.com/YOURUSERNAME/reponame. 

But the GitHub Pages website will be at an address which is YOURUSERNAME.github.io/reponame

By way of example, the repository containing this tutorial can be found at:

[https://github.com/paulbradshaw/tables](https://github.com/paulbradshaw/tables)

But if I then create a site for the same repository it will be at this URL:

[https://paulbradshaw.github.io/tables](https://paulbradshaw.github.io/tables)

## Create a GitHub Pages site

That's the repo made, but to create a GitHub Pages site, do the following:

![](https://raw.githubusercontent.com/paulbradshaw/tables/master/reposettings.png)

1. Click on the **Settings** tab
2. Scroll down and click on the button **Launch automatic page generator**

![](https://github.com/paulbradshaw/tables/blob/master/githubautopage.png)

You will now be asked to customise three elements: 

* The name (used as the page title and the first heading on the resulting page)
* A tagline (typically be placed in a Heading 2 tag underneath that)
* And the body for the main page (the main text)

The body area will be filled with Markdown that begins `### Welcome to GitHub Pages`. You can delete this and type in your own body text. In that case you will need to use Markdown: [GitHub provides a guide here](https://help.github.com/categories/writing-on-github/)

Alternatively, if you have a 'readme.md' file in your repository, you can choose to use this as your webpage body text too.

![](https://github.com/paulbradshaw/tables/blob/master/githugpages_readme.png)

Once you're happy with that (you can edit this at any time later anyway), click **Continue to layouts**.

Choose a layout that you want (the simpler the better, generally), and finish the process.

## Finding and editing your new webpage

Repositories in GitHub can have various '*branches*': these are typically different versions of a project. When creating a GitHub Pages site for your project, it is stored in one of these branches.

To find your new site, then, you will need to switch from the 'master' branch to the branch called '**gh-pages**' using the drop-down menu above the list of files in your repo:

![](https://github.com/paulbradshaw/tables/blob/master/githubbranches.png)

Once select, the view should change. You should see two files in this branch: `index.html` and `params.json`, and two folders: `javascripts` and `stylesheets`. If you had images in your body text then there will also be an `images` folder.

![](https://github.com/paulbradshaw/tables/blob/master/pagesview.png)

Once you are in this branch you can edit those files like you can any others in GitHub, by clicking on the file name, and then on that page clicking on the pencil 'edit' icon to the right (currently between the 'Desktop' icon and the 'bin' icon).

You can also upload extra files (HTML files, images, CSS or JavaScript files for eaxmple) as you can normally in GitHub, by dragging them from your computer onto the GitHub Branches branch of the repo.

But remember, to actually *see* the webpage, you will need to change the URL to your username followed by `.github.io/`, followed by the repo name.
