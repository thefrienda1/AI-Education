# AI Education: Data and Analysis Code

This repository contains the datasets and analysis code used in the study of AIGC literacy, motivational efficacy, and curriculum-based community structures in higher education.

## Repository Structure

| File                       | Description                                                                                                                                                                                          |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `21_training_schemes.xlsx` | Collected 2021 undergraduate training schemes from the participating schools/departments. These data were used to identify courses shared across schools and construct the curriculum-based network. |
| `common_courses.xlsx`      | List of common undergraduate courses shared by two or more schools/departments.                                                                                                                      |
| `courses1.txt`             | Course-based network after applying an edge-weight threshold of 1.                                                                                                                                   |
| `courses2.txt`             | Course-based network after applying an edge-weight threshold of 2.                                                                                                                                   |
| `courses3.txt`             | Course-based network after applying an edge-weight threshold of 3. This is the primary network used in the main analysis.                                                                            |
| `courses4.txt`             | Course-based network after applying an edge-weight threshold of 4.                                                                                                                                   |
| `courses5.txt`             | Course-based network after applying an edge-weight threshold of 5.                                                                                                                                   |
| `data.xlsx`                | Survey dataset used for the statistical analyses.                                                                                                                                                    |
| `greedy.ipynb`             | Python code for community detection using the Greedy modularity maximization algorithm.                                                                                                              |
| `louvain.ipynb`            | Python code for community detection using the Louvain algorithm.                                                                                                                                     |
| `leiden.ipynb`             | Python code for community detection using the Leiden algorithm.                                                                                                                                      |
| `figure.ipynb`             | Python code used to generate the network/community visualization figures.                                                                                                                            |

## Data and Analysis Workflow

The analysis follows the workflow below:

**Training Schemes → Common Courses → Curriculum Network → Community Detection → Survey Data → Statistical Analysis**

### 1. Curriculum Training Schemes

`21_training_schemes.xlsx` contains the undergraduate training schemes collected from the participating schools/departments.

These training schemes were used to identify courses that were formally shared across schools. Courses shared by two or more schools/departments were defined as common courses and were used to construct the curriculum-based network.

### 2. Common Courses

`common_courses.xlsx` contains the identified common courses.

Each school/departments is represented as a node, and two schools are connected when their undergraduate training schemes contain common courses. The edge weight represents the number of common courses between two schools.

### 3. Network Data and Thresholds

The `courses*.txt` files contain the network data used for community detection.

* `courses.txt`: network without an edge-weight threshold.
* `courses1.txt`: threshold = 1.
* `courses2.txt`: threshold = 2.
* `courses3.txt`: threshold = 3.
* `courses4.txt`: threshold = 4.
* `courses5.txt`: threshold = 5.

The threshold indicates the minimum number of common courses required for an edge to be retained. The network with **threshold = 3** (`courses3.txt`) was selected as the primary network for the main community detection analysis.

### 4. Community Detection

Three community detection algorithms are provided:

* **Greedy modularity maximization** — `greedy.ipynb`
* **Louvain** — `louvain.ipynb`
* **Leiden** — `leiden.ipynb`

The Greedy solution with an edge-weight threshold of 3 was selected as the primary community structure because of its deterministic and reproducible results. The Louvain and Leiden solutions were used for comparison and robustness assessment.

### 5. Survey Data

`data.xlsx` contains the survey data used to examine differences in AIGC literacy and motivational efficacy across curriculum-based communities.

The main variables include:

* Using AIGC
* Evaluating AIGC
* Value Efficacy
* Skill Efficacy
* Usage Efficacy

The dataset used for analysis contains 301 valid responses.

### 6. Visualization

`figure.ipynb` contains the Python code used to generate the curriculum network and community detection visualizations presented in the study.

## Software

The analyses were conducted primarily in **Python**, using Jupyter Notebook (`.ipynb`) files. The notebooks contain the analysis procedures for community detection and network visualization.

## Reproducibility

The files in this repository are provided to facilitate transparency and reproducibility of the analyses reported in the associated study. Researchers may use the training schemes, network files, survey data, and analysis notebooks to reproduce or extend the reported analyses.

## Repository

The complete dataset and analysis code are publicly available at:

https://github.com/thefrienda1/AI-Education
