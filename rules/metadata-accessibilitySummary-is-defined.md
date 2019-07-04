---
id: metadata-accessibilitySummary-is-defined
name: Metadata 'schema:accessibilitySummary' is defined
description: Checks that the Package Document has at least one 'schema:accessibilitySummary' metadata entry
requirement: epub:3.2
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

The Package Document [`metadata` element](https://www.w3.org/publishing/epub3/epub-packages.html#sec-metadata-elem) has at least one child [`meta` element](https://www.w3.org/publishing/epub3/epub-packages.html#sec-meta-elem) with a `property` attribute set to `schema:accessibilitySummary` and no `refines` attribute.

## Expectation 2

Every [`meta` element](https://www.w3.org/publishing/epub3/epub-packages.html#sec-meta-elem) with a `property` attribute set to `schema:accessibilitySummary` has a non-empty text value after whitespace normalization.

## Assumptions

_This rule does not depend on any assumptions._

## Accessibility Support

schema.org accessibility metadata’s usefulness depends on its implementation on retailers, distributors, and search systems.

## Test Cases

### Passed

#### Passed Example 1

This Package Document has a `schema:accessibilitySummary` metadata entry:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>Moby Dick</dc:title>
        <meta property="schema:accessibilitySummary">This publication conforms to the EPUB Accessibility specification at WCAG Level AA</meta>
        …
    </metadata>
    …
</package>
```

#### Passed Example 2

This Package Document has multiple `schema:accessibilitySummary` metadata entries, for different languages.

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>Moby Dick</dc:title>
        <meta property="schema:accessibilitySummary">This publication conforms to the EPUB Accessibility specification at WCAG Level AA</meta>
        <meta property="schema:accessibilitySummary" xml:lang="fr">Cette publication est conforme à la spécificatin EPUB Accessibility au niveau WCAG AA</meta>
        …
    </metadata>
    …
</package>
```

### Failed

#### Failed Example 1

This Package Document has no `schema:accessibilitySummary` metadata entry:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>Moby Dick</dc:title>
    </metadata>
    …
</package>
```

#### Failed Example 2

This Package Document has a `schema:accessibilitySummary` metadata entry with an empty value:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>Moby Dick</dc:title>
        <meta property="schema:accessibilitySummary">  </meta>
        …
    </metadata>
    …
</package>
```


#### Failed Example 3

This Package Document has multiple `schema:accessibilitySummary` metadata entries for the same language:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>Moby Dick</dc:title>
        <meta property="schema:accessibilitySummary">This publication conforms to the EPUB Accessibility specification at WCAG Level AA</meta>
        …
    </metadata>
    …
</package>
```

## Background

 * [EPUB Accessibility 1.0](http://www.idpf.org/epub/latest/accessibility)
 * [accessibilitySummary](https://schema.org/accessibilitySummary) definition on schema.org
 * [WebSchemas wiki lists possible values](http://www.w3.org/wiki/WebSchemas/Accessibility)
 * [Schema.org Accessibility Metadata](http://kb.daisy.org/publishing/docs/metadata/schema-org.html) on DAISY’s Accessible Publishing Knowledge Base

## Changelog

- July 3, 2019: initial rule version
