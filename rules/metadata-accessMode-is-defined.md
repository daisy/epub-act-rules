---
id: metadata-accessMode-is-defined
name: Metadata 'schema:accessMode' is defined
description: Checks that the Package Document has at least one 'schema:accessMode' metadata entry
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

The Package Document [`metadata` element](https://www.w3.org/publishing/epub3/epub-packages.html#sec-metadata-elem) has at least one child [`meta` element](https://www.w3.org/publishing/epub3/epub-packages.html#sec-meta-elem) with a `property` attribute set to `schema:accessMode` and no `refines` attribute.

## Expectation 2

Every [`meta` element](https://www.w3.org/publishing/epub3/epub-packages.html#sec-meta-elem) with a `property` attribute set to `schema:accessMode` has a text value matching one of the [expected values](https://www.w3.org/wiki/WebSchemas/Accessibility) after removing leading and trailing whitespace.

## Assumptions

_This rule does not depend on any assumptions._

## Accessibility Support

schema.org accessibility metadata’s usefulness depends on its implementation on retailers, distributors, and search systems.

## Test Cases

### Passed

#### Passed Example 1

This Package Document has a `schema:accessMode` metadata entry:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>Moby Dick</dc:title>
        <meta property="schema:accessMode">textual</meta>
        …
    </metadata>
    …
</package>
```

#### Passed Example 2

This Package Document has multiple `schema:accessMode` metadata entries:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>Moby Dick</dc:title>
        <meta property="schema:accessMode">textual</meta>
        <meta property="schema:accessMode">visual</meta>
        …
    </metadata>
    …
</package>
```

### Failed

#### Failed Example 1

This Package Document has no `schema:accessMode` metadata entry:

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

This Package Document has a `schema:accessMode` metadata entry with an unknown value:

```xml
<package version="3.0" xml:lang="en" unique-identifier="uid" xmlns="http://www.idpf.org/2007/opf" xmlns:dc="http://purl.org/dc/elements/1.1/">
    <metadata>
        <dc:language>en</dc:language>
        <dc:identifier id="uid">NOID</dc:identifier>
        <dc:title>Moby Dick</dc:title>
        <meta property="schema:accessMode">text</meta>
        …
    </metadata>
    …
</package>
```

## Background

 * [EPUB Accessibility 1.0](http://www.idpf.org/epub/latest/accessibility)
 * [accessMode](https://schema.org/accessMode) definition on schema.org
 * [WebSchemas wiki lists possible values](http://www.w3.org/wiki/WebSchemas/Accessibility)
 * [Schema.org Accessibility Metadata](http://kb.daisy.org/publishing/docs/metadata/schema-org.html) on DAISY’s Accessible Publishing Knowledge Base

## Changelog

- July 3, 2019: initial rule version
