# Open Education Template - Developer's Guide

## Introduction

This book is intended to teach you how to author OPE-style textbooks, as well as setup container images that contain all the software required for following along with the textbook content. <br>

The OPE project is an initiative towards making education open source, and to achieve highly interactive teaching and presentation material. 

## View Published Docubook

1. [Text Book](https://isaiahstapleton.github.io/ope-docubook/textbook/intro_tb.html)
2. [Lecture Notes](https://isaiahstapleton.github.io/ope-docubook/lecturenotes/intro_ln.html)
3. [Lab Manual](https://isaiahstapleton.github.io/ope-docubook/labmanual/intro_lm.html)

## Creating New Textbooks

The OPE repository has a branch titled [coursecontenttemplate](https://github.com/OPEFFORT/ope/tree/coursecontenttemplate) that contains everything you need to start creating new OPE textbooks. First start by cloning the repository and then switching to the coursecontenttemplate branch by running the following commands:

```shell

git clone https://github.com/OPEFFORT/ope.git

cd ope

git checkout coursecontenttemplate

```

### Understanding Template Layout

Before you get started creating a new Textbook, you must familiarize yourself with the layout of the OPE template. There are three different parts of the OPE template:

1. Textbook Content (tb)
2. Lecture Notes (ln)
3. Lab Manual (lm)

The files associated with each will contain the two letters that appear in parenthesis above. For example, files associated with textbook content will have tb in the file name (such as tb_config.yml). Going forward in this guide, xx will be used to refer to a file that is not specific to any of the three, but rather all of them (such as xx_config.yml). 

#### Important files

- **Makefile:** The top level Makefile automates the tasks of building and publishing the book content. This includes the textbook, the lecture notes, and the lab manual. You can see a list of build targets by running the "Make" command in the same directory as the Makefile. 

- **xx_config.yml:** This config file is used to change book settings such as: title, author, logo, URL to publish to, and jupyter extensions you would like enabled, etc.

- **xx_toc.yml:** This file is used to modify the different sections of the book. In the section labeled parts, you can add a new section by specifying it's caption (name of section), whether it is numbered or not, and then you may specify the different sub sections within that section by specifying the files associated with that subsections content. 
    - The caption name does not have to be the same name as the directory containing the content for that section (ex. part1 does not have to have the caption: 'part1')
    - It is recommended to keep the different sections labeled part1, part2, part3, ..., as it is easier to keep track of the different sections. However, it is not required as long as the path to the file for the section has the correct directory listed.
    - The basic layout for a section is as follows:
    ```
     - caption: 'Name of section'
        numbered: true
        chapters:
        - file: directory/file
    ```

- **intro_xx.md:** This file is used to create the landing page for the textbook. The content within this file will be the first page displayed when accessing the textbook, lecture notes, or lab manual. 


### Creating Content

Now that you understand the layout of the template, you are ready to start creating content for the textbook.

As was mentioned previously the xx_toc.yml file is used to specify the files that contain the content of the book. It is recommended to use ipynb format, as that will allow you to utilize the full power of the textbook. At the top of every ipynb file, you should include a code cell with the following line: 
```
%run -i ../python/common.py
```

This will enable powerful notebook functions such as: displaying a series of slide images, displaying html table, and displaying interactive terminal media player, just to name a few.

Following this you should specify a title for the subsection by creating a markdown cell and creating an h1 text element:
```
# Title
```

After this, you are able to freely add either code cells or markdown cells and they will be displayed in the same way they appear in the ipynb file.
