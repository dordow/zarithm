# zarithm
LaTeX files to add arithmetics to ZRM style specifications
=======
# Introduction

The first version of the formal notation Z was defined in the Z
Reference Manual (ZRM) by Mike Spivey, who also developed the tool
`fuzz` to type check Z specifications written in LaTeX. This ZRM version
of Z does not support rational and real numbers out of the box. Z was
later standardized by ISO and IEC (ISO/IEC 13568:2002(E)) where the
mathematikal toolkit was extended to include rational and real numbers.
However, for an occasional Z user like me it can be better to stick with
the ZRM version for the following reasons:

-   The `fuzz` type checker is very stable and easy to use (on the
    command line), and it works on LaTeX sources.
-   The `fuzz` tool is well documented.
-   The ZRM is an easy read, the ISO standard is not (at least not for
    me).

The intention of this project is to provide ZRM level arithmetic
definitions for rational and real numbers, following the ideas of Sam
Valentine\'s \"Definitions of Numbers in Z\".

The approach described here makes use of the fact that `fuzz` accepts
more than one LaTeX file and remembers the Z definitions of the files
provided first. It is not necessary to include all number definitions in
ones own LaTeX file.

Note that the Z definitions are sufficient for type setting, not for
automated proof. If the user intends to use automated proof, there is
probably no better way than to transit to standard Z.

# Usage

There are two files, `zarithm.tex` and `zarithm.sty`. The latter
provides the LaTeX commands for typesetting the number sets, operations
and relations. Ideally, it should be placed where the style files for
LaTeX are located. The former file includes the Z definitions of the
number sets, some prominent constants, the operations and relations.

When using `fuzz`, one needs to provide `zarithm.tex` as first file:

``` example
fuzz <path to zarithm.tex>zarithm.tex <my_z_spec.tex>
```

An example can be found unter `./test/polynomials.tex`.

