---
title: 'Rclean: A Tool for Writing Cleaner, More Transparent Code'
tags:
  - R
  - reproducibility
  - open-science
  - transparency
  - code cleaning
  - data provenance
authors:
  - name: Matthew K. Lau
    orcid: 0000-0003-3758-2406
    affiliation: 1
  - name: Thomas F.J.M. Pasquier
    orcid: 0000-0000-0000-0000
    affiliation: "2, 3" # (Multiple affiliations must be quoted)
affiliations:
 - name: Harvard Forest, Harvard University 
   index: 1
 - name: Department of Computer Science, University of Bristol 
   index: 2
 - name: Department of Computer Science and Engineering, Harvard University
   index: 3
date: 21 January 2019
bibliography: rclean-joss.bib
---

<!-- JOSS welcomes submissions from broadly diverse research areas. For -->
<!-- this reason, we request that authors include in the paper some -->
<!-- sentences that would explain the software functionality and domain of -->
<!-- use to a non-specialist reader. Your submission should probably be -->
<!-- somewhere between 250-1000 words. -->

<!-- In addition, your paper should include: -->

<!-- - A list of the authors of the software and their affiliations -->
<!-- - A summary describing the high-level functionality and purpose of the software for a diverse, non-specialist audience -->
<!-- - A clear statement of need that illustrates the purpose of the software -->
<!-- - A list of key references including a link to the software archive -->
<!-- - Mentions (if applicable) of any ongoing research projects using the software or recent scholarly publications enabled by it -->

<!-- As this short list shows, JOSS papers are only permitted to contain a -->
<!-- limited set of metadata (see header below), Statement of Need, -->
<!-- Summary, and Reference sections. You can see an example accepted paper -->
<!-- here. Given this paper format, a "full length" paper is not permitted, -->
<!-- e.g., software documentation such as API (Application Programming -->
<!-- Interface) functionality should not be in the paper and instead should -->
<!-- be outlined in the software documentation. -->

<!-- *Important*: You paper will be reviewed by one or more reviewers in -->
<!-- a public GitHub issue. Take a look at the `review criteria -->
<!-- <review_criteria.html>`_ to better understand how your submission will -->
<!-- be reviewed. -->


<!-- Submitting your paper -->

<!-- Submission then is as simple as: -->
<!-- Filling in the short submission form -->
<!-- Waiting for reviewers to be assigned over in the JOSS reviews -->
<!-- repository: https://github.com/openjournals/joss-reviews -->

<!-- Submission requirements -->

<!-- - The software should be open source as per the OSI definition -->
<!-- - The software should have an obvious research application -->
<!-- - You should be a major contributor to the software you are submitting -->
<!-- - The software should be a significant contribution to the available -->
<!--   open source software that either enables some new research -->
<!--   challenges to be addressed or makes addressing research challenges -->
<!--   significantly better (e.g., faster, easier, simpler) -->
<!-- - The software should be feature complete (no half-baked solutions) -->
<!--   and designed for maintainable extension (not one-off -->
<!--   modifications). Minor ‘utility’ packages, including ‘thin’ API -->
<!--   clients, are not acceptable. -->

<!-- In addition, the software associated with your submission must: -->

<!-- - Be stored in a repository that can be cloned without registration -->
<!-- - Be stored in a repository that is browsable online without -->
<!--   registration -->
<!-- - Have an issue tracker that is readable without registration -->
<!-- - Permit individuals to create issues/file tickets against your -->
<!--   repository -->

<!-- JOSS publishes articles about research software. This definition -->
<!-- includes software that: solves complex modeling problems in a -->
<!-- scientific context (physics, mathematics, biology, medicine, social -->
<!-- science, neuroscience, engineering); supports the functioning of -->
<!-- research instruments or the execution of research experiments; -->
<!-- extracts knowledge from large data sets; offers a mathematical -->
<!-- library, or similar. -->

<!-- Authorship -->

