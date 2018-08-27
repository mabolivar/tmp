# Data Science projects' guidelines

## Data analysis pipelines

+ A pipeline breaks up a monolithic make-all-the-things script into discrete, manageable chunks.
+ Each stage of the pipeline defines 
    - its input and its outputs 
    - does not modify its inputs, so it is idempotent.
+ Rerunning a stage of the pipeline produces the same results as the previous run.

![pipelines](http://stat545.com/automation01_slides/images/pipeline.png)

### Advantages

1. When you modify one stage of the pipeline, you don't have to rerun the entire pipeline. *You only rerun the downstream, dependent stages.*
1. Divide up work amongst a group by assigning to each person stages of the pipeline design.
1. You can draw pretty pictures of your pipeline, because a pipeline is a graph.

## File organization

### At minimum

```
name_of_project
|--data
    |--2017report.csv
    |--2016report.pdf
    |--summary2016_2017.csv
|--docs
    |--01-analysis.Rmd
    |--01-analysis.html
|--scripts
    |--01-pull-data-from-source.py
    |--02-exploratory_analysis.R
|--name_of_project.Rproj
|--run_all.R
```

### Optimal

```
name_of_project
|--data
	|--raw
		|--WhateverData.xlsx
    	|--2017report.csv
    	|--2016report.pdf
	|--tidy
    	|--summary2016_2017.csv
|--docs
    |--01-analysis.html
    |--01-analysis.pdf
    |--02-deeper.html
    |--02-deeper.pdf
|--images
	|--figure-01.png
	|--figure-02-png
|--models
	|--logistic-regression.cls
	|--random-forest.rds
	|--gams.xml
|--scripts
    |--01-pull-data-from-source.py
    |--02-clean-and-prepare-data.py
    |--03-train-predictive-model.R
|--name_of_project.Rproj
|--run_all.R
|--README.md
```


## Resources

+ Automating data analysis pipelines
    - [Website](http://stat545.com/automation00_index.html)
    - [Slides](http://stat545.com/automation01_slides/index.html#/automating-data-analysis-pipelines)
+ [File organization best practices](https://andrewbtran.github.io/NICAR/2018/workflow/docs/01-workflow_intro.html)
