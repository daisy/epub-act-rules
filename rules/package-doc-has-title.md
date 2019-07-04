---
id: package-doc-has-title
name: Package Document has a title
description: Checks that the EPUB Package Document has title metadata
requirement: epub:4.3.1 + wcag:2.4.2
mapping:
  - failed: not satisfied
  - passed: further testing is needed
  - inapplicable: further testing is needed
type: atomic
input_aspects:
  - XML Document
---

## Applicability

The rule applies to any EPUB Package Document.

## Expectation 1

The Package Document [`metadata` element](https://www.w3.org/publishing/epub3/epub-packages.html#sec-metadata-elem) has at least one child [`title` element](https://www.w3.org/publishing/epub3/epub-packages.html#sec-opf-dctitle) in the Dublin Core Metadata Element Set namespace.

## Expectation 2

The first `dc:title` element that is a child of the `metadata` element has a name attribute that is not empty.

## Assumptions

_This rule does not depend on any assumptions._

## Accessibility Support

_There are no major accessibility support issues known for this rule._

## Test Cases

### Passed

#### Passed Example 1

This Package Document has a `dc:title` metadata entry:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>Moby Dick</dc:title>
        …
    </metadata>
    …
</package>
```

#### Passed Example 2

This Package Document has multiple `dc:title` metadata entries:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>The Lord Of The Rings</dc:title>
        <dc:title>Part One: The Fellowship of the Ring</dc:title>
        …
    </metadata>
    …
</package>
```

### Failed

#### Failed Example 1

This Package Document has no `dc:title` metadata entry:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
    </metadata>
    …
</package>
```

#### Failed Example 2

This Package Document has a `dc:title` metadata entry with no value:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>   </dc:title>
    </metadata>
    …
</package>
```

## Background

 * [EPUB Accessibility 1.0](http://www.idpf.org/epub/latest/accessibility)
 * [WCAG 2.1 Success Criterion 2.4.2 “Page Titled”](https://www.w3.org/TR/WCAG/#page-titled)
 * [Publication Title](http://kb.daisy.org/publishing/docs/epub/title.html) on DAISY’s Accessibility Publishing Knowledge Base

## Changelog

- July 3, 2019: initial rule version
