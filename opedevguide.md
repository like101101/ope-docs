# Open Education Template - developer’s guide

## Introduction

This document is intended to assist the jupyter notebook template developers in understanding and contributing to the templates.  <br>

The OPE project is an initiative towards making education open source, and to achieve highly interactive teaching and presentation material. 

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
