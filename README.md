# Matrix Rank Calculator

A browser-based matrix rank calculator and Programming for Problem Solving (C) mini project for IITM BAHADURGARH CSE Semester 1.

## Contents

- [Overview](#overview)
- [Features](#features)
- [How It Works](#how-it-works)
- [Getting Started](#getting-started)
- [Using the Interface](#using-the-interface)
- [Project Structure](#project-structure)
- [Documentation](#documentation)
- [Known Limitations](#known-limitations)
- [Development Workflow](#development-workflow)
- [Roadmap](#roadmap)
- [License and Contact](#license-and-contact)

## Overview

This project demonstrates how Gaussian elimination can be used to calculate the rank of a matrix. The interactive HTML page lets users build a matrix, load sample input, calculate its rank, and inspect the elimination steps alongside equivalent C source code.

## Features

- Create matrices with up to 6 rows and 6 columns.
- Calculate matrix rank using Gaussian elimination.
- Display elimination steps and an equivalent C implementation.
- Review viva questions about arrays, loops, matrices, and Gaussian elimination.
- Use the page offline after opening it locally.

## How It Works

1. Read the matrix dimensions and values from the input grid.
2. Select a pivot column and eliminate matching values in other rows.
3. Swap rows when a pivot is zero but a lower row contains a usable value.
4. Reduce the working rank when an entire pivot column is zero.
5. Display the final rank and log the row operations performed.

The JavaScript implementation mirrors the C logic shown in the expandable source-code panel. It uses arrays, nested loops, conditionals, row swapping, and arithmetic operations rather than an external mathematics library.

## Getting Started

No build tools or external dependencies are required.

### Open locally

Open [matrix_rank_calculator.html](matrix_rank_calculator.html) directly in a modern browser.

### Serve locally

From the repository root, use either command:

```bash
# Python 3
python3 -m http.server 8000

# Node.js, if available
npx serve .
```

Then open `http://localhost:8000/matrix_rank_calculator.html` for the Python server, or the URL printed by `serve`.

For GitHub Pages, publish the repository root from the `main` branch. Since the file is named `matrix_rank_calculator.html`, use that path in the published URL.

## Using the Interface

1. Set the number of rows and columns.
2. Select **Build Grid**.
3. Enter a number in every cell.
4. Select **Calculate Rank**.
5. Review the result and select **Show** beside the elimination steps.
6. Use **Load Sample Input** to restore the built-in example.

The sample matrix is:

```text
1  2  3
2  4  6
1  1  1
```

The second row is twice the first row, so this matrix has rank 2.

## Project Structure

```text
.
├── matrix_rank_calculator.html                 # Interactive matrix rank calculator
├── src/                                        # Reserved for future source files
├── assets/                                     # Images and other media
├── docs/
│   ├── Matrix_Rank_Calculator_Research_Paper.pdf
│   └── Matrix_Rank_Calculator_Presentation.pptx
├── LICENSE
└── README.md
```

## Documentation

- [Research Paper](docs/Matrix_Rank_Calculator_Research_Paper.pdf) — research and background for the project.
- [Presentation](docs/Matrix_Rank_Calculator_Presentation.pptx) — project presentation materials.

## Known Limitations

- The interface limits each dimension to 6.
- The implementation is a teaching demonstration, not a numerically robust linear algebra library.
- The elimination code mirrors the original C example and should be tested further for every rectangular-matrix shape, especially matrices with more columns than rows.
- There is no automated browser test suite or standalone `.c` source file yet; the C example is embedded in the HTML page.
- Matrix cells must contain valid numeric values before calculation can run.

## Development Workflow

The repository uses lightweight branches for separate work areas:

| Branch | Purpose |
| --- | --- |
| `main` | Stable project branch and GitHub Pages source |
| `develop` | Integration branch for completed changes |
| `docs/updates` | Documentation and presentation updates |
| `feature/calculator-improvements` | Calculator behavior and interface improvements |
| `docs/research-materials` | Research paper and presentation work |
| `testing/validation` | Manual and automated validation experiments |
| `release/v1.0` | Versioned release preparation |

For a normal change:

```bash
git checkout develop
git checkout -b feature/short-description
# Make and test the change
git add -A
git commit -m "Describe the change"
git push -u origin feature/short-description
```

Keep `main` deployable. Merge feature work into `develop` first, then promote tested changes to `main`.

## Roadmap

- [ ] Add a downloadable C source file.
- [ ] Improve handling and validation of rectangular matrices.
- [ ] Add automated tests for zero, identity, dependent, and rectangular matrices.
- [ ] Add a reset button and clearer validation messages.
- [ ] Add an `index.html` entry point for simpler GitHub Pages URLs.

## License and Contact

This project is released under the MIT License. See [LICENSE](LICENSE) for the full text.

Mayank Swaraj — [mayankswaraj18cr@gmail.com](mailto:mayankswaraj18cr@gmail.com)
