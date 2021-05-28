# Downloads

## Competition report
[![arXiv](https://img.shields.io/badge/cs.CV-arXiv%3A2105.13265-B31B1B.svg)](https://arxiv.org/abs/2105.13265)

The competition report summarizes competition challenges and tasks, evaluation protocol, method descriptions and evaluation results.
We provide an author copy of the official report published in ICDAR's proceedings, archived on arXiv.


## Dataset 
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.4817662.svg)](https://doi.org/10.5281/zenodo.4817662)

For each task, we provide a folder containing inputs **and expected outputs (ground truth)**:

- `1-detbblock` is for Task 1: “Detect Building Blocks”;
- `2-segmaparea` is for Task 2: “Segment Map Area”;
- `3-locglinesinter` is for Task 3: “Locate Graticule Line Intersections”.

For each of those tasks, we provide a training set, a validation set and a test set.

- `$TASK/train` contains sample inputs and expected outputs to be used to train your method.  
  File names in this set start with `1NN`.
- `$TASK/validation` contains sample inputs and expected outputs to be used to assess the performance of your method without touching the test set.  
  It should be used to calibrate the hyper-parameters of your approach.  
  File names in this set start with `2NN`.
- `$TASK/test` contains sample inputs and expected outputs to be used to measure and report the final performance of your method.  
  File names in this set start with `3NN`.


## Participants' submissions, descriptions and evaluation reports
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.4818228.svg)](https://doi.org/10.5281/zenodo.4818228)

We released submitted results and methods descriptions from competition's participants,
along with the evaluation results we computed.

Content is organized as follows.

- Descriptions of their methods submitted by participants are available in the `descriptions/` folder.
- Results submitted by participants are available in the `task-1/`, `task-2/` and `task-3/` folders.
- Metrics computed by competition organizers are available in the `evaluation_t1/`, `evaluation_t2/` and `evaluation_t3/` folders.


## Evaluation tools
[![DOI](https://zenodo.org/badge/347978686.svg)](https://zenodo.org/badge/latestdoi/347978686)

Easy PIP installation:
```shell
pip install -U icdar21-mapseg-eval
```

Evaluation tools are open-source Python 3.7+ programs [available on GitHub](https://github.com/icdar21-mapseg/icdar21-mapseg-eval) and [archived on Zenodo](https://zenodo.org/badge/latestdoi/347978686).

Please check the [documentation for the evaluation tools](https://github.com/icdar21-mapseg/icdar21-mapseg-eval/blob/main/README.md) for more details about how to install them.

