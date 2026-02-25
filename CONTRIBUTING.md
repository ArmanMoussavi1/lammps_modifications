# Contributing a New Modification

Follow these steps to add a new LAMMPS modification to this repository.

## 1. Create a folder under `modifications/`

Choose a short, descriptive name (use hyphens, no spaces):

```
modifications/
└── your-modification-name/
```

## 2. Add the modified source file(s)

Copy the relevant LAMMPS source file(s) into the folder and apply your changes. Keep file names identical to the originals so they can be dropped straight into a LAMMPS source tree.

Example:
```
modifications/your-modification-name/
├── fix_nvt.cpp
└── fix_nvt.h
```

## 3. Write a `README.md` for the modification

Each modification folder **must** contain a `README.md` with the following sections:

```markdown
# <Modification Name>

## Purpose
What problem does this modification solve, or what new feature does it add?

## LAMMPS Version
Which LAMMPS version(s) this modification was developed and tested against (e.g. `29 Aug 2024`).

## Files Modified
List every file that was changed and where it lives in the LAMMPS source tree:

| File | LAMMPS path |
|------|-------------|
| fix_nvt.cpp | `src/fix_nvt.cpp` |

## Changes Made
A clear description of exactly what was changed and why.
Use code blocks or diffs where helpful.

## Usage
Any special compile flags, input script keywords, or other instructions needed to use this modification.

## Caveats / Known Limitations
Anything the user should be aware of.
```

## 4. Update the main `README.md` table

Add a row to the **Modifications** table in the root `README.md`:

```markdown
| [your-modification-name](modifications/your-modification-name/) | One-line description |
```

## Style Guidelines

- Keep modifications focused — one logical change per folder.
- Prefer minimal diffs; avoid reformatting unrelated code.
- Document the *why*, not just the *what*.
