---
layout: default
---

Here's how to edit this website!

## Overview

1. Make changes and push to github (make sure you have collaborator privilages, and see later sections for details on specific kinds of changes)
2. Go to `/afs/ir.stanford.edu/group/alpslab/alpslab.stanford.edu` and pull your changes

		ssh [SUNetID]@cardinal.stanford.edu
		cd /afs/ir.stanford.edu/group/alpslab/alpslab.stanford.edu
		git pull

	There's a script on the server that makes the changes live after a successful merge.

## Specific kinds of changes

### How to add a new page to the website

1. make a markdown file, e.g. `new-file.md` in the top of the `alpslab.stanford.edu` directory

2. add this to the top of the markdown file:

		---
		layout: default
		---

3. if you want this page to appear in the navbar, add another value to the header:

		---
		layout: default
		title: New Page
		---

4. visit `alpslab.stanford.edu/new-page.html`.

### How to add a new entry to the "News" section

1. make a markdown file in the \_posts folder. give it a name according to these conventions: yyyy-mm-dd-title.md

2. give it a header of the following form:

		---
		layout: post
		title:  "YOUR TITLE"
		date:   2018-03-03 16:16:01 -0600 [your date/time goes here]
		categories: [a couple relevant tags]
		---

3. Write the body of your post below the header.

### How to add a person to the website

1. go to the file `_data/alpslab.yml`

2. find (or add) whatever role they play in the lab (e.g. Principal Investigator, Graduate Student, Alumni), and add a new person to that role.

		- role: [WHATEVER ROLE]
		  people:
		    - [OTHER PEOPLE]
		    - name: New Person
		      img: newPerson.jpg
		      webpage: //www.stanford.edu/~newP
		      bio:
		        - >
		          A paragraph of this person's bio.
		        - >
		          Another paragraph of this person's bio.
		    - [OTHER PEOPLE]

### How to add a publication to the website

1. go to the file `_bibliography/alpslab.bib` and add the publication.

If the publication is not appearing once you publish it to the website, this could be because of:
1. A typo in the alpslab.bib file. Make sure all the commas are in the right places!
2. You haven't published anything for this year yet and don't have the year header set up.

If (2) is the case, navigate to _config.yml at the root of the directory. Change line 12 as follows

`max_year: *insert new year*`

Then navigate to 02-publications.md at the root of the directory. Change line 18 as follows:

`...for year in (2011..*insert new year*)...`

### How to add an image to the front page carousel

1. got to the file `_data/carousel.yml`

2. add a new image to the end of the file

		- [OTHER IMAGES]
		- image: my-new-image.jpg
		  label: "A description of my new image"
		  alt: "if you want, you can add a line of alt text. otherwise, the label will be the alt text."


## Troubleshooting

If the website does not update within a minute or so of making these changes, this might be because the build script has stopped working. Run

	jekyll build
	rsync -r -a -v _site/* ../WWW/

in a terminal on the Stanford server in the `/afs/ir.stanford.edu/group/alpslab/alpslab.stanford.edu` directory.

### Setup

As of 9/25/2018, the website can be updated provided one has Ruby 2.5.1, Jekyll 3.8.4, Jekyll-Scholar 5.1.4, and Redcarpet 3.4.0 (back compatibility with earlier versions of the aforementioned software is possible but not guaranteed). Your Cardinal account comes with versions of Ruby and Jekyll that are incompatible with the website. First, update Ruby via rbenv:

```
# get rbenv
git clone https://github.com/sstephenson/rbenv.git ~/.rbenv

echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
# run the updated .bashrc
source ~/.bashrc
# fetch the ruby-build installer plugin to make things easier
git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
# download Ruby 2.5.1. this will take some time.
rbenv install 2.5.1
# set your system's default ruby to 2.5.1
rbenv global 2.5.1
```

Next, get fresh Jekyll, and install Jekyll-Scholar and Redcarpet:

```
gem install redcarpet -v 3.4.0
gem install jekyll -v 3.8.4
gem install jekyll-scholar -v 5.14.0
```

Lastly, ensure that local encoding is set to UTF-8:

```
export LANG=en_US.UTF-8
export LANGUAGE=en_US.UTF-8
export LC_ALL=en_US.UTF-8
```

Note that while `jekyll` is compatible with [GitHub pages](https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/), [`jekyll-scholar` is not](https://github.com/inukshuk/jekyll-scholar#github-pages).

For local debugging, one could run

```
jekyll build
```

and then navigate to `_site/index.html`.

<!-- Unfortunately, the links in this repo are currently hard-coded with the assumption that all files are present at the host (in the online version, `http://cocolab.stanford.edu/`, in the local version `file://`), so further abstraction and modifications would have to be made in order to actually navigate the site locally... --->
