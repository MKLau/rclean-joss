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
bibliography: rclean.bib
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
concerns have arisen over the reproducibility of scientific research
[@Peng2011 @Baker2016 @Stodden2018] and the potential issues
related to the complexity and fragility of analytical software
[@Pasquier2017 @Chen2018]. There is now a recognition of the need for
well documented, transparent code and that simply making the code open is
not enough [@Chen2018]. Because of this, tools that can lower the time
and energy required to re-factor and streamline analytical scripts
could have a significant impact on scientific reproducibility across all
disciplines [@Visser2015]. Toward this goal, we have created ``Rclean``
to aid in the automated code reduction to focus on results that are
specifically relevant to a research product, such as a blog, academic
talk or research article.

The ``Rclean`` package provides a simple, easy to use tool for
scientists conducting analyses in the R programing language. Using
graph analytic algorithms, ``Rclean`` isolates the code necessary to
produce a given result (e.g. an object stored in memory or a table or
figure written to disk). This process relies on the
generation of data provenance [@Muniswamy-Reddy2009], which is a
formal representation of the execution of a computational process
(https://www.w3.org/TR/prov-dm/), to rigorously determine the
the unique computational pathway from inputs to the chosen
results. However, as the intended user is a researcher conducting
analyses, the process is abstracted and only the minimum information
is required and presented to the user to streamline the process of
creating "cleaner" code. The output generated by ``RClean`` is the
minimum and sufficient code needed to generate the chosen result.

As statistical programming becomes more common across the sciences,
tools that make the production of accessible code will be an important
aid for improving scientific reproducibility. ``Rclean`` has been
designed to take advantage of recent advances in data provenance
capture techniques to create an easy to use tool for this purpose. New
users can easily install the package from the Comprehensive R Archive
Network (CRAN) [@Lau2018]. The package is open-source and welcomes
contributions. For example, the existing framework could be extended 
to support new provenance capture methods, and there is tremendous 
potential for the use of code cleaning in the creation of more robust 
capsules [@Pasquier2018]. Interested contributors can connect to the 
project at https://github.com/provtools/Rclean. The project is also 
tagged and curated at Zenodo (DOI: 10.5281/zenodo.1208640).


# Citations


<!-- # Figures -->
<!-- Figures can be included like this: ![Example figure.](figure.png) -->

# Acknowledgements

We acknowledge contributions from Brigitta Sipocz, Syrtis Major, and Semyeong
Oh, and support from Kathryn Johnston during the genesis of this project.


# References

