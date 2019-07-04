---
id: pagebreak-has-label
name: Page break markers have an accessible name
description: Checks that page break markers in an EPUB Publication content documents have accessible labels.
requirement: best practice
mapping:
  - failed: not satisfied
  - passed: satisfied
  - inapplicable: not satisfied
type: atomic
input_aspects:
  - DOM Tree
---

## Applicability

The rule applies to any HTML element with the semantic role of `doc-pagebreak` that is included in the accessibility tree.

## Expectation

Each target element has an accessible name that is not only whitespace.

## Assumptions

_This rule does not depend on any assumptions._

## Accessibility Support

TBD.

## Test Cases

TBD.

## Background

 * [EPUB Accessibility 1.0](http://www.idpf.org/epub/latest/accessibility)
 * TBD

## Changelog

- July 3, 2019: initial rule version (work in progress)
