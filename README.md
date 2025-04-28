# Solver Configuration Collection

This repository provides a curated collection of solver configuration files for use with:

- [Metrics](https://github.com/crilllab/metrics) ([Documentation](https://metrics.readthedocs.io)):  
  An open-source Python library to automate experiments and analyze solver performance.
- [XCSP-Launcher](https://github.com/thibaultfalque/xcsp-launcher):  
  A tool for installing, managing, and executing solvers supporting the XCSP3 format.

These configuration files describe how to install, build, and run various constraint programming solvers.

---

## 📚 Available Solver Configurations

- [ACE](./ace.solver.yaml) — Configuration for the [ACE](https://github.com/xcsp3team/ace) constraint programming solver.

*(Additional solvers will be added progressively.)*

---

## 🛠️ Solver Configuration Format

The detailed documentation describing the solver configuration file format is available [here](./format.md).

This includes information on:

- Build modes (manual or automatic)
- Solver version management
- Command-line options and templates
- Output parsing patterns