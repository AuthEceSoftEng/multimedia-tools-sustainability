# multimedia-tools-sustainability
This repository holds the experimental setup information regarding the sustainability evaluation of open source multimedia projects

This repository to the following paper submitted at [Sustainability Journal](https://www.mdpi.com/journal/sustainability/special_issues/cultural_heritage_storytelling_engagement_management_era_big_data_semantic_web):  
```
Michail D. Papamichail, Andreas L. Symeonidis

Data Driven Analytics towards Software Sustainability: The case of Open Source Multimedia Tools on Cultural Storytelling
```

## Experimental Setup

1. Use the GitHub API in order to extract the information of the most starred and most forked Java projects and use the `description` and `topics` in order to identify the ones that are related to multimedia.
2. Once having extracted the multimedia-related repositories, use the GitHub API in order to get a full list of commits. Upon getting the commits, sort them by timestamp and get lifecycle of the project. Then, calculate all weeks between the first and the last commit along with the latest commit hash (attribute sha) for each respective week.
3. Download the source code for each respective `commit sha` and perform static analysis (using [SourceMeter Tool](https://www.sourcemeter.com/)) in order to calculate the values of various metrics that quantify four primary source code properties: ***cohesion***, ***complexity***, ***coupling***, and ***inheritance***.
4. Use the static analysis results in order to calculate the progressing behavior of each metric for each project as reflected in its linear trend.
5. Use the analysis results for the latest commit of all projects in order to identify the general behaviour of each metric (apply frequency analysis and polynomial regression).
6. Using the commits information, identify the packages that have been dropped and thus should be considered as candidates for being non-maintainable. In order to conclude for the packages that are being dropped based on reasons that have to do with quality control, apply a series of filtering criteria.
7. Train the maintainability evaluation models, each targeting a certain property, using the aforementioned results (general behaviour of metrics along with progressing behavior). This process employs one-class-classification using SVMs.