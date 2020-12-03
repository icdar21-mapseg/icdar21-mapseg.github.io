# Overview
<!--
Generated using https://online.officetimeline.com
See source in timeline_data/source.xls
-->
<!-- <center> -->
[![Competition timeline](img/timeline.png)  ](img/timeline.png)
<!-- *Competition timeline ([link to larger view](img/timeline.png))* -->
<!-- </center> -->

[Downloads](downloads.md){: .btn}
[Subscribe to updates](contact.md#subscribe-to-updates){: .btn}
[Registration](registration.md){: .btn}

*Brought to you by*
*the [LASTIG](https://www.umr-lastig.fr/) team of the [IGN](https://ign.fr/) (the French National Mapping Agency),*
*the [R&D Lab](https://www.lrde.epita.fr/). of the [EPITA](https://www.epita.fr/) (French engineering school in computer science),*
*and the [Center of Historical Studies](http://crh.ehess.fr/) of the [EHESS](https://www.ehess.fr/) (French graduate schools of social sciences).*

## Important dates

| From       | To / On    | Title                                                               | Tasks |
| ---------- | ---------- | ------------------------------------------------------------------- | ----- |
|            | 2020-11-18 | Train and validation sets available                                 | all   |
| 2020-11-18 | 2021-04-05 | Training phase                                                      | all   |
|            | 2021-03-31 | Registration deadline for competition participants                  | all   |
|            | 2021-04-05 | Test datasets available                                             | 1     |
| 2021-04-05 | 2021-04-09 | Test phase                                                          | 1     |
|            | 2021-04-09 | Submission deadline for results                                     | 1     |
|            | 2021-04-12 | Test datasets available                                             | 2&3   |
| 2021-04-12 | 2021-04-16 | Test phase                                                          | 2&3   |
|            | 2021-04-16 | Submission deadline for results                                     | 2&3   |
| 2021-04-12 | 2021-04-23 | Write short method description                                      | all   |
|            | 2021-04-23 | Method descriptions due                                             | all   |
|            | 2021-07-01 | Full data disclosure: round truth for test set, participant results | all   |

<br>

<!-- ## How to register?
Please check the [Registration page](registration.md). -->

<!-- ## How to download dataset and evaluation tools?
- The **train and validation sets** for all tasks are available under the [Downloads page](downloads.md).
- **Evaluation tools** will be **open sourced soon** so participant can check their results themselves.
- **Test sets** for all tasks will be released **at the start of the test phase.**
- **All competition material** (full dataset, participant results, evaluation tools) will be released publicly **at the end of the competition.** -->

## About the competition
This competition consists in solving several challenges which arise during the digitization of historical maps.
We are particularly interested in a large map series consisting in many Paris atlases over half a century (1860's-1940's).
For each year, a set of approximately 20 sheets forms a tiled view of the city.
Such maps are highly detailed and very accurate even in modern standards.
The **graphical nature of the content** is visible in the full map sheet illustrated below.

<center>
![A sample map sheet](img/map_large_in.jpg) 
*A sample map sheet ([link to larger version](img/map_large_in.jpg))* <!-- FIXME add really larger image -->
</center>

This material provides a very valuable resource for historians and a **rich body of scientific challenges** for the document analysis and recognition (DAR) community: map-related challenges (overlapping of many information layers) and document-related ones (document preservation).

<center>
![Excerpt showing map-related challenges](img/challenges_map_related.jpg)
*Excerpt showing map-related challenges*
</center>

<center>
![Excerpt showing document-related challenges](img/challenges_doc_related.jpg)
*Excerpt showing document-related challenges*
</center>

We expect this competition to provide solutions for three levels of scientific problems:

- [Task 1: Detection of building blocks](tasks/task1.md)
- [Task 2: Segmentation of map content within map sheets](tasks/task2.md)
- [Task 3: Localization of graticule lines intersections](tasks/task3.md)

These tasks are necessary step during the digitization of historical maps, ie when gradually turning a raster image into a set of vector geometries projected onto a particular geographical coordinate reference system.
Automatic approaches with good generalization power will provide an enormous gain for the Geographical Information Systems (GIS) communities looking for solutions when digitizing old maps,
and create a great potential for many historical studies.


## Key strengths for participants
- All datasets and evaluation tools are released with an **open licence** as soon as they are available.
- Winners of each task will be invited to **co-author** the report paper.
- We propose unsolved research problems with an **important potential impact**.
  