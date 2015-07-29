# Compatibility #
## Java version ##
Minimum version of JVM required to run Luke 1.0.1 and earlier is 1.5.

Minimum version of JVM required to run Luke 3.x and 4.x is 1.6.

## Lucene Java indexes ##
Luke 1.0.1 should be able to open indexes built using the following versions of Lucene-Java:

  * 3.0.x
  * 2.x (any version)
  * _(1.9? 1.4? earlier? to be verified)_

Please note that if you used Field.Store.COMPRESSED in your index, your field can be still retrieved by Lucene 2.9+, but the content of the field will be automatically decompressed. This means that during optimize the size of your index may grow substantially.

Starting with version 4.x Luke cannot open indexes created with Lucene 3.0.0 or earlier.

Starting with version 3.1.0 Luke releases will use the same numbering as Lucene releases, to avoid confusion.

## Lucene.Net indexes ##
Apparently recent versions of Lucene-Java cannot open indexes built with Lucene.Net - reported incompatible versions include:

  * Lucene.Net 2.3.2.1 and Lucene-Java 2.9.1

At the moment there is no workaround for this issue.