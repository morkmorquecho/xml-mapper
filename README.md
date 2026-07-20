# PathForge

## Visual XML Path Mapping Tool

PathForge is a visual tool designed to simplify the creation of XML data extraction mappings.

It allows users to upload XML documents, navigate through their structure, select nodes or attributes, and automatically generate their corresponding XPath expressions. These mappings can then be exported as JSON configurations to be consumed by extraction algorithms, ETL processes, or data transformation pipelines.

---

## 💡 Use Case

Many systems still exchange information using XML formats such as:

* Electronic invoices
* Government documents
* Legacy enterprise systems
* Data integration pipelines
* External APIs

Finding the correct XPath manually can be time-consuming and error-prone.

PathForge provides a visual approach where users can simply select the required information from an XML document and generate a structured extraction map.

---

## Example

Given this XML:

```xml
<Invoice>
    <Customer>
        <Name>John Smith</Name>
    </Customer>

    <Total currency="USD">
        150.00
    </Total>
</Invoice>
```

A user can create the following mapping:

```json
{
  "customer_name": {
    "path": "/Invoice/Customer/Name"
  },
  "total_amount": {
    "path": "/Invoice/Total"
  },
  "currency": {
    "path": "/Invoice/Total/@currency"
  }
}
```

This configuration can later be used by an extraction engine to automatically retrieve the required values.

---

## Architecture

PathForge consists of three main components:

### XML Parser

Responsible for loading and analyzing XML documents.

### Path Generator

Generates XPath expressions based on the selected XML elements.

### Mapping Builder

Creates reusable extraction configurations with custom field names.

---

## Workflow

```
XML Document
      |
      v
XML Tree Explorer
      |
      v
Select Node / Attribute
      |
      v
Generate XPath
      |
      v
Assign Field Name
      |
      v
Export JSON Mapping
```
