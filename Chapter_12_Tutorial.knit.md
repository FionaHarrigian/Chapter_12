---
title: "Chapter_12_Tutorial"
author: "Fiona Harrigian and Tshianeo Ndou"
date: "2025-11-08"
output:
  bookdown::html_document2: 
    toc: TRUE
    toc_float: true
    toc_collapsed: true
    toc_depth: 3
    number_sections: true
link-citations: yes
fontsize: 12pt
bibliography: Bibliography_Ch12_Tutorial.bib 
csl: AmJBot.csl
---







# Pre-Tutorial Homework

## To-do:

* [Learn how to create a GitHub account](#learn-how-to-create-a-github-account)
* [Download and Install Git](#download-and-install-git)

### Learn how to create a GitHub account

First, we need to create a GitHub account. To create a github account, visit [Github](https://github.com/). Register with your BSU email address and create an account for free. Good news if you already have a GitHub account, just login with your details!

### Download and Install Git

Download and install Git on your local computer using [this link](https://git-scm.com/install/). Choose your operating system and follow the directions given on the website.

# Introduction

Throughout this semester, we have discussed making our science **reproducible** and **accessible**. We started by learning the concept of **reproducible science** and why it is so important. We also learned that there is a **reproducibility crisis**, what might be causing it, and how to address it. To address writing reproducible code, we learned about R markdown files and how to format them in a clear, reproducible way. We next learned how to make bibliographies, appendices, tables, figures, citations, and references in R markdown and how to use settings to best display them. We learned about creating and using functions and lists in R and writing code in a clear, reproducible, and defensive way. 

Then, we discussed the scientific method and how to mitigate the threats to each step of the scientific process. One of the mitigation strategies is using the **TOP** (Transparency and Openness Promotion) Guidelines, another is the **OSF** (Open Science Framework). Other mitigation strategies include the **FAIR** and **CARE** principles. FAIR principles focus on making data accessible to everyone, whereas CARE principles apply specifically to data involving Indigenous People and emphasize considerations of who benefits from the data, who can collect the data and the responsibilities and ethics surrounding the data. They are technically in opposition to each other but are equally important to consider when conducting research and before sharing data. Connected to this was the concept of a **Creative Common license** and which would be best to use for your own research. 

Finally, we learned about **data management**, that it is best to create a data management plan before starting research, and how to manage your data in a way that means it will continue to usable by you, your colleagues, and the general public, as long as such accessibility has been checked by the CARE principles. 

One of the final pieces of making your science **reproducible** is making sure your **data and code are accessible far into the future**, and importantly considering the FAIR and CARE principles. During this tutorial, we will introduce **Git** and **Github**, which will help make your science more reproducible. 


## Git and GitHub

**Git** is a **version control** system, which keeps track of the changes made to the files stored within it and allows us to return to previous versions. **GitHub** is the cloud hosting service built on top of Git. It can store data for you remotely, solving the issue of data storage. However, it was not built specifically for researchers, but instead for computer programmers. So at first glance, GitHub can be challenging to understand and use. With some time, the many helpful features of GitHub can become more clear and be used to help us conduct more **reproducible research**.

One of these features is **data storage and access**. When you create a project, which GitHub calls a **repository**, you can store data and code along with a README.md file that can be used to make your file structure even more clear. It can be particularly useful when several collaborators are working on the same project. Github allows files to be shared and edited, and tracks who edited which files and how they edit the files. Researchers unconnected to the project can also suggest changes to files, if the repository is public, which could provide further checks that help make science more **reproducible**. Github will store versions of your file indefinitely and for free, and will connect to RStudio Projects, which we will discuss today. We created this tutorial with information from [@Gandrud2020].

On **Day 1**, we will learn [Key Terms](#key-terms) for work in **Git** and **GitHub**, make a new repository in GitHub and clone it into a new RStudio Git version control project, and work with partners to practice working with GitHub.

On **Day 2**, we will look at **GitHub repositories** that are alive and nice examples of how your GitHub repository might look in the future! We will practice importing data from one of these into RStudio, and uploading data into your own GitHub repository.


# Day 1

## Learning Objectives

* [Set your R Terminal to Git Bash](#set-your-r-terminal-to-git-bash)
* [Key Terms](#key-terms)
* [Creating a remote repository in GitHub](#creating-a-remote-repository-in-github)
* [Creating a local repository in RStudio](#creating-a-local-repository-in-rstudio)
* [Turn on notifications for push changes](#turn-on-notifications-for-push-changes)
* [Activity for Day 1 of the Tutorial](#activity-for-day-1-of-the-tutorial)
* [Committing your changes cautiously](#committing-your-changes-cautiously)


### Set your R Terminal to Git Bash

Make sure your settings are up to date by going to Tools –> Global Options –> Terminal –> under the General Tab –> New Terminals Open with: GitBash –> Apply.

### Key Terms

As we work today and for your future Git adventures, here are a few useful terms and their definitions. You can use the search bar embedded in the table to search terms or any words in the definitions for further clarification and assistance. Pay specific attention to the definitions for **Commit**, **Commit message**, **Pull**, **Push**, and **Repository**.



```{=html}
<div class="datatables html-widget html-fill-item" id="htmlwidget-ed21fe7db514b4aa58f3" style="width:100%;height:auto;"></div>
<script type="application/json" data-for="htmlwidget-ed21fe7db514b4aa58f3">{"x":{"filter":"none","vertical":false,"extensions":["Buttons"],"data":[["Branch","Clone","Collaborator","Commit","Commit ID","Commit message","Default Branch","Diff","Directory","Force push","Main","Master","Merge","Private Repository","Public Repository","Pull","Pull Request","Push","Push a branch","README","Repository","SSH Key"],["A branch is a parallel version of a repository. It is contained within the repository, but does not affect the primary or main branch allowing you to work freely without disrupting the \"live\" version. When you've made the changes you want to make, you can merge your branch back into the main branch to publish your changes.","A clone is a copy of a repository that lives on your computer instead of on a website's server somewhere, or the act of making that copy. When you make a clone, you can edit the files in your preferred editor and use Git to keep track of your changes without having to be online. The repository you cloned is still connected to the remote version so that you can push your local changes to the remote to keep them synced when you're online.","A collaborator is a person with read and write access to a repository who has been invited to contribute by the repository owner.","A commit, or \"revision\", is an individual change to a file (or set of files). When you make a commit to save your work, Git creates a unique ID (a.k.a. the \"SHA\" or \"hash\") that allows you to keep record of the specific changes committed along with who made them and when. Commits usually contain a commit message which is a brief description of what changes were made.","Also known as SHA. A 40-character checksum hash that identifies the commit.","Short, descriptive text that accompanies a commit and communicates the change the commit is introducing.","The base branch for new pull requests and code commits in a repository. Each repository has at least one branch, which Git creates when you initialize the repository. The first branch is usually called main, and is often the default branch.","A diff is the difference in changes between two commits, or saved changes. The diff will visually describe what was added or removed from a file since its last commit.","A folder containing one or more files or folders. You can create directories to organize the contents of a repository.","A Git push that overwrites the remote repository with local changes without regard for conflicts.","The default development branch. Whenever you create a Git repository, a branch named main is created, and becomes the active branch. In most cases, this contains the local development, though that is purely by convention and is not required.","The default branch in many Git repositories. By default, when you create a new Git repository on the command line, a branch called master is created. Many tools now use an alternative name for the default branch. For example, when you create a new repository on GitHub, the default branch is called main.","Merging takes the changes from one branch (in the same repository or from a fork), and applies them into another. This often happens as a \"pull request\" (which can be thought of as a request to merge), or via the command line. A merge can be done through a pull request via the GitHub.com web interface if there are no conflicting changes, or can always be done via the command line.","Private repositories are only visible to the repository owner and collaborators that the owner specified.","A public repository can be viewed by anyone, including people who aren't GitHub users.","Pull refers to when you are fetching in changes and merging them. For instance, if someone has edited the remote file you're both working on, you'll want to pull in those changes to your local copy so that it's up to date. See also fetch.","Pull requests are proposed changes to a repository submitted by a user and accepted or rejected by a repository's collaborators. Like issues, pull requests each have their own discussion forum.","To push means to send your committed changes to a remote repository on GitHub.com. For instance, if you change something locally, you can push those changes so that others may access them.","When you successfully push a branch to a remote repository, you update the remote branch with changes from your local branch.","A text file containing information about the files in a repository that is typically the first file a visitor to your repository will see. A README file, along with a repository license, contribution guidelines, and a code of conduct, helps you share expectations and manage contributions to your project.","A repository is the most basic element of GitHub. They're easiest to imagine as a project's folder. A repository contains all of the project files (including documentation), and stores each file's revision history. Repositories can have multiple collaborators and can be either public or private.","SSH keys are a way to identify yourself to an online server, using an encrypted message. It's as if your computer has its own unique password to another service. GitHub uses SSH keys to securely transfer information to your computer."]],"container":"<table class=\"display\">\n  <thead>\n    <tr>\n      <th>Term<\/th>\n      <th>Definition<\/th>\n    <\/tr>\n  <\/thead>\n<\/table>","options":{"dom":"Blfrtip","buttons":["copy","csv","excel","pdf","print"],"pageLength":5,"columnDefs":[{"name":"Term","targets":0},{"name":"Definition","targets":1}],"order":[],"autoWidth":false,"orderClasses":false,"lengthMenu":[5,10,25,50,100],"rowCallback":"function(row, data, displayNum, displayIndex, dataIndex) {\nvar value=data[0]; $(this.api().cell(row, 0).node()).css({'font-weight':'bold'});\n}"},"selection":{"mode":"multiple","selected":null,"target":"row","selectable":null}},"evals":["options.rowCallback"],"jsHooks":[]}</script>
```


### Creating a remote repository in GitHub

Now that you have created a GitHub account, it is time to make your first repository! To do so, 

1. Click the green and white image in the upper right hand corner of GitHub and look for the Repositories button.

<img src="Pictures/findrepo_github.jpg" width="50%" style="display: block; margin: auto;" />

2. Click the green "New" button in the upper right hand corner of the Repositories tab.

<img src="Pictures/new_repo.jpg" width="75%" style="display: block; margin: auto;" />

3. Fill out the new Repository, your username should be in the owner section. Give the repository a name that is easy for you to remember, cannot match the name of another repository in your account. GitHub will recommend fun and interesting names, which would be unique but may be hard to remember and associate with your work, so be careful what you choose. 

For the Configuration options:

1. Create a public repository.
2. Turn on Add README so that you'll have a readme file in your repository.
3. Turn on Add .gitignore file and choose R as file template. 
4. Click Create Repository.

<img src="Pictures/creatingrepo.png" width="50%" style="display: block; margin: auto;" />


### Creating a local repository in RStudio

In RStudio, just like creating a new project at the beginning of this class (or anytime you want to start a new project), you can make a new project that can be linked to a remote repository in GitHub. 

1. Go back to your GitHub, find the repository you just made and go to the green Code button in the upper right hand corner. Click this and a tab will appear that says Clone. Under this tab, there is a HTTPS section. Make sure you are in this section, then press the icon of one square on top of another inside of the red circle below in Figure \@ref(fig:redcircle).

<div class="figure" style="text-align: center">
<img src="Pictures/redcircle.png" alt="Cloning Repository from GitHub into RStudio" width="75%" />
<p class="caption">(\#fig:redcircle)Cloning Repository from GitHub into RStudio</p>
</div>

2. Create a new project on RStudio with Git version control by first choosing "Version Control" in the new project wizard.

<img src="Pictures/new_project_git.jpg" width="50%" style="display: block; margin: auto;" />

3. Next, select the Git button to clone a project from a Git repository.

<img src="Pictures/GitRproject.jpg" width="50%" style="display: block; margin: auto;" />


4. Paste this url that you just copied into the box that says Repository URL inside the Clone Git Repository box. For the Project directory name, use the same name as your GitHub repository. Create the new RStudio Git version control inside a subdirectory, using your Desktop, Documents folder, or anywhere you normally create new RStudio directories.

<img src="Pictures/gitversion.png" width="50%" style="display: block; margin: auto;" />

### Turn on notifications for push changes

If you are the owner of the repository, when you and your collaborators make changes, you can see the changes if you have push notifications turned on. This is good for tracking and knowing what your collaborators are working on. 
To turn on push notifications: 

1. Click on Settings on the upper right while in the repository you just created (or any you need notifications for). 

<img src="Pictures/settings.jpg" width="75%" style="display: block; margin: auto;" />


2. Scroll down to the bottom of the list of settings and in the lower left corner, click on Email notifications.
You should see the Email notifications page. 


<img src="Pictures/email_not.jpg" width="50%" style="display: block; margin: auto;" />


3. Make sure to add the email address you would like to receive notifications on, check the box next to Active if not already checked, then press Update settings. 


<img src="Pictures/push_not.jpg" width="50%" style="display: block; margin: auto;" />


Unfortunately only the admin or owner of the repository can get notifications when changes are made. So far we have not found a way to make collaborators receive these notifications. We tried using the “Watch” button in the upper right for the collaborator to receive this messages, but that did not seem to work. This remains to be explored as it can be a useful tool for remote communication. 

### Activity for Day 1 of the Tutorial

By now, you should have created a repository of your own and linked it with a matching project in RStudio. The next piece of working in github is to practice working with a collaborator.

In pairs, you will:

1. Choose one of the pair to be the admin and one to be the collaborator. 

2. The admin will go to the settings of their repository, then click on Collaborators in the upper left area of the settings. You’ll be prompted to login, once you do, you’ll get to the collaborators screen. 

<img src="Pictures/collab_add.jpg" width="50%" style="display: block; margin: auto;" />

<img src="Pictures/login_screen.jpg" width="25%" style="display: block; margin: auto;" />

<img src="Pictures/collab_admin.jpg" width="50%" style="display: block; margin: auto;" />


3. Add your partner by clicking the add people button and searching for your partner’s GitHub account name (check with them, sometimes it may be different from their name, include numbers, etc.)

<img src="Pictures/manage_access.jpg" width="50%" style="display: block; margin: auto;" />

4. Click Add to repository, your partner should get a code in an email to access your repository.

<img src="Pictures/introrepo.png" width="50%" style="display: block; margin: auto;" />

5. Once the collaborator partner finds the admin’s repository, click on the green code button in the upper right hand corner.

<img src="Pictures/green_code_button.jpg" width="100%" />

6. Copy the HTTPS URL with the box button to the right of the url.
Follow the directions to clone your repository in RStudio as presented in [Creating a local repository in RStudio](#creating-a-local-repository-in-rstudio).

<img src="Pictures/copy_link.jpg" width="50%" style="display: block; margin: auto;" />

7. Once each of you have the repository open in RStudio, one will go first, writing a sentence in the README.md, saving the your local file, committing the change (Figure \@ref(fig:redgreen)), pushing the change to the remote GitHub repository file, then the other partner pulls that change with the down pull arrow and adds their own sentence. 

8. Do a repeat of this exercise until you have 3 sentences each (or 1 each for time).
* Have conversation with each other (Fiona and Tshia will push and pull and demonstrate on the projector).

### Committing your changes cautiously

* Do not commit at the same time as your collaborator, Git does not like it. It will show an error (Figure \@ref(fig:redgreen)).
* Make sure the box for the doc/file you are working on is checked before (blue tick) before you push. This stages the file and enables changes to be committed.
* You will need to write something in the commit box for GitHub to accept the changes and it is helpful to summarize the changes you have made for your future reference and your collaborators. Remember, some of the power of GitHub is that changes can be tracked, but this feature is only helpful when you can easily pick out the version you are looking for from a long list of versions.
* To avoid accidental merging and overwriting your changes or the changes of your collaborators,  communicate with your them when committing, pushing, and pulling changes. After creating this tutorial, we also found it helpful to have a backup version (not associated with GitHub) saved as well.


<div class="figure" style="text-align: center">
<img src="Pictures/red_green.png" alt="Interface when pushing and committing changes" width="75%" />
<p class="caption">(\#fig:redgreen)Interface when pushing and committing changes</p>
</div>



# Day 2

## Learning Objectives

* [Activity for Day 2 of the Tutorial](#activity-for-day-2-of-the-tutorial)
* [Checking out public repositories](#checking-out-public-repositories)
* [Import data into R from a GitHub repository](#import-data-into-r-from-a-github-repository)
* [Downloading data, uploading data, importing into RStudio project](#downloading-data-uploading-data-importing-into-rstudio-project)

### Activity for Day 2 of the Tutorial

In **Day 1**, we learned [Key Terms](#key-terms) for work in **Git** and **GitHub**, made a new repository in GitHub and cloned it into a new RStudio Git version control project, and worked with partners to practice making changes, committing them, pushing changes to the remote GitHub repository, and pulling changes from the **remote GitHub repository** to your **local RStudio project** files.

On **Day 2**, we will look at **GitHub repositories** that are alive and nice examples of how your GitHub repository might look in the future! We will practice importing data from one of these into RStudio, and uploading data into your own GitHub repository.

### Checking out public repositories

As you read more papers, interact with collaborators, and become a scientist doing extremely reproducible science, you will likely need to bring data from a public GitHub repository into your own computer and into R. 

* One example of a public repository is Sven’s repository for this class [Reproducible 603](https://github.com/svenbuerki/EEB603_Reproducible_Science). Following the link, you can see his repository, with all the folders and files inside displayed in a list. If you scroll to the bottom, you can see the README with information about this repository/class.

* Another example of a public repository is one that was made as part of a paper submission. Fiona read a cool microbial ecology paper that tracked the ecological and evolutionary responses of Curtobacterium over an elevation gradient in Southern California [@Chase2021]. In the paper, there is a section that says Data Availability. Following the [link](https://github.com/alex-b-chase/curtoEvol) to their github, we can see a similar set of folders and files, as well as a README.

<img src="Pictures/Chase_et_al_2021_data_availability.jpg" width="50%" style="display: block; margin: auto;" />

### Import data into R from a GitHub repository

* For either repository, find a data file. Usually, you will have the specific data in mind and may have background for the name you are looking for. However, sometimes repositories can be unclear. Use what we have learned in class to identify data, whether a .csv file, a .txt file, or a .xlsx file. 

### Downloading data, uploading data, importing into RStudio project

1. Download the data file by clicking on the Download raw file button. It will now be on your computer. 

2. Practice uploading data to your own GitHub repository by returning to your repository, clicking the add file button next to the green code button, then Upload files in the dropdown. 

3. You can drag files into the box or choose your files. Make sure to commit your changes in the section underneath the box. 

4. To import data into RStudio, go to your repository in GitHub. 

5. Find the data file we just uploaded and go to the file by clicking on it in the list of files in your repository. 

6. Click on the Raw button in the upper left. 

7. It should bring you to a page with just the file contents and the url at the top is what you need to copy. 

8. Moving back to RStudio, in a new R script, run these lines of code:


``` r
# Paste URL into url object
#url <-"PASTE HERE"
# Download data
#YOUR_data <- rio::import(url, format = "csv")
```

You should now see your data file in the environment, ready to be used!


# Relevant resources

As a final send-off to all of you (and any future users of this tutorial), here is a list of resources we used to build this tutorial. 

For the latest version of Gandrud's textbook, visit this link which will allow you to search Boise State University's library and download an ebook: [3rd edition reproducuble Research with R and Rstudio](https://boisestate.on.worldcat.org/search?queryString=gandrud%20reproducible&bookReviews=off&idDetect=true&clusterResults=true&groupVariantRecords=false)

[Github for dummies video](https://www.youtube.com/watch?v=mJ-qvsxPHpY&t=859s)

[Github control version video](https://www.youtube.com/watch?v=HVsySz-h9r4&t=9s)


# References

<div id="refs"></div>

# (APPENDIX) Appendices {-}

# Appendix 1

Citations of all R packages used to generate this report.
[1] J. Allaire, Y. Xie, C. Dervieux, et al. _rmarkdown: Dynamic
Documents for R_. R package version 2.29. 2024.
<https://github.com/rstudio/rmarkdown>.

[2] S. M. Bache and H. Wickham. _magrittr: A Forward-Pipe Operator for
R_. R package version 2.0.3. 2022. <https://magrittr.tidyverse.org>.

[3] J. Becker, C. Chan, D. Schoch, et al. _rio: A Swiss-Army Knife for
Data I/O_. R package version 1.2.4. 2025.
<https://gesistsa.github.io/rio/>.

[4] C. Boettiger. _knitcitations: Citations for Knitr Markdown Files_.
R package version 1.0.12. 2021.
<https://github.com/cboettig/knitcitations>.

[5] C. Chan, T. J. Leeper, J. Becker, et al. _rio: A Swiss-army knife
for data file I/O_. 2023. <https://cran.r-project.org/package=rio>.

[6] J. Cheng, C. Sievert, B. Schloerke, et al. _htmltools: Tools for
HTML_. R package version 0.5.8.1. 2024.
<https://github.com/rstudio/htmltools>.

[7] R. Francois and D. Hernangómez. _bibtex: Bibtex Parser_. R package
version 0.5.1. 2023. <https://github.com/ropensci/bibtex>.

[8] G. Grolemund and H. Wickham. "Dates and Times Made Easy with
lubridate". In: _Journal of Statistical Software_ 40.3 (2011), pp.
1-25. <https://www.jstatsoft.org/v40/i03/>.

[9] K. Müller and H. Wickham. _tibble: Simple Data Frames_. R package
version 3.2.1. 2023. <https://tibble.tidyverse.org/>.

[10] Y. Qiu. _prettydoc: Creating Pretty Documents from R Markdown_. R
package version 0.4.1. 2021. <https://github.com/yixuan/prettydoc>.

[11] R Core Team. _R: A Language and Environment for Statistical
Computing_. R Foundation for Statistical Computing. Vienna, Austria,
2024. <https://www.R-project.org/>.

[12] K. Ren and K. Russell. _formattable: Create Formattable Data
Structures_. R package version 0.2.1. 2021.
<https://renkun-ken.github.io/formattable/>.

[13] V. Spinu, G. Grolemund, and H. Wickham. _lubridate: Make Dealing
with Dates a Little Easier_. R package version 1.9.3. 2023.
<https://lubridate.tidyverse.org>.

[14] H. Wickham. _forcats: Tools for Working with Categorical Variables
(Factors)_. R package version 1.0.0. 2023.
<https://forcats.tidyverse.org/>.

[15] H. Wickham. _ggplot2: Elegant Graphics for Data Analysis_.
Springer-Verlag New York, 2016. ISBN: 978-3-319-24277-4.
<https://ggplot2.tidyverse.org>.

[16] H. Wickham. _stringr: Simple, Consistent Wrappers for Common
String Operations_. R package version 1.5.1. 2023.
<https://stringr.tidyverse.org>.

[17] H. Wickham. _tidyverse: Easily Install and Load the Tidyverse_. R
package version 2.0.0. 2023. <https://tidyverse.tidyverse.org>.

[18] H. Wickham, M. Averick, J. Bryan, et al. "Welcome to the
tidyverse". In: _Journal of Open Source Software_ 4.43 (2019), p. 1686.
DOI: 10.21105/joss.01686.

[19] H. Wickham, J. Bryan, M. Barrett, et al. _usethis: Automate
Package and Project Setup_. R package version 3.1.0. 2024.
<https://usethis.r-lib.org>.

[20] H. Wickham, W. Chang, L. Henry, et al. _ggplot2: Create Elegant
Data Visualisations Using the Grammar of Graphics_. R package version
3.5.2. 2025. <https://ggplot2.tidyverse.org>.

[21] H. Wickham, R. François, L. Henry, et al. _dplyr: A Grammar of
Data Manipulation_. R package version 1.1.4. 2023.
<https://dplyr.tidyverse.org>.

[22] H. Wickham and L. Henry. _purrr: Functional Programming Tools_. R
package version 1.0.2. 2023. <https://purrr.tidyverse.org/>.

[23] H. Wickham, J. Hester, and J. Bryan. _readr: Read Rectangular Text
Data_. R package version 2.1.5. 2024. <https://readr.tidyverse.org>.

[24] H. Wickham, J. Hester, W. Chang, et al. _devtools: Tools to Make
Developing R Packages Easier_. R package version 2.4.5. 2022.
<https://devtools.r-lib.org/>.

[25] H. Wickham, D. Vaughan, and M. Girlich. _tidyr: Tidy Messy Data_.
R package version 1.3.1. 2024. <https://tidyr.tidyverse.org>.

[26] Y. Xie. _bookdown: Authoring Books and Technical Documents with R
Markdown_. Boca Raton, Florida: Chapman and Hall/CRC, 2016. ISBN:
978-1138700109. <https://bookdown.org/yihui/bookdown>.

[27] Y. Xie. _bookdown: Authoring Books and Technical Documents with R
Markdown_. R package version 0.44. 2025.
<https://github.com/rstudio/bookdown>.

[28] Y. Xie. _Dynamic Documents with R and knitr_. 2nd. ISBN
978-1498716963. Boca Raton, Florida: Chapman and Hall/CRC, 2015.
<https://yihui.org/knitr/>.

[29] Y. Xie. "knitr: A Comprehensive Tool for Reproducible Research in
R". In: _Implementing Reproducible Computational Research_. Ed. by V.
Stodden, F. Leisch and R. D. Peng. ISBN 978-1466561595. Chapman and
Hall/CRC, 2014.

[30] Y. Xie. _knitr: A General-Purpose Package for Dynamic Report
Generation in R_. R package version 1.50. 2025.
<https://yihui.org/knitr/>.

[31] Y. Xie, J. Allaire, and G. Grolemund. _R Markdown: The Definitive
Guide_. Boca Raton, Florida: Chapman and Hall/CRC, 2018. ISBN:
9781138359338. <https://bookdown.org/yihui/rmarkdown>.

[32] Y. Xie, C. Dervieux, and E. Riederer. _R Markdown Cookbook_. Boca
Raton, Florida: Chapman and Hall/CRC, 2020. ISBN: 9780367563837.
<https://bookdown.org/yihui/rmarkdown-cookbook>.

[33] H. Zhu. _kableExtra: Construct Complex Table with kable and Pipe
Syntax_. R package version 1.4.0. 2024.
<http://haozhu233.github.io/kableExtra/>.

# Appendix 2

Version information about R, the operating system (OS) and attached or R loaded packages. This appendix was generated using `sessionInfo()`.

```
## R version 4.4.1 (2024-06-14 ucrt)
## Platform: x86_64-w64-mingw32/x64
## Running under: Windows 11 x64 (build 26200)
## 
## Matrix products: default
## 
## 
## locale:
## [1] LC_COLLATE=English_United States.utf8 
## [2] LC_CTYPE=English_United States.utf8   
## [3] LC_MONETARY=English_United States.utf8
## [4] LC_NUMERIC=C                          
## [5] LC_TIME=English_United States.utf8    
## 
## time zone: America/New_York
## tzcode source: internal
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets  methods   base     
## 
## other attached packages:
##  [1] rio_1.2.4            lubridate_1.9.3      forcats_1.0.0       
##  [4] stringr_1.5.1        purrr_1.0.2          readr_2.1.5         
##  [7] tidyr_1.3.1          tibble_3.2.1         ggplot2_3.5.2       
## [10] tidyverse_2.0.0      devtools_2.4.5       usethis_3.1.0       
## [13] bibtex_0.5.1         knitcitations_1.0.12 htmltools_0.5.8.1   
## [16] prettydoc_0.4.1      magrittr_2.0.3       dplyr_1.1.4         
## [19] kableExtra_1.4.0     formattable_0.2.1    bookdown_0.44       
## [22] rmarkdown_2.29       knitr_1.50          
## 
## loaded via a namespace (and not attached):
##  [1] gtable_0.3.6      xfun_0.53         bslib_0.8.0       remotes_2.5.0    
##  [5] htmlwidgets_1.6.4 tzdb_0.4.0        vctrs_0.6.5       tools_4.4.1      
##  [9] generics_0.1.3    fansi_1.0.6       RefManageR_1.4.0  pkgconfig_2.0.3  
## [13] lifecycle_1.0.4   compiler_4.4.1    textshaping_0.4.0 munsell_0.5.1    
## [17] codetools_0.2-20  httpuv_1.6.15     sass_0.4.9        yaml_2.3.10      
## [21] urlchecker_1.0.1  pillar_1.9.0      later_1.4.1       jquerylib_0.1.4  
## [25] ellipsis_0.3.2    cachem_1.1.0      sessioninfo_1.2.3 mime_0.12        
## [29] tidyselect_1.2.1  digest_0.6.37     stringi_1.8.4     grid_4.4.1       
## [33] fastmap_1.2.0     colorspace_2.1-1  cli_3.6.3         pkgbuild_1.4.7   
## [37] utf8_1.2.4        withr_3.0.2       scales_1.3.0      promises_1.3.2   
## [41] backports_1.5.0   timechange_0.3.0  httr_1.4.7        hms_1.1.3        
## [45] memoise_2.0.1     shiny_1.10.0      evaluate_1.0.3    miniUI_0.1.1.1   
## [49] viridisLite_0.4.2 profvis_0.4.0     rlang_1.1.4       Rcpp_1.0.13      
## [53] xtable_1.8-4      glue_1.7.0        xml2_1.3.6        pkgload_1.4.0    
## [57] svglite_2.2.1     rstudioapi_0.16.0 jsonlite_1.8.8    R6_2.5.1         
## [61] plyr_1.8.9        systemfonts_1.3.1 fs_1.6.4
```



