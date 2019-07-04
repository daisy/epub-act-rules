---
id: publication-has-titles
name: Publication has titles
description: Checks that an EPUB Publication has titles for the Package and Content Documents
requirement: epub:4.3.1 + wcag:2.4.2
mapping:
  - failed: not satisfied
  - passed: further testing is needed
  - inapplicable: not satisfied
type: composite
input_rules:
  - epub:package-doc-has-title
  - act-r:2779a5
---

## Applicability

The rule applies to every Package Document or Content Document in an EPUB Publication.

## Expectation

For each test target, the outcome of the following rules is passed or inapplicable:

- [Package Document has a title](https://github.com/daisy/epub-act-rules/rules/package-doc-has-title.md)
- [HTML Page has a title](https://act-rules.github.io/rules/2779a5)

## Assumptions

_This rule does not depend on any assumptions._

## Accessibility Support

_There are no major accessibility support issues known for this rule._

## Test Cases

_The test cases are those defined in the constituent atomic rules._

## Background

 * [EPUB Accessibility 1.0](http://www.idpf.org/epub/latest/accessibility)
 * [WCAG 2.1 Success Criterion 2.4.2 “Page Titled”](https://www.w3.org/TR/WCAG/#page-titled)
 * [Publication Title](http://kb.daisy.org/publishing/docs/epub/title.html) on DAISY’s Accessibility Publishing Knowledge Base
 * [Page Title](http://kb.daisy.org/publishing/docs/html/title.html) on DAISY’s Accessibility Publishing Knowledge Base

## Changelog

- July 3, 2019: initial rule version
