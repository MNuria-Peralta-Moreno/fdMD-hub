# fdMD-hub
A framework built on the original fragment dissolved Molecular Dynamics (fdMD) approach, integrating methodological advances and complementary workflows to explore and evaluate ligand binding in fragment-based drug discovery and beyond.


## Overview

fdMD-hub brings together the original fdMD methodology and its subsequent
extensions within a common repository.

The fdMD approach explores ligand–protein interactions through molecular
dynamics simulations in a competitive, multi-copy environment. Multiple
copies of a ligand are distributed around the target protein, allowing
potential binding sites and binding modes to be investigated.

Building on this foundation, fdMD-hub provides a shared home for
methodological developments and supporting workflows that extend the
scope of the original approach.

## Methods and repository structure

Each method is maintained in a dedicated directory containing its
implementation, documentation, and relevant usage instructions.

### `fdMD/` — Original fdMD approach

The original fragment dissolved Molecular Dynamics methodology,
providing the foundation for the developments collected in this repository.

This directory should retain the attribution, licensing information,
and references associated with the original implementation.

### `fdGaMD/` — Gaussian accelerated fdMD

An extension of fdMD incorporating Gaussian accelerated molecular
dynamics (GaMD) to enhance conformational sampling during the exploration
of ligand–protein interactions.

### Additional developments

Further methodological extensions and complementary workflows will be
documented in their respective directories as they become available.

## Getting started

Start with the README in the directory corresponding to the method
you intend to use. Method-specific documentation will describe:

- Software requirements and dependencies.
- Input preparation and configuration.
- Workflow execution.
- Output processing and analysis.
- Examples and practical considerations.

Requirements and execution procedures may differ between methods.

## Availability

This repository is being assembled and documented progressively.
The presence and implementation status of each method will be indicated
in its corresponding directory.

## Attribution and provenance

fdMD-hub builds on the original fdMD methodology and acknowledges the
authors and contributors of each implementation.

For code originating from another repository, the corresponding
documentation will identify its original source, authors, license,
and any modifications introduced here.

## Citation

Please cite the original fdMD publication and the publications associated
with the specific methods used in your work.

Method-specific references and citation instructions will be provided
in the corresponding directories.

## License

This project is licensed under the BSD 3-Clause License.
See the LICENSE file for details.

The original fdMD implementation is copyright (c) 2019,
Jaime Rubio Martínez. Original copyright and license notices
are retained in the corresponding files.