<!-- Purely financial (such as being named on an award) and organizational -->
<!-- (such as general supervision of a research group) contributions are -->
<!-- not considered sufficient for co-authorship of JOSS submissions, but -->
<!-- active project direction and other forms of non-code contributions -->
<!-- are. The authors themselves assume responsibility for deciding who -->
<!-- should be credited with co-authorship, and co-authors must always -->
<!-- agree to be listed. In addition, co-authors agree to be accountable -->
<!-- for all aspects of the work. -->

<!-- Submissions using proprietary languages/dev environments -->

<!-- We strongly prefer software that doesn't rely upon proprietary (paid -->
<!-- for) development environments/programming languages. However, provided -->
<!-- your submission meets our submission requirements (including having a -->
<!-- valid open source license) then we will consider your submission for -->
<!-- review. Should your submission be accepted for review, we may ask you, -->
<!-- the submitting author, to help us find reviewers who already have the -->
<!-- required development environment installed. -->

<!-- The review process -->

<!-- After submission: -->

<!-- - One or more JOSS reviewers are assigned and the review is carried -->
<!--   out in the reviews repository -->
<!-- - Authors respond to reviewer-raised issues (if any are raised) on the -->
<!--   submitted repository's issue tracker. -->
<!-- - Reviewer contributions, like any other contributions, should be -->
<!--   acknowledged in the repository -->
<!-- - Upon successful completion of the review, deposit a copy of your -->
<!--   (updated) repository with a data-archiving service such as Zenodo or -->
<!--   figshare, issue a DOI for the archive, and update the review issue -->
<!--   thread with your DOI -->
<!-- - After assignment of a DOI, your paper metadata is deposited in -->
<!-- CrossRef and listed on the JOSS website And that's it -->
<!-- - If you want to learn more about what the review process looks like -->
<!--   in detail, take a look at the reviewer guidelines. -->

# Summary

The growth of open-source statistical software programming has been
explosive in the last decade. In particular, the statistical
programming language ``R`` has grown exponentially to become one of
the top ten programming languages in use today. However, recently
concerns have arisen over the reproducibility of science
[@Stodden2018] and the potential contribution made by the complexity
and fragility of analytical software
[@Pasquier2017 @Trisovic2018]. Because of this, tools that can lower
the time and energy required to re-factor and streamline analytical
scripts could have significant impact on scientific reproducibility
across all of science. Toward this goal, we have created ``Rclean`` to
aid in the rapid reduction of code to focus on results that are
specifically relevant to a research product, such as a blog, academic
talk or research article.

The ``Rclean`` package provides a simple, easy to use tool for
scientists conducting analyses in the R programing language. Using
graph analytic algorithms, ``Rclean`` isolates the code necessary to
produce a chosen result (e.g. an object stored in memory or a table or
figure that was writtin to disk). This process relies on the
generation of data provenance, which is a formal representation of the
execution of a computational process [@W3C], in order to rigorously
determine the unique computaional pathway from inputs to the chosen
results. However, as the intended user is a researcher conducting
analyses, the process is abstracted and only the minimum information
is required and presented to the user to streamline the process of
creating "cleaner" code.

As statistical programming becomes more common across the sciences,
tools that make the production of accessible code will be an important
aid for improving scientific reproducibility. ``Rclean`` has been
designed to take advantage of recent advances in data provenance
capture techniques to create an easy to use tool for this purpose. New
users can easily install the package from the Comprehensive R Archive
Network (CRAN) [@Lau2018]. The package is open-source and welcomes
contributions who are working in this area. For example, new
provenance capture methods could be easily implemented into the
existing framwork, and there is tremendous potential for the use of
code cleaning in the creation of more robust copsules
[@Pasquier @CodeOcean @Gigantum @CoRE2 @DataVerse]. Interested
contributors can connect to the project at
https://github.com/provtools/Rclean. The project is also tagged and
curated by Zenodo (DOI: 10.5281/zenodo.1208640).


# Citations


<!-- # Figures -->
<!-- Figures can be included like this: ![Example figure.](figure.png) -->

# Acknowledgements

We acknowledge contributions from Brigitta Sipocz, Syrtis Major, and Semyeong
Oh, and support from Kathryn Johnston during the genesis of this project.


