 
+++

title = "ScaRLib presentation for LSS course"
description = "ScaRLib presentation for LSS course"
outputs = ["Reveal"]
aliases = [
    "/guide/"
]

+++

# ScaRLib
## A Framework for Cooperative Many Agent Deep Reinforcement Learning in Scala

##### *Davide Domini, Filippo Cavallari*

Laboratory of  Software Systems @ University of Bologna

---

# Introduction

--- 

# Tools

<image src="./imgs/tools.jpeg" >

---

# Domain Analysis: Knowledge Crunching

---

# Domain Analysis: Ubiquotous Language

---

# Domain Analysis: Core Domain Chart

---

# Design

---

# DevOps: Repository Management

* {{< frag c="To track the development of our project we created a GitHub organization called `ScaRLib-group`." >}}
* {{< frag c="The main repository that contains the code is called `ScaRLib`." >}}
* {{< frag c="To manage the repository GitFlow was used" >}}
  * {{< frag c="The branch `Main` contains project releases" >}}
  * {{< frag c="The branch `Develop` was used for ongoing development" >}}
  * {{< frag c="For each feature a branch `feature/feature-name` was used" >}}
* {{< frag c="Commits were written following the [Conventional Commit](https://www.conventionalcommits.org/en/v1.0.0/) approach." >}}
* {{< frag c="The organization contains also some secondary repositories that are useful for speeding up the use of the tool" >}}

---

# DevOps: Build Automation

* To manage the project structure `Gradle` was used.
* The project was organized into three sub-projects:
  * `scarlib-core`
  * `dsl-core`
  * `alchemist-scafi`
* Thanks to Gradle, we were able to easily manage dependencies between the sub-projects and third-party libraries. 
* We also utilized Gradle for customized tasks (e.g., jars generation).

---

# DevOps: Continuous Integration 

To automate the CI process, `GitHub Actions` were utilized. The workflow has been divided into the following steps:
1. `Test`: runs (on many operating systems) available tests for the ScaRLib project.
2. `Release`: if tests were successful, the semantic-release tool is executed, which will automatically create a new release of the software if needed.
3. `Success`: checks if all previous jobs were successful, it is used for branch protection.">

<image src="./imgs/ci-resume.png" width="75%">

--- 

# DevOps: Versioning and Releasing

* To distinguish different versions of the software, the guidelines proposed by [Semantic Versioning](https://semver.org/) have been followed.

* The correct version to be associated with the software state is based on the saved commits, which were written following the Conventional Commit approach. For example:
  * **MAJOR** release: Any commit type and scope terminating with `!` causes a `BREAKING CHANGE`
  * **MINOR** release: Commit type `feat` (*Features*) with any scope
  * **PATCH** release: Commit type `fix` (*Bug Fixes*) with any scope
  * **NO** release: Commit type `ci` (*Build and continuous integration*)
* ScaRLib is currently released on the [Maven Central](https://central.sonatype.com/?smo=true) platform, making it easy and quick to find dependencies to import ScaRLib into new projects.


---

# License

ScaRLib is distributed under the terms of the GNU General Public License (GPL-3.0).

| Permissions | Limitations | Conditions |
| ------------ |------------ |------------ |
✅ Commercial use | ❌ Liability  | ℹ License and copyright notice |
✅ Modification | ❌ Warranty | ℹ State changes |
✅ Distribution |  |  ℹ Disclose source |
✅ Patent use |  |  ℹ Same license  |
✅ Private use |  |  |
| | |

A full copy of the GNU General Public License can be found [here](https://www.gnu.org/licenses/).


---

# Future Work


Possible additional features that can be implemented in the future, in addition to those already present, thanks to the modularity of the system, may include the following:

- Add the ability to use neural networks of any type, not just feed-forward (e.g., CNN and/or RNN).
- Add more default learning algorithms (e.g., [MAPPO]).
- Consider integrating other tools for simulating the environment (e.g., [FlameGPU]).

[MAPPO]: https://sites.google.com/view/mappo
[FlameGPU]: https://flamegpu.com/
