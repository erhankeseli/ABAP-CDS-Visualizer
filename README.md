# ABAP and CDS Visualizer

A simple, zero-dependency, single-page web tool to automatically generate [Mermaid-JS](https://mermaid-js.github.io/mermaid/#/) diagrams from ABAP CDS View and Class definitions.

This utility helps developers quickly visualize the hierarchy and dependencies for both CDS views and the structure of ABAP classes.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## ✨ Features

*   **Dual-Mode Visualization:** Switch between dedicated tabs for CDS Entities and ABAP Classes.
*   **Zero Setup:** It's a single, self-contained `html` file. No installation or server required.
*   **Instant Visualization:** See the diagram update in real-time as you edit the code.
*   **Intelligent Parsing:**
    *   For **CDS Views**, automatically detects relationships from `FROM` and `JOIN` clauses.
    *   For **ABAP Classes**, automatically detects inheritance (`INHERITING FROM`) and method definitions.
*   **Code Export:** Easily copy the generated Mermaid syntax for use in documentation or wikis.
*   **Clean & Modern UI:** A simple, tabbed interface that's easy to use.

## 🚀 How to Use

1.  **Download:** Get the `abap-cds-visualizer.html` file from this repository.
2.  **Open:** Open the file in any modern web browser.
3.  **Select Tab:** Choose the "CDS Entities" or "ABAP Classes" tab based on the code you want to visualize.
4.  **Paste:** Copy your definitions and paste them into the input text area.
5.  **Visualize:** The diagram will be generated automatically. You can also click the **"Visualize Relationships"** button to refresh.

## 📋 Examples

### CDS View Example

This example demonstrates how the tool maps dependencies from `JOIN` clauses.

#### Input CDS Code

```abap
define view entity ProductSales
  as select from snwd_so as SalesOrder
  join snwd_so_i as Item on SalesOrder.node_key = Item.parent_key
  join snwd_pd as Product on Item.product_guid = Product.node_key
{
  key SalesOrder.so_id as SalesOrder,
  Product.product_id as Product,
  Product.short_descr as ProductName
}
```

### ABAP Class Example

This example shows a simple inheritance structure and method definitions.

#### Input ABAP Code

```abap
class lcl_child definition inheriting from lcl_parent.
  methods: child_method.
endclass.

class lcl_parent definition.
  methods: parent_method.
endclass.
```