# References

<!-- Example paper.bib file: -->

<!-- @article{Pearson:2017, -->
<!--   	Adsnote = {Provided by the SAO/NASA Astrophysics Data System}, -->
<!--   	Adsurl = {http://adsabs.harvard.edu/abs/2017arXiv170304627P}, -->
<!--   	Archiveprefix = {arXiv}, -->
<!--   	Author = {{Pearson}, S. and {Price-Whelan}, A.~M. and {Johnston}, K.~V.}, -->
<!--   	Eprint = {1703.04627}, -->
<!--   	Journal = {ArXiv e-prints}, -->
<!--   	Keywords = {Astrophysics - Astrophysics of Galaxies}, -->
<!--   	Month = mar, -->
<!--   	Title = {{Gaps in Globular Cluster Streams: Pal 5 and the Galactic Bar}}, -->
<!--   	Year = 2017 -->
<!-- } -->

<!-- @book{Binney:2008, -->
<!--   	Adsnote = {Provided by the SAO/NASA Astrophysics Data System}, -->
<!--   	Adsurl = {http://adsabs.harvard.edu/abs/2008gady.book.....B}, -->
<!--   	Author = {{Binney}, J. and {Tremaine}, S.}, -->
<!--   	Booktitle = {Galactic Dynamics: Second Edition, by James Binney and Scott Tremaine.~ISBN 978-0-691-13026-2 (HB).~Published by Princeton University Press, Princeton, NJ USA, 2008.}, -->
<!--   	Publisher = {Princeton University Press}, -->
<!--   	Title = {{Galactic Dynamics: Second Edition}}, -->
<!--   	Year = 2008 -->
<!-- } -->

<!-- @article{zenodo, -->
<!--   	Abstractnote = {Gala is a Python package for Galactic astronomy and gravitational dynamics. The bulk of the package centers around implementations of gravitational potentials, numerical integration, and nonlinear dynamics.}, -->
<!--   	Author = {Adrian Price-Whelan and Brigitta Sipocz and Syrtis Major and Semyeong Oh}, -->
<!--   	Date-Modified = {2017-08-13 14:14:18 +0000}, -->
<!--   	Doi = {10.5281/zenodo.833339}, -->
<!--   	Month = {Jul}, -->
<!--   	Publisher = {Zenodo}, -->
<!--   	Title = {adrn/gala: v0.2.1}, -->
<!--   	Year = {2017}, -->
<!--   	Bdsk-Url-1 = {http://dx.doi.org/10.5281/zenodo.833339} -->
<!-- } -->

<!-- @article{gaia, -->
<!--     author = {{Gaia Collaboration}}, -->
<!--     title = "{The Gaia mission}", -->
<!--     journal = {\aap}, -->
<!--     archivePrefix = "arXiv", -->
<!--     eprint = {1609.04153}, -->
<!--     primaryClass = "astro-ph.IM", -->
<!--     keywords = {space vehicles: instruments, Galaxy: structure, astrometry, parallaxes, proper motions, telescopes}, -->
<!--     year = 2016, -->
<!--     month = nov, -->
<!--     volume = 595, -->
<!--     doi = {10.1051/0004-6361/201629272}, -->
<!--     adsurl = {http://adsabs.harvard.edu/abs/2016A%26A...595A...1G}, -->
<!-- } -->

<!-- @article{astropy, -->
<!--     author = {{Astropy Collaboration}}, -->
<!--     title = "{Astropy: A community Python package for astronomy}", -->
<!--     journal = {\aap}, -->
<!--     archivePrefix = "arXiv", -->
<!--     eprint = {1307.6212}, -->
<!--     primaryClass = "astro-ph.IM", -->
<!--     keywords = {methods: data analysis, methods: miscellaneous, virtual observatory tools}, -->
<!--     year = 2013, -->
<!--     month = oct, -->
<!--     volume = 558, -->
<!--     doi = {10.1051/0004-6361/201322068}, -->
<!--     adsurl = {http://adsabs.harvard.edu/abs/2013A%26A...558A..33A} -->
<!-- } -->
