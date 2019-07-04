---
id: publication-has-required-accessibility-metadata
name: Publication has required accessibility metadata
description: Checks that an EPUB Publication has metadata entries for all the required accessibility metadata.
requirement: epub:3.2
mapping:
  - failed: not satisfied
  - passed: further testing is needed
  - inapplicable: not satisfied
type: composite
input_rules:
  - epub:metadata-accessibilityFeature-is-defined
  - epub:metadata-accessibilityHazard-is-defined
  - epub:metadata-accessibilitySummary-is-defined
  - epub:metadata-accessMode-is-defined
---

## Applicability

The rule applies to every Package Document in an EPUB Publication.

## Expectation

For each test target, the outcome of all the following rules is passed:

- [Metadata 'schema:accessibilityFeature' is defined](https://github.com/daisy/epub-act-rules/rules/metadata-accessibilityFeature-is-defined.md)
- [Metadata 'schema:accessibilityHazard' is defined](https://github.com/daisy/epub-act-rules/rules/metadata-accessibilityHazard-is-defined.md)
- [Metadata 'schema:accessibilitySummary' is defined](https://github.com/daisy/epub-act-rules/rules/metadata-accessibilitySummary-is-defined.md)
- [Metadata 'schema:accessMode' is defined](https://github.com/daisy/epub-act-rules/rules/metadata-accessMode-is-defined.md)

## Assumptions

_This rule does not depend on any assumptions._

## Accessibility Support

schema.org accessibility metadata’s usefulness depends on its implementation on retailers, distributors, and search systems.

## Test Cases

_The test cases are those defined in the constituent atomic rules._

## Background

 * [EPUB Accessibility 1.0](http://www.idpf.org/epub/latest/accessibility)
 * [WCAG 2.1 Success Criterion 2.4.2 “Page Titled”](https://www.w3.org/TR/WCAG/#page-titled)
 * [Publication Title](http://kb.daisy.org/publishing/docs/epub/title.html) on DAISY’s Accessibility Publishing Knowledge Base
 * [Page Title](http://kb.daisy.org/publishing/docs/html/title.html) on DAISY’s Accessibility Publishing Knowledge Base

## Changelog

- July 3, 2019: initial rule version
