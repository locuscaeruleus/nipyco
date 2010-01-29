Possible titles
---------------

* Reproducible Brain Imaging Results with Nipype
* Why should I use Nipype to run my spm or fsl analysis?
* Nipype to run spm or FSL analysis

Authors
-------

* Satrajit Ghosh
* Chris Burns
* Dav Clark
* Cindee Madison
* Rosalia Tungaraza
* K. Jarrod Millman


Introduction
------------

Nipype is a project under the umbrella of Nipy, an effort to develop
open-source, community-developed neuroimaging tools in Python.  The
goals of Nipype are two-fold.  First, to provide a uniform interface
to existing neuroimaging software packages.  Second, to provide a
pipeline structure which allows for parallel processing, simple
parameter sweeping, interoperability between packages, reproducible
analyses, and easy pipeline visualization.

Nipype aims to: (1) encourage the scientific exploration of different
algorithms and associated parameters; (2) ease the development of
workflows within and between packages; (3) reduce the learning
curve associated with understanding the algorithms, APIs and user
interfaces of disparate packages; (4) provide a plugin like
environment for developers to create and test new cross-package
algorithms; and (5) provide a collaborative environment for
neuroimaging software development in a high-level language. These aims
address some limitations of existing neuroimaging pipeline
systems (e.g., LONIPipeline, CaMBA, MIPAV, BioImageSuite). 


Methods
-------

Nipype is an open-source project hosted SourceForge and written in the
Python programming language, a freely available, high-level language
that is accessible to both programmers and non-programmers.  Our
documentation is written in a light-weight markup language called
Restructured Text, from which print-quality HTML and PDF documentation
are generated using the Sphinx Python application.  The source code is
tested using the Nose Python testing framework to ensure robustness
and to allow for easier code mainenance. Using IPython, Nipype can be
used interactively or in a distributed computing mode. Nipype is
released frequently to provide users with prompt bug fixes and feature
updates, and has a release cycle of every two months. Figure 1 shows
the component architecture of nipype.

The interface component provides access to the individual programs and
functions from external packages, such as SPM, FSL, and Freesurfer.
Internally, each algorithm in the external package is wrapped in a
Python class with each algorithm parameter mapped to a class
attribute.  Researchers can get or set the parameter attributes and
call a run method to execute the algorithm with the supplied
parameters.  (See Fig. 1 for an overview of the component architecture)

The pipeline component provides the framework for connecting interface
nodes to form a complete analysis workflow. The workflow is
represented in a directed acyclic graph (DAG), enabling efficient use
of existing scheduling algorithms and ensuring operational
consistency (see Fig. 2 for an example workflow). Provenance
information is stored during each stage of the pipeline, including
information about the working environment, the parameter values passed
to the algorithms and an md5 hash of the input state. The md5 hash
which is computed based on contents of files determines if a stage
needs re-execution or can safely be skipped.

The pipeline mechanism allows one to easily compare ... XXX
the effects of 
algorithms or method on a given set of identical inputs and a
determine the effects of varying individual nodes on the entire workflow, use optimized
algorithms from different packages in the same workflow and distribute
the computation across computers.

Graph visualization of pipeline
Some examples (choose as you please):

* `SPM FreeSurfer pipeline <http://dl.dropbox.com/u/363467/fs_spm_graph.dot.png>`_

* `SPM Level1 pipeline <http://dl.dropbox.com/u/363467/spm_graph.dot.png>`_

* `SPM detailed level1 pipeline <http://dl.dropbox.com/u/363467/spm_graph_detailed.dot.png>`_

Parallel (ref Fernando)


Results
-------

Used at MIT BErkeley MGH
DTI?
Used on motor tasks, perception, PET, ...
avoidance of redundant expensive computation, reduces duplication in
parallel or nearly parallel pipelines

Encourages exploration of algorithm parameter changes
The pipeline allows one to easily compare algorithms [expand on this]



Very reproducible
easy to keep track of whats been done, and how



Conclusion
----------

Growing developer community
Future plans
(add afni,  ANTS, direct interface to nipy)
Good opportunity for comparative validation of tools and algorithms
Data more sematically annotated (go into detail)
query on data,
Web interface
running on large cluster with Large Scale studies
instituion wide stnadardized diagnostics

facilitates training
