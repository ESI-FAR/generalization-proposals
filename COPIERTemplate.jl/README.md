# 1. General information

## Title

Best practices for Julia package development using COPIERTemplate.jl. (COPIERTemplate.jl)

## Project and call

ESI-FAR.

## Team

Lead RSE: Abel Soares Siqueira

Proposed composition of the team (Mention RSEs): ESI-FAR team.

Role of the SIT (software impact team): Who?

## Expertise

Julia development. Package development best practices. Software quality best practices.

## Requested budget

6 person months.

## Start date

Proposed start date: 01/March

## Duration

Proposed duration in months: 18 months.

## Embedding in the eScience Center

Please indicate the names of the SH(s) and PM(s) this proposal was discussed with: Nico and Rena.

## Earlier agreements

No agreements.

# 2. The project

## Abstract

_Describe the project. Explicitly formulate the goals of the project. Describe the challenges and proposed solutions. Consider, for example, challenges related to technology, community, training, governance, etc._

COPIERTemplate.jl is a template for the engine Copier. It contains opinionated software development best practices that we adopt in some of our packages. These include traditional Julia package requirements, such as a src, test and docs folder structure, README and LICENSE files, GitHub workflows for testing, documentation, CompatHelper and TagBot. However, it also includes other best practices, such as linting and formatting specification files, pre-commit hooks, and CITATION.cff files.
COPIERTemplate.jl can be applied and reapplied to existing packages, as supported by Copier. This means that the best practices can be updated in the template and propagated to packages using it. This solves issues with outdated practices and also allows older packages to improve their package very quickly.
COPIERTemplate.jl is also a Julia package, created from the template that it stores. As a package, it wraps some functionalities of Copier to allow users to use the template without having to install Copier directly.
Finally, COPIERTemplate.jl has a GitHub workflow that automatically checks for updates for the template and tries to apply it in the current project.

## Relevance

This project increases quality and sustainability for other packages in the Julia ecosystem.
It is a template, so it reusable by default.
The focus of our work will be increasing usability and dissemination of the software and of the best practices that it provides.

## Scope

Here are some tasks that define the scope:

- Implement more best practices: COPIERTemplate.jl has been released, but it currently only supports some of the best practices that we adopt in other projects. Implementing these tasks in the template is the bulk of the work. Furthermore, we should investigate what other well-maintained packages are doing and steal what is useful. We should make sure that the most disruptive or divisive features are optional/have alternatives.
- Implement more of the Copier interface: Currently, we only apply the template. It should be useful to add functionalities for updating as well.
- Polish the auto-update feature: The auto-update feature works well when there are no conflicts. We need to decide how to better handle the conflicts in a user-friendly way and test the feature.
- Apply the template to some packages in and outside of our organization: As a dissemination task, we can apply the template, with permission of the package authors, to existing packages.
- Document and/or use auto-generating issues to indicate next steps: Like in the Python template, there are manual steps to be taken after a repo has been created. In addition to documentation, the Python template also includes workflows that generate issues for these tasks.

Out of scope:

- Providing a full alternative to PkgTemplates.jl. That package has many edge cases, some of which are not desired anymore.
- Implementing a template engine.

# 3. Status of the code

## Link to codebase

Package Repo: <https://github.com/abelsiqueira/COPIERTemplate.jl>

There is no link to RSD, since this package is not part of the eScience Center yet.

The package where we first implemented these best practices is TulipaEnergyModel.jl: <https://github.com/TulipaEnergy/TulipaEnergyModel.jl>.

RSD for TulipaEnergyModel: https://research-software-directory.org/software/tulipaenergymodel

## Description

The status of the code is that it is barely usable.
The basic infrastructure has been created as a proof of concept, and some issues were created to keep track of work.

# 4. Plan

## Tasks & Timeline

As described above:

- T1: Implement more best practices
- T2: Implement more of the Copier interface
- T3: Polish the auto-update feature
- T4: Apply the template to some packages in and outside of our organization
- T5: Document and/or use auto-generating issues to indicate next steps

The work will happen mostly in that order, with the following rough distribution:

- T1: 60% of the time.
- T2: 5% of the time.
- T3: 15% of the time.
- T4: 10% of the time.
- T5: 10% of the time.

## Deliverables

- We can produce a software paper for the package, for instance in the Journal of Open Source Software.
- We can present the package in JuliaCon 2024 (Abel will submit this to JuliaCon 2024 either way) or 2025.
- The package might impact the whole Julia ecosystem and the eScience Center will be co-author of a main package related to software best practices.
- Specific to ESI-FAR, this will help make sure that the packages that we develop in NextGenOpt and possibly in MOPO follow software best practices.

# 5. Landscaping / Relation with existing technologies

- [Julia's default Pkg.jl generate command](https://pkgdocs.julialang.org/v1/creating-packages/): This is a very basic tool to create the minimum for a Julia project - a UUID and a src file structure. It does not include even the minimum required to release a package.
- [PkgTemplates.jl](https://github.com/tpapp/PkgSkeleton.jl): This is by far the most common template in Julia. It includes several choices that are and were common in Julia. It is a pure Julia solution that includes the template engine, so the templating and the engine are coupled. This makes the inclusion of new options much harder, which makes the package outdated at times. Furthermore, it does not allow reapplication of the template, which means that new additions are not immediately available for current template users. COPIERTemplate.jl should provide a subset of choices - based on what is most up-to-date and desired - while being much easier to maintain and update. Furthermore, COPIERTemplate.jl can also be applied to projects that were created with PkgTemplates.jl, so existing users can still migrate to COPIERTemplate.jl.
- [PkgSkeleton.jl](https://github.com/tpapp/PkgSkeleton.jl): A lightweight template generator. It lacks information (README is sparse and there is no documentation), so it doesn't deal with the main task of improving best practices.

# 6. Impact & Sustainability

The project is, by design, focused on reusability.
If adopted, it will impact many packages across disciplines.
It can be adopted by virtually every single package developer in the Julia ecosystem, just like our Python template.

We will share the knowledge of this project in the Lightning talks and possibly in the Software Sustainability SIG.

Part of the project involves applying the template to other existing communities.
By talking to these other communities, we attract the attention of possible developers.
We will also submit it to JuliaCon, which will make it very visible.

# 7. Comments

No comments.
