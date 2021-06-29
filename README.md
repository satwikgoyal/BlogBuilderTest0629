# DACSS Course Website

This is the generic DACSS course website GitHub. Students will create a templated repository, work in RStudio to create new posts, and then commit and push the changes prior to submitting a pull request to main repository. 

# Instructions

Note: this assumes you have setup Git and RStudio and have basic knowledge of how to use Git. Please watch the following [videos](https://youtube.com/playlist?list=PL6fG9co6nK8ebkhWSS11z9MWKzRdoqzoT) or follow a basic Git guide first to set everything up.

## Forking the Repository

First you will need to fork the repository. You can do that by clicking the `Fork` icon on the top right corner of the DACCS repo page.

![fork](_guide/images/fork.png)

If prompted to choose a user, choose your main GitHub account.

After you have forked the repo, you will have your 'own' version of the repo page to edit; any changes made to this repo will not affect the main DACSS repo. Before heading over to RStudio and making changes, make sure to clone the repo by using the repo HTTP link with a new RStudio project.

## R Package Requirements

You will need to have the `distill` and `postcards` packages first.

- [Distill](https://rstudio.github.io/distill/) will easily allow you to make posts to the blog.
- [Postcards](https://github.com/seankross/postcards) will easily enable you to create a personalized 'About Me' page for the blog.

Make sure you install the packages with `install.packages` like so:

```
install.packages('distill')
install.packages('postcards')
```

And load the libraries before proceeding further:

```
library(distill)
library(postcards)
```

## Creating a New Post with Distill

You can create a post by using the `create_post` function from Distill. It takes in [multiple arguments](https://rdrr.io/cran/distill/man/create_post.html) but I would recommend utilizing `title` and `author` at least.

For example I can do:

```
create_post(title = 'iris', author = 'Hans Quiogue')
```

The package will easily generate an R Markdown file for you to edit and use as a template for your post. Now, you can edit the file to your liking.

Note: I would recommend updating the header description and add categories:

![iris](_guide/images/iris.png)

Categories will be important as the inputted text will be used as labels for posts. This will come aparent later on. 

Once you are done, simply knit the file as a `distill_article`.

![knit](_guide/images/knit.png)

You will recieve an output preview of what your post will look like.

Once you are done commit and push your changes to your repo.

![commit](_guide/images/commit.png)

Note: it is important to select the new generated and modified files to ensure that your post is created properly on Github.

## Creating an About Me Page with Postcards

You can create an About Me page by using the `create_postcard` function. 

Here are [examples](https://github.com/seankross/postcards#the-templates) of themes you can use.

```
# Four different themes you can use, only choose one!
create_postcard(file = 'your_name.Rmd', template = "jolla")
create_postcard(file = 'your_name.Rmd', template = "jolla-blue")
create_postcard(file = 'your_name.Rmd', template = "trestles")
create_postcard(file = 'your_name.Rmd', template = "onofre")
```

Choose one you would like to use. Make sure to update `your_name.Rmd` with your name in the `file` argument of the function.

A file will be generated for your about page. Be sure to edit the page to your liking. You may view what your page looks like by knitting the page as `postcards`.

I would recommend storing your iamges in the `images` folder for consistency.

![postcards](_guide/images/postcards.png)

Like before, once you're done commit and push all the new generated and modified files to your repo.

## Making a Pull Request to the Main Repo

Once you are done with everything, you may submit a pull request to the main repo. Head over the [repo page](https://github.com/DACSS/dacss_course_website) and click the `Pull requests` button.

![pr](_guide/images/pr.png)

Then when your on the next page, click the green `New pull request` button. Afterwards, click the blue `compare accross forks` link.

![compare](_guide/images/compare.png)

Edit the head repository **to your repo.**

![head](_guide/images/head.png)

Once you've done that, create a new pull request.

![new pr](_guide/images/new_pr.png)

Add some comments on what this pull request does. For example, in mine I added a new post about the iris dataset and created my about me page. Once you're done click the `Create pull request` button.

That's it! Wait for the instructor to review your pull request. They will give you feedback and if they approve your request, all your changes will be reflected on the main repo and website!

## Syncing a Fork 

If you notice that your repo is behing the main repo, you may want to sync up your local repo. 

![behind](_guide/images/behind.png)

You may manually do so by following [GitHub's official guide](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/syncing-a-fork).

Or you can the run the code chunk in `sync.Rmd`. This file can be found in the root directory of your repo.

![behind](_guide/images/run.png)

If the following code succeeds, you have synced up with the main repo. All you need to do is commit and push any changes that you made (if you have not, then you should be good to go!).