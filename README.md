go-papi
=======


Description
-----------

go-papi provides a Go interface to PAPI, the [Performance Application
Programming Interface](http://icl.cs.utk.edu/papi/).  PAPI provides
convenient access to hardware performance counters, primarily those
provided by the CPU but with others (e.g., various networks) also
available.

As the [PAPI(3) man
page](http://icl.cs.utk.edu/projects/papi/wiki/PAPIC:PAPI.3) explains,
the PAPI API is split into "high level" and "low level" functions,
with the former being simpler to use but less flexible and the latter
providing finer-grained control over the sets of data measured and
reported.


Installation
------------

If necessary, set the `GOROOT` environment variable to the directory
containing `src/Make.inc` and `src/Make.pkg` and the `PAPI_INCDIR`
environment variable to the directory containing `papi.h`.  Also,
ensure that the directory containing `libpapi.so` is listed in your
`LD_LIBRARY_PATH`.

Afterwards, you can follow the usual Go package installation
procedure:

<pre>
    git clone http://github.com/losalamos/go-papi
    cd go-papi
    gomake
    gotest
    gomake install
</pre>

or simply

<pre>
    goinstall github.com/losalamos/go-papi
</pre>


Documentation
-------------

The go-papi API can be viewed with [godoc](http://golang.org/cmd/godoc/),
for example by running

<pre>
    godoc -http=:6060 -path=.
</pre>

to start a local Web server and viewing the documentation in your
favorite browser at <http://localhost:6060/pkg/go-papi/>.

For code examples, take a look at the `*_test.go` files in the go-papi
source distribution.  `papi_hl_test.go` utilizes PAPI's high-level
API; `papi_ll_test.go` utilizes PAPI's low-level API; and
`papi_test.go` utilizes a few miscellaneous functions.


License
-------

BSD-ish with a "modifications must be indicated" clause.  See
<http://github.com/losalamos/go-papi/LICENSE> for the full text.


Author
------

Scott Pakin, <pakin@lanl.gov>