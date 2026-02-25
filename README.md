# LAMMPS Modifications

A curated collection of useful modifications to [LAMMPS](https://www.lammps.org/) (Large-scale Atomic/Massively Parallel Simulator) source code. Each modification includes the patched or replaced source file(s) alongside documentation explaining what was changed and why.

## Repository Structure

```
lammps_modifications/
├── modifications/
│   ├── <modification-name>/
│   │   ├── README.md          # Description, purpose, and usage instructions
│   │   ├── <source-file>.cpp  # Modified LAMMPS source file(s)
│   │   └── <source-file>.h    # (if applicable)
│   └── ...
├── CONTRIBUTING.md            # Guidelines for adding new modifications
└── README.md                  # This file
```

## How to Use a Modification

1. Browse the [`modifications/`](modifications/) directory and find the modification relevant to your use case.
2. Read the `README.md` inside that modification's folder to understand:
   - What the modification does
   - Which LAMMPS version(s) it targets
   - Any caveats or dependencies
3. Copy the modified source file(s) into the corresponding location in your LAMMPS source tree, replacing the originals.
4. Recompile LAMMPS as usual.

## Modifications

| Name | Description |
|------|-------------|
| *(more to come)* | |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to add a new modification to this repository.

## License

See [LICENSE](LICENSE).
