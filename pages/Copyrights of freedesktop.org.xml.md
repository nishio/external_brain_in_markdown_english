---
title: "Copyrights of freedesktop.org.xml"
---

The question of whether the "database" freedesktop.org.xml, which is a "database" about mime-types, is copyrightable.

For example, if the database were as follows, this would not be eligible for protection as "[[Database works]]" because it is merely an exhaustive list of facts and there is no creativity in its body type composition.
:
| *.json | application/json |
| -- | -- |
| *.orf | image/x-olympus-orf |
| *.svg | image/svg+xml |
| *.pl | application/x-perl |

So what does freedesktop.org.xml actually say? I have concluded that it is highly creative even if it is interpreted as a database, and in fact, Nishio thinks that it is at the level of [[Program works]].

Past revision as it is missing from master: [mimemagic : freedesktop.org.xml [https://github.com/mimemagicrb/mimemagic/blob/c0f7b6b21a192629839db87612794](https://github.com/mimemagicrb/mimemagic/blob/c0f7b6b21a192629839db87612794) d08f9ff7e88/script/freedesktop.org.xml]

For example, it not only maps filename patterns to mime-type, but also comments for human readers, abbreviations and how to write them without abbreviations, the relationship that json is a subclass of javascrit, which icon to use when displaying icons to humans, and so on.
At this point, the composition may already have some creativity beyond "mere listing of mime-type data," at least as much as the Town Page, which is recognized as copyrightable... but let's put that on hold for the moment and read on.
xml

```xml
  <mime-type type="application/json">
    <comment>JSON document</comment>
    <acronym>JSON</acronym>
    <expanded-acronym>JavaScript Object Notation</expanded-acronym>
    <sub-class-of type="application/javascript"/>
    <generic-icon name="text-x-script"/>
    <glob pattern="*.json"/>
  </mime-type>
```


In addition, some things are in the form of commentary that is not subject to computer processing, such as "ORF is a non-standards compliant TIFF" for those who read this file.
This means that this file is not a mechanical output, but is supposed to be read and rewritten by humans.
xml

```xml
  <mime-type type="image/x-olympus-orf">
    <comment>Olympus ORF raw image</comment>
    <acronym>ORF</acronym>
    <expanded-acronym>Olympus Raw Format</expanded-acronym>
    <sub-class-of type="image/x-dcraw"/>
    <magic priority="50">
      <!-- an ORF file is basically a TIFF file with a non standard !-->
      <!-- header IIRO which is not nice since it is only composed  !-->
      <!-- of ASCII codes. Fortunately, the TIFF header is followed !-->
      <!-- by the offset of the first TIFF ifd which is always      !-->
      <!-- 0x00000008 (Little endian) for an ORF                    !-->
      <match value="IIRO\x08\x00\x00\x00" type="string" offset="0"/>
    </magic>
    <glob pattern="*.orf"/>
  </mime-type>
```


In SVG, the free tool Inkscape checks for the presence of comment text, etc. in the output and uses it to make judgments. In order to use uncertain hints, a priority value is used to express the degree of confidence in the judgment.
In essence, this is a description of a method of conditional judgment, and these judgment rules were not created mechanically from some specification document, but were created by a human being who looked at the actual file and thought, "How can I make a judgment?
xml

```xml
  <mime-type type="image/svg+xml">
    <comment>SVG image</comment>
    <acronym>SVG</acronym>
    <expanded-acronym>Scalable Vector Graphics</expanded-acronym>
    <sub-class-of type="application/xml"/>
    <magic priority="80">
      <match type="string" value="&lt;!DOCTYPE svg" offset="0:256"/>
    </magic>
    <magic priority="80">
      <match type="string" value="&lt;!-- Created with Inkscape" offset="0"/>
      <match type="string" value="&lt;svg" offset="0"/>
    </magic>
    <magic priority="45">
      <match type="string" value="&lt;svg" offset="1:256"/>
    </magic>
    <glob pattern="*.svg"/>
    <root-XML namespaceURI="http://www.w3.org/2000/svg" localName="svg"/>
  </mime-type>
```


When it comes to Perl, the authors list the various extensions with comments on what kind of extensions they are, and then try to determine them by hinting at patterns that are likely to appear in the Perl code.
xml

```xml
  <mime-type type="application/x-perl">
    <comment>Perl script</comment>
    <sub-class-of type="application/x-executable"/>
    <sub-class-of type="text/plain"/>
    <generic-icon name="text-x-script"/>
    <alias type="text/x-perl"/>
    <magic priority="50">
      <match type="string" value='eval \"exec /usr/local/bin/perl' offset="0"/>
      <match type="string" value="/bin/perl" offset="2:16"/>
      <match type="string" value="/bin/env perl" offset="2:16"/>
      <match type="string" value="use Test::" offset="0:256"/>
      <match type="string" value="BEGIN {" offset="0:256"/>
    </magic>
    <magic priority="40">
      <match type="string" value="use strict" offset="0:256"/>
      <match type="string" value="use warnings" offset="0:256"/>
      <match type="string" value="use diagnostics" offset="0:256"/>
      <match type="string" value="\n=pod" offset="0:256"/>
      <match type="string" value="\n=head1 NAME" offset="0:256"/>
      <match type="string" value="\n=head1 DESCRIPTION" offset="0:256"/>
    </magic>
    <glob pattern="*.pl"/>
    <glob pattern="*.PL"/><!-- CPAN-style Perl build script -->
    <glob pattern="*.pm"/><!-- module -->
    <glob pattern="*.al"/><!-- autoloader -->
    <glob pattern="*.perl"/>
    <glob pattern="*.pod"/><!-- documentation -->
    <glob pattern="*.t" weight="10"/><!-- CPAN-style Perl test script -->
  </mime-type>
```


Thus, this XML file is a combination of directives that allow the computer to determine the mime-type from the extension and the contents of the file.
The definition of a program under the Copyright Act is "an expression as a combination of commands to a computer so that it can function and obtain a single result," which satisfies the requirement. The fact that the method of expression is XML is irrelevant to the determination of whether or not it is a program.

----
Summary of the Twitter discussion compared to the Town Pages case:.
- The Town Pages are a collection of "data with no room for creativity, a combination of names and phone numbers," and simply collecting them by sweat equity does not constitute a work of authorship, but the classification by occupation has creativity, and thus became a database work of authorship.
- Nishio thinks that in this case, the "directive on which offset value at the beginning of the file is checked to determine the mime-type" is a creative information with a very unique device in the first place, so it may be a work of the program before a work of the database.

---
This page is auto-translated from [/nishio/freedesktop.org.xmlの著作物性](https://scrapbox.io/nishio/freedesktop.org.xmlの著作物性) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.