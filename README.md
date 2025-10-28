# CDS View to Mermaid Visualizer

A simple, zero-dependency, single-page web tool to automatically generate [Mermaid-JS](https://mermaid-js.github.io/mermaid/#/) flowchart diagrams from ABAP CDS View entity definitions.

This utility helps developers quickly visualize the hierarchy and dependencies between different CDS views, making complex data models easier to understand.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)



## ✨ Features

*   **Zero Setup:** It's a single, self-contained `html` file. No installation or server required.
*   **Instant Visualization:** See the relationship diagram update in real-time as you edit the code.
*   **Intelligent Parsing:** Automatically detects relationships from `FROM` and `JOIN` clauses.
*   **Code Export:** Easily copy the generated Mermaid syntax for use in documentation, wikis, or other Markdown files (like this one!).
*   **Clean & Modern UI:** A simple, intuitive interface that's easy to use.

## 🚀 How to Use

1.  **Download:** Get the `cds-visualizer.html` file from this repository.
2.  **Open:** Open the file in any modern web browser (Chrome, Firefox, Edge, Safari).
3.  **Paste:** Copy your CDS view definitions and paste them into the "Input CDS Definitions" text area.
4.  **Visualize:** Click the **"Visualize Relationships"** button.

The tool will immediately generate the Mermaid syntax in the second text box and render the visual flowchart at the bottom of the page.

## 📋 Example

This example demonstrates how the tool maps parent-child relationships between three CDS views.

#### Input CDS Code

Paste this into the tool:

```abap
define view entity C_First
  as select from I_CustomerLineItems

define view entity I_CustomerLineItems
  as select from I_CustomerLineItem      as _CustomerLineItem
  left outer to one join  I_BusinessPartnerAmount 

