## Centralized Version Control Systems

![Centralized VCS](https://raw.githubusercontent.com/DanySK/shared-slides/e375d394b0eb319d6c5b9b6a7a2c707dc347b7ac/git/centralized-vcs.svg)

---

## Decentralized VCS

![Decentralized VCS](https://raw.githubusercontent.com/DanySK/shared-slides/e375d394b0eb319d6c5b9b6a7a2c707dc347b7ac/git/decentralized-vcs.svg)

---

## Real-world DVCS

![Real-world Decentralized VCS](https://raw.githubusercontent.com/DanySK/shared-slides/e375d394b0eb319d6c5b9b6a7a2c707dc347b7ac/git/dvcs-sink.svg)

---

## Git repository hosting

Several services allow the creation of *shared repositories on the cloud*.
They *enrich* the base git model with services built around the tool:

* **Forks**: copies of a repository associated to different users/organizations
* **Pull requests** (or **Merge requests**): formal requests to *pull* updates from *forks*
  * repositories do not allow pushes from everybody
  * what if we want to contribute to a project we cannot push to?
    * *fork* the repository (we *own* that copy)
    * write the contribution and push to our *fork*
    * ask the maintainers of the *original repository* to *pull from* our fork
* **Issue tracking**

---

## Most common services

* **GitHub**
  * Replaced Sourceforge as the *de-facto standard* for open source projects hosting
  * *Academic plan*
* **GitLab**
  * Available for free as *self-hosted*
  * Userbase grew when Microsoft acquired GitHub
* **Bitbucket**
  * From Atlassian
  * Well integrated with other products (e.g., Jira)


---

## GitHub

* *Hosting* for git repositories
* *Free for open source*
* *Academic accounts*
* *De-facto standard* for open source projects
* One *static website* per-project, per-user, and per-organization
  * (a feature exploited by these slides)

---

# DVCS: Workflows

> with great power comes great responsibility

and also

> power is nothing without control

Elements to consider:
* How *large* is the team?
* How *complex* is the project?
* Do team members work *together* (in spacetime)?
* Do team members *trust* each other?

---

## Trunk-based(-like) development

![Trunk-based development (like)](https://raw.githubusercontent.com/DanySK/shared-slides/e375d394b0eb319d6c5b9b6a7a2c707dc347b7ac/git/dvcs-sink.svg)

---

## Trunk-based(-like) development


Single branch, shared truth repository, frequent merges

* *Small* teams, *low-complexity* projects, *colocated* teams, *high* trust
* Typical of small company projects

---

## Git flow (classic)

![Git flow](https://raw.githubusercontent.com/DanySK/shared-slides/e375d394b0eb319d6c5b9b6a7a2c707dc347b7ac/git/dvcs-flow-sink.svg)

---

## Git flow (classic)

Multiple branches, shared truth repository

* *Large* teams, *high-complexity* projects, *preferably colocated* teams, *high* trust
* Typical of large company projects

---

{{% import path="shared-slides/git/git-flow.md" %}}

---

## Forks versus branches

* In Git, separate *development lines* are separate *branches*
* However, everyone has a *copy* of the *same repository*
* Git *hosting services* can *identify copies* of the same project belonging to different users

These copies are called **forks**

* Branches on one fork can be requested to be merged on another fork
  * With **merge request** (also called **pull request**, depending on the host)
* Pull requests enable easier code review
  * Necessary when the developer *does not trust* the contributor
  * But very useful anyway
* Working with pull requests is **not part of git** and *requires host support*
  * GitHub, GitLab, and Bitbucket all support pull requests

---

## Single branch, multiple forks

![Trunk-based development (like)](https://raw.githubusercontent.com/DanySK/shared-slides/e375d394b0eb319d6c5b9b6a7a2c707dc347b7ac/git/dvcs-fork.svg)

---

## Single branch, multiple forks

* Single branch, multiple independent repository copies
* *Unknown* team size, *low-complexity* projects, *sparse* teams, *low* trust
* Typical of **small open-source projects**

---

## Git flow over multiple forks

![Trunk-based development (like)](https://raw.githubusercontent.com/DanySK/shared-slides/e375d394b0eb319d6c5b9b6a7a2c707dc347b7ac/git/dvcs-flow-fork.svg)

---

## Git flow over multiple forks

* Multiple branches, multiple independent repository copies
* *Unknown* team size, *high-complexity* projects, *sparse* teams, *low* trust
* Typical of **complex open-source projects**
