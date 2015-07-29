# Changes in version 4.0.0-ALPHA (released on 2012.07.17) #
This is a major upgrade of Luke to Lucene 4.0.0-ALPHA.

---

> NOTE !!! This upgrade changes and/or removes some of the Luke functionality, either because it's no longer available in Lucene or it would be too difficult to port. Specifically:
> - norms modification is not supported
> - deleting by docid (and ranges) is not supported, instead you can delete by query.
> - "replacing" document is not supported (not easy to pinpoint the document to delete).

---


Large parts of Luke had to be re-written or heavily modified. As a consequence I'm pretty sure there will be many new bugs and some missing features. Please report these, preferably with Apache-style patches to fix them - thank you!

Other changes in this version:

  * Add term offsets when available to "Show Positions" dialog.
  * Modify the list of field flags to better reflect the available field information. FieldType is not always reliable, and some type informaton is not preserved in the index (e.g. whether an indexed field was tokenized).
  * Add detailed segment information in the Files section. This includes Codec and FieldInfo-level details not available elsewhere.
  * Add support for explaining automaton queries' structure.
  * Bring back format details for old indexes (available when opening without IndexReader).
  * Add clipboard copy function in more places.

  * [Issue 36](https://code.google.com/p/luke/issues/detail?id=36): XMLExporter generating invalid XML, when special characters are present in a TermVector field (Craig.Stires)
  * [Issue 19](https://code.google.com/p/luke/issues/detail?id=19): Custom directory implementation must be inherited from FSDirectory (mitja.lenic)
  * [Issue 21](https://code.google.com/p/luke/issues/detail?id=21): luke tarball needs to extract to a "luke" directory (bevan.koopman,  Photodeus)
  * [Issue 27](https://code.google.com/p/luke/issues/detail?id=27): Cannot add or edit documents using StandardAnalyzer (dean.thrasher)

# Changes in version 3.5.0 (released on 2011.12.28) #
  * Update to Lucene 3.5.0 and fix some deprecated API usage.
  * [Issue 49](https://code.google.com/p/luke/issues/detail?id=49): fix faulty logic that prevented opening indexes in read-only mode (MarkHarwood).
  * [Issue 43](https://code.google.com/p/luke/issues/detail?id=43): fix left-over references to Field (merkertr).
  * [Issue 42](https://code.google.com/p/luke/issues/detail?id=42): Luke should indicate if a field is a numeric field (merkertr).

# Changes in version 3.4.0 (released on 2011.10.03) #
  * [Issue 46](https://code.google.com/p/luke/issues/detail?id=46): and 47: Update to Lucene 3.4.0 and fix some changed APIs.
  * Rearranged "field flags" so that they are more logical and cover index options added in 3.4.0. E.g. omitNorms is represented as "with Norms" and marked by "N", IndexOptions are expanded to "Idfp" to mark indexed fields with docs, freqs and positions.

Update: version 3.4.0\_1 fixes a silly last-minute typo in luke.xml.

# Changes in version 3.3.0 (released on 2011.07.06) #
  * [Issue 40](https://code.google.com/p/luke/issues/detail?id=40) and 41: Update to Lucene 3.3.0 and fix some deprecated / changed APIs.

# Changes in version 3.1.0 (released on 2011.04.30) #
This release uses Lucene 3.1.0 jars.

  * [Issue 35](https://code.google.com/p/luke/issues/detail?id=35): Lucene 3.1 compatible luke version (oss.akk)
  * [Issue 36](https://code.google.com/p/luke/issues/detail?id=36): XMLExporter generating invalid XML, when special characters are present in a TermVector field (Craig.Stires)
  * [Issue 17](https://code.google.com/p/luke/issues/detail?id=17): Recent changes to DocReconstructor sometimes cause null ref (solrtrey)
  * [Issue 19](https://code.google.com/p/luke/issues/detail?id=19): Custom directory implementation must be inherited from FSDirectory (mitja.lenic)
  * [Issue 21](https://code.google.com/p/luke/issues/detail?id=21): luke tarball needs to extract to a "luke" directory (bevan.koopman, Photodeus)
  * [Issue 33](https://code.google.com/p/luke/issues/detail?id=33): Term Positions increment incorrect (karolina.bernat)
  * [Issue 27](https://code.google.com/p/luke/issues/detail?id=27): Cannot add or edit documents using StandardAnalyzer (dean.thrasher)

# Changes in v. 1.0.1 (released on 2010.04.01) #
This release upgrades to Lucene 3.0.1 jars.

## New features and improvements ##
  * [Issue 5](https://code.google.com/p/luke/issues/detail?id=5): Field value decoder for 32 bit numeric fields (float, int) missing.
  * Added support for XmlQueryParser.
  * [Issue 12](https://code.google.com/p/luke/issues/detail?id=12): Add option to specify custom XmlQueryParser.
## Bug fixes ##
  * [Issue 3](https://code.google.com/p/luke/issues/detail?id=3): Analyzer plugin (and analyzers) don't work.
  * [Issue 4](https://code.google.com/p/luke/issues/detail?id=4): Compress flag no longer available.
  * [Issue 14](https://code.google.com/p/luke/issues/detail?id=14): Error while using custom similarity.

# Changes in v. 1.0.0 (released on 2009.12.23) #
This release just upgrades to Lucene 3.0 jars.

# Changes in v. 0.9.9.1 (released on 2009.11.20) #
This release upgrades to Lucene 2.9.1 jars and Hadoop 0.20.1 jars.

## New features and improvements ##
  * Add per-field value decoders, for displaying field values that should be interpreted as numeric or date or binary values.
  * Improve the Analysis plugin to switch between the mixed and the only-new API.
  * Improve visibility and layout of Thinlet tables.
  * Add display of commit user data Map.
  * Add ability to edit per-commit user data Map

## Bug fixes ##
  * Term frequency vectors were not displayed for selected field (reported by Benjamin Heilbrunn)