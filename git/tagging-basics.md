## Branches as attachable (and movable) labels

```mermaid
flowchart RL
  HEAD{{"HEAD"}}

  master(master)
  tag1(1.2.3)

  C10([10]) --> C9([9]) --> C8([8]) --> C7([7]) --> C6([6]) --> C5([5]) --> C4([4]) --> C3([3]) --> C2([2]) --> C1([1])

  master -.-> C10

  HEAD -.-> C10
  HEAD --"fas:fa-link"--o master
  tag1 --o C4

  class HEAD head;
  class master,tag1 branch;
  class C1,C2,C3,C4,C5,C6,C7,C8,C9,C10,C11,C12,C13 commit;
```

Looks good, but if we do something like: ⬇️ `git checkout 1.2.3` [some changes] `git commit` ⬇️

```mermaid
flowchart RL
  HEAD{{"HEAD"}}

  master(master)

  tag1(1.2.3)

  C10([10]) --> C9([9]) --> C8([8]) --> C7([7]) --> C6([6]) --> C5([5]) --> C4([4]) --> C3([3]) --> C2([2]) --> C1([1])
  C11([11]) --> C4
  master -.-> C10

  HEAD -.-> C10
  HEAD --"fas:fa-link"--o master
  tag1 --o C11

  class HEAD head;
  class master,tag1 branch;
  class C1,C2,C3,C4,C5,C6,C7,C8,C9,C10,C11,C12,C13 commit;
```

Our version **moved**, *we never want this to happen*!

---

## Tagging

The `tag` subcommand to create *permanent labels* attached to commits.
Tags come in two fashions:
* **Lightweight** *tags* are very similar to a "permanent branch": *pointers to commits that never change*
* **Annotated** *tags*  (option `-a`) store additional information: a *message*, and, optionally, a *signature* (option `-s`/`-u`)

```mermaid
flowchart RL
  HEAD{{"HEAD"}}
  master(master)

  C10([10]) --> C9([9]) --> C8([8]) --> C7([7]) --> C6([6]) --> C5([5]) --> C4([4]) --> C3([3]) --> C2([2]) --> C1([1])

  master -.-> C10

  HEAD -.-> C10
  HEAD --"fas:fa-link"--o master

  class HEAD head;
  class master branch;
  class C1,C2,C3,C4,C5,C6,C7,C8,C9,C10,C11,C12,C13 commit;
```

⬇️ `git checkout C4 && git tag 1.2.3` ⬇️

```mermaid
flowchart RL
  HEAD{{"HEAD fas:fa-unlink"}}

  master(master)
  tag1>1.2.3]

  C10([10]) --> C9([9]) --> C8([8]) --> C7([7]) --> C6([6]) --> C5([5]) --> C4([4]) --> C3([3]) --> C2([2]) --> C1([1])

  master -.-> C10

  HEAD -.-> C4
  tag1 --o C4

  class HEAD head;
  class master branch;
  class tag1 tag;
  class C1,C2,C3,C4,C5,C6,C7,C8,C9,C10,C11,C12,C13 commit;
```

`HEAD` cannot attach to tags!
