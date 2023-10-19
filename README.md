# FE2_Documentation

[**Access link to documentation**](https://ffw-baudenbach.github.io/FE2_Documentation/)

The documentation is generated automatically generated on every change from the [docs](/docs) folder.

## How it works

This approach uses [MkDocs](https://mkdocs.org) to generate static html files out of markdown files.  
We use the template [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) for visualization.

The generated Website is hosted as *GitHub Page* directly with this project.  

Changes to documentation on the main branch in the [/docs](/docs) folder will generate and deploy the documentation automatically.  

Configuration is done inside [mkdocs.yml](mkdocs.yml) file.  
All template related configurations are done inside the [template.yml](template.yml) file.

## How to develop locally

* Install Python
* Clone this repository
* Run `pip install --upgrade -r requirements.txt` (might need administrator rights)
* Run `mkdocs serve`
* Access [http://localhost:8000](http://localhost:8000) in browser
* Any change will reload the browser automatically

## How to update local installation

* Run `pip install --upgrade -r requirements.txt` again (might need administrator rights)
