## Understanding the Difference Between `*` and `/*` in `.gitignore`

When configuring your `.gitignore` file, the difference between `*` and `/*` is subtle but important. Both are used to **ignore files and folders**, but they behave differently depending on their placement and syntax.

### `*` — Ignore Everything Recursively

```gitignore
*
```

- Ignores **all files and folders**, at **all levels** of the directory tree.
- This includes files in subfolders, nested directories, and so on.

#### Example Matches:

- `README.md`
- `src/`
- `src/main.js`
- `dist/`
- `dist/playground/user.js`

This is a **recursive catch-all**.

---

### `/*` — Ignore Only Root-Level Files and Folders

```gitignore
/*
```

- Ignores **only** the files and folders located at the **root** of your repository.
- Does **not** ignore contents inside subdirectories (unless the subdirectory itself is excluded).

#### Example Matches:

- `README.md`
- `src/` _(the folder itself)_

#### Example Non-Matches:

- `src/main.js` _(inside the folder — still visible)_
- `dist/playground.user.js`

---

### Summary Table

| Pattern | Ignores               | Recursive? | Use Case                                           |
| ------- | --------------------- | ---------- | -------------------------------------------------- |
| `*`     | All files and folders | Yes        | Ignore everything in the repo                      |
| `/*`    | Only root-level items | No         | Ignore just the top-level, keep subfolder contents |

---

### Pro Tip

To ignore root files but **keep subfolders tracked**, combine patterns:

```gitignore
/*
!*/
```

This tells Git to:

- Ignore everything at the root,
- But unignore folders (so you can still include files inside them explicitly).

---
