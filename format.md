# Solver Configuration File Specification

This document describes the structure of the `.xsc.yaml` configuration files used to register solvers with XCSP Launcher.

---

## General Information

| Field | Type | Description |
|------|------|-------------|
| `name` | string | Human-readable name of the solver. |
| `id` | string | Unique identifier, typically like a Java package name. |
| `description` | string | Short description of the solver. |
| `git` | string | Git repository URL where the solver's source code can be found. |

---

## Build Instructions

| Field | Type | Description |
|------|------|-------------|
| `build.mode` | string | Build mode: `manual` or `auto` |
| `build.build_command` | string | If `manual`, the exact command to compile the solver. |

---

## Command Line Execution

| Field | Type | Description |
|------|------|-------------|
| `command.prefix` | string | Command prefix (e.g., `{{java}} -jar`, `{{python}}`). Note that `{{java}}` or `{{python}}` are plaholders for using the correct path to this binaries. |
| `command.template` | string | Template for running a solver instance (with placeholders like `{{executable}}`, `{{instance}}`, `{{options}}`). |
| `command.always_include_options` | string | Options that are always appended to solver calls. |
| `command.options` | dict | Mapping between standard options and solver-specific CLI parameters. |

Standard options that can be customized:
- `time`
- `seed`
- `all_solutions`
- `number_of_solutions`
- `verbosity`
- `print_intermediate_assignment`

---

## Versions Management

| Field | Type | Description |
|------|------|-------------|
| `versions` | list of dict | List of supported versions. Each entry contains: |
| `version.version` | string | Version label. |
| `version.alias` | list of string | Optional list of aliases (e.g., "latest", "dev"). |
| `version.executable` | string | Path to the executable after building. |
| `version.git_tag` | string | Git tag or commit to checkout. |

---

## Output Parsing

This is a special section that corresponds to the [`data` part](https://metrics.readthedocs.io/en/latest/scalpel-config.html#description-of-the-data-to-extract) of the `metrics-scalpel` configuration file. 


---

# 📣 Notes

- Placeholders in the command template are enclosed in double curly braces: `{{executable}}`, `{{instance}}`, `{{options}}`, `{{java}}`, `{{python}}`.
- `versions` allows supporting multiple tagged releases of a solver without re-downloading the full source each time.

---

