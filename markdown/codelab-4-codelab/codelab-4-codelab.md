author: Marc DiPasquale
summary: Create a CodeLab Using Markdown
id: codelab-4-codelab
tags: 
categories: codelab,markdown
environments: Web
status: Published
feedback link: https://github.com/SolaceDev/codelab-4-codelab
analytics account: UA-3921398-10

# CodeLab to Create a CodeLab

## CodeLab Overview
Duration: 0:02:00

Are you trying to create easy to use, visually appealing content for the tech community? This CodeLab will show you how to quickly create your own Google CodeLab just like the one you're using right now. 
When creating a Codelab you have two authoring options: 
1. Using a Google Doc
1. Using a markdown file

In this codelab we are going to use the second option and author our codelab using a markdown file. This gives us the flexibility of using our markdown file for other things and also storing it in our github repo with any code that might be used for a tutorial. 

Here is an example image of another CodeLab that I created:
![image_caption](img/codelabexample.png)


**Resources:** 
* The markdown for this codelab is located here: [codelab.md](https://github.com/SolaceDev/codelab-4-codelab/blob/master/codelab.md)
* [Google CodeLabs Tools Github](https://github.com/googlecodelabs/tools) - The repo that contains the claat tool we'll be using today
* [Google Group for CodeLab Authors](https://groups.google.com/forum/#!forum/codelab-authors) - great forum for asking questions about codelabs and discussing future functionality
* [A blog that I used when getting started with Google Codelabs](https://medium.com/@mariopce/tutorial-how-to-make-tutorials-using-google-code-labs-gangdam-style-d62b35476816)

## Environment Setup
Duration: 0:04:00

In order to create a CodeLab you need *Go* and *claat* (the codelabs command line tool) installed.

The instructions below are what worked for me on Mac, but you can also find instructions [here](https://github.com/googlecodelabs/tools/tree/master/claat) 

#### Install Go 

Install [Go](https://golang.org/dl/) if you don't have it.
You can use Homebrew if you have it on mac 
``` bash
$ brew install go
```

#### Setup Go Environment Variables
Below is what I set on mac, but instructions are [here](https://golang.org/doc/install) for other OS options

``` bash
$ export GOPATH=$HOME/Go
$ export GOROOT=/usr/local/opt/go/libexec
$ export PATH=$PATH:$GOPATH/bin
$ export PATH=$PATH:$GOROOT/bin
```

#### Install claat
Install claat
``` bash
$ go get -u -v -x github.com/googlecodelabs/tools/claat
```

You should now have the *claat* command available to you. 
``` bash
$ claat
```

## Solace Guidelines
Duration: 0:05:00

Please follow these guidelines when creating codelabs that will be hosted at [solace.dev/codelabs](https://solace.dev/codelabs)

### Content Guidance
* Each codelab should be focused on one topic or a very small group of related topics. 
* Use sections to separate steps for ease of navigation
* Include an "Overview" or "What You'll Learn Section" at the beginning of a codelab
* Include an "Environment Setup" or "What You'll Need Section" section that sets up the environment, if necessary. 
* Try to make the codelab fun and engaging 
* Provide code used in a public git repo

### Where to create your codelab
* It is recommended that you create your codelab in a git repository for version tracking. This can be in a Solace git org such as SolaceDev or SolaceSe; or a personal repo if preferred.  
* It is fine to keep the codelab markdown in the same repository as sample code if desired.
* An example structure for a codelab repo can be seen [here](https://github.com/SolaceDev/codelab-4-codelab)


## Create your initial CodeLab
Duration: 0:05:00

Now that we have the environment setup let's go ahead and create a markdown file where we'll create the actual codelab. 
Please have your markdown file name match the "id" in the header metadata that you will set in the next subsection. 

Negative
: If you're using Windows make sure to set your text editor to use UNIX line endings! 

####
``` bash
$ vim unique-codelab-identifier.md
```


#### Fill-in the header metadata
Copy and paste the headers below into your markdown file and change the values appropriately. 
Guidelines are available below the sample headers. 

``` 
author: Author Name
summary: Summary of your codelab that is human readable
id: unique-codelab-identifier
tags: workshop,iguide
categories: Java,Spring
environments: Web
status: Published
feedback link: A link where users can go to provide feedback (Maybe the git repo)
analytics account: UA-3921398-10
```

Metadata consists of key-value pairs of the form "key: value". Keys cannot
contain colons, and separate metadata fields must be separated by blank lines.
At present, values must all be on one line. All metadata must come before the
title. Any arbitrary keys and values may be used; however, only the following
will be understood by the renderer:
* Author: Author name or git username
* Summary: A human-readable summary of the codelab. Defaults to blank.
* Id: An identifier composed of lowercase letters ideally describing the
  content of the codelab. This field should be unique among
  codelabs. This will be in the URL of the codelab. 
* Tags: Leave "workshop" if creating a Developer workshop or "iguide" if creating an integration guide. Remove both if neither. 
* Categories: A comma-separated list of the topics or technologies the codelab covers. Include items such as language(s) and protocol(s) used. 
* Environments: Leave as "Web"
* Status: The publication status of the codelab. Valid values are:
  - Draft: Codelab is not finished.
  - Published: Codelab is finished and visible.
  - Deprecated: Codelab is considered stale and should not be widely advertised.
  - Hidden: Codelab is not shown in index.
* Feedback Link: A link to send users to if they wish to leave feedback on the
  codelab. Link to git repo where code for the tutorial will live.
* Analytics Account: A Google Analytics ID to include with all codelab pages. Leave as shown above. 

#### Add the Title
Next add your title using a single '#' character
```
# Title of codelab
```

#### Add Sections & Durations
Then for each section use Header 2 or '##' & specify an optional duration beneath for time remaining calculations
Optional section times will be used to automatically total & remaining tutorial times
In markdown I've found that the time is formatted hh:mm:ss

Example
``` bash
## Section 1
Duration: 0:10:00

## Section 2
Duration: 0:05:00
```

#### Add Section Content
Now that we have 2 sections to our titled codelab let's go ahead and add some content to each section. 
Make up your own or copy & paste the example below: 

Copy into section 1 (Below Duration and above Section 2):
```
### Info Boxes
Plain Text followed by green & yellow info boxes 

Negative
: This will appear in a yellow info box.

Positive
: This will appear in a green info box.

You created info boxes!

### Bullets
Plain Text followed by bullets
* Hello
* CodeLab
* World

You created bullets!

### Numbered List
1. List
1. Using
1. Numbers

You created a numbered list!

```

Copy into section 2 (Below Duration): 
```
### Add a Link
Add a link!
[Example of a Link](https://www.google.com)

### Add an Image
Add an image!
![image_caption](https://googlecloud.tips/img/031/codelabs.png)

### Embed an iframe
![https://codepen.io/tzoght/embed/yRNZaP](https://en.wikipedia.org/wiki/File:Example.jpg "Try Me Publisher")
```
More Markdown Parser examples can be found [here](https://github.com/googlecodelabs/tools/tree/master/claat/parser/md).

## Export & Serve Locally
Duration: 0:02:00

Now that you have an initial codelab defined in your markdown file let's go ahead and generate the static site content. 
We can export & serve the content locally using the `claat` command that we installed earlier. 

``` bash
$ claat export codelab.md
$ claat serve
```

* Your browser should have opened (if it doesn't then try going to localhost:9090 in your browser). 
* Choose the directory that matches your "id" that you put in the headers. 
* Viola! You should have your first codelab!

## Add your CodeLab to solace.dev/codelabs
Duration: 0:01:00

When you ran the `claat export` command you created the static web content needed to host your codelab. 
It placed static web content in a directory specified by your unique "id" and you can view it locally by opening the index.html page. 

Negative
: Note that when you view it locally by opening index.html some of the graphics may not show up (such as access_time, Next, Back), but they work once online. 


### Stage your Codelab
Clone the solace-dev-codelabs repo and checkout a new branch with a name that makes sense

``` bash
git clone git@github.com:SolaceDev/solace-dev-codelabs.git
cd solace-dev-codelabs
git checkout -b add-codelab-foo
```

Add your markdown file and related artifacts (such as images) to the `markdown` folder. 
Export your static web content and add it to the `codelabs` folder. 
Please ensure that your markdown file name matches your header metadata `id` for ease of future updates. 
``` bash
cd /path/to/solace-dev-codelabs
mkdir markdown/<header-metadata-id> #Only necessary if creating a new codelab
cp /path/to/<header-metadata-id>.md markdown/<header-metadata-id>/
cp -r /path/to/<header-metadata-id>/img markdown/<header-metadata-id>/
cd markdown/<header-metadata-id>
claat export <header-metadata-id>.md
rm -rf ../../codelabs/<header-metadata-id> #Only necessary if updating an existing codelab
mv <header-metadata-id> ../../codelabs/
```

Commit & Push your changes 
``` bash
git commit -a -m 'Added or Updated <header-metadata-id> codelab'
git push --set-upstream origin add-codelab-foo
```

### Create a Pull Request
Now that your changes have been pushed to a new branch branch we need to request that they get pulled into the master branch to go live on solace.dev/codelabs. 

Do this by navigating to the github repo at: [https://github.com/SolaceDev/solace-dev-codelabs](https://github.com/SolaceDev/solace-dev-codelabs)

Since your commit has already been pushed you should see a highlighted box near the top of the page; Choose the "Pull Request" button next to it and fill out the form with comments on what changes are being requested. Upon submitting the Pull Request the Codelabs team will be notified, perform a review and ensure the codelab goes live on the site. 

### Thank You!
Thank you for contributing to Solace Codelabs! 
Please reach out to the Solace DevRel team with any questions.
