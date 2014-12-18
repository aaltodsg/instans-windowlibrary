
## Aggregate Window Library

_Note: To run the example, [INSTANS](https://github.com/aaltodsg/instans) needs to be [installed](https://github.com/aaltodsg/instans/wiki). It is also assumed that
the $INSTANS_HOME environment variable points to the INSTANS root directory._

Some examples for computing aggregate values (sum, average, min, max)
over time windows. Both events and windows are configured using an RDF
input file. The current version supports e.g.:
* Both tumbling and non-tumbling (overlapping) windows
* Integer and xsdDatetime formats for time descriptors in events.

A test can be run by entering:

`$ ./aggr-test.sh`

The related files are:

* _queries/aggr-lib.rq_: The SPARQL "library" to compute aggregates
* _config/ex_windef.ttl_: Window and event configuration parameters defined in a turtle file
* _input/ex_events.ttl_: Some sample events for window trials (xsd:dateTime timestamp)
* _input/ex_int_events.ttl_: Sample events with an integer timestamp
* _aggr-test.sh_: The sample command line to run the example

The library and parameters are documented inline in the aggr-lib.rq and ex_windef.ttl files. Not everything is practical to parametrize and therefore users are encouraged to directly modify an own copy of aggr-lib.rq e.g. to match more complex input event formats or to format the output as needed.

Additionally the same repository contains a sample of using the SPARQL
built-in AVERAGE aggregate for computing averages with INSTANS. The files are aggr-builtin.rq and aggr-builtin.ttl. The example can be executed with:

`$ instans -r queries/aggr-builtin.rq -t data/aggr-builtin.ttl`
