## Part E: Git History, Merge Conflict & Reflection

### 1. Commit History (`git log --oneline --graph --all`)
Paste your terminal/app commit log output here (showing at least three commits on `program.c` and the branch merge).

### 2. Merge Conflict & Resolution
* **Git Conflict Message:**
  `Auto-merging program.c`
  `CONFLICT (content): Merge conflict in program.c`
  `Automatic merge failed; fix conflicts and then commit the result.`
* **How It Was Resolved:** Opened `program.c`, removed the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), kept the intended code line, staged the file with `git add program.c`, and committed the resolution with `git commit`.

### 3. Reflection Questions
1. **Concurrency (SCCS vs. Git):** SCCS uses pessimistic locking, allowing only one developer to edit a file at a time. Git uses optimistic concurrency, letting developers edit local copies simultaneously and resolve overlaps later through branching and merging. SCCS slows teams down more because developers sit idle waiting for locks to be released on shared files.
2. **Storage (Interleaved Deltas vs. Snapshots):** SCCS stores interleaved deltas in a single history file, saving disk space and reconstructing versions in one pass, though making branching and multi-file operations difficult. Git stores full snapshots per commit, making branch switching and diffs fast at the cost of higher initial storage.
3. **Why Multi-File Commits Matter:** A single feature or bug fix in a real project usually spans multiple files such as source code, configuration, and tests. Multi-file atomic commits group related edits into one logical unit so the project is not left in a broken, half-updated state.
4. **Version Control vs. PM Tools:** Text-based artifacts like the WBS document, task tables, and EVM data belong in version control so baseline changes are tracked. Dynamic workflow items like Kanban cards, live task assignments, due dates, and Gantt schedules belong in a project management tool such as Jira, Trello, or Azure DevOps.
5. **Enduring SCCS Idea:** Modern version control still relies on SCCS's foundational concept of annotated change metadata—recording unique revision identifiers alongside who made each change, when it occurred, and a log comment explaining why.
