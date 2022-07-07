[![Actions Status](https://github.com/lizmat/span/actions/workflows/test.yml/badge.svg)](https://github.com/lizmat/span/actions)

NAME
====

snip - Provide functionality similar to Haskell's span

SYNOPSIS
========

```raku
use snip;

.say for snip * < 10, 2, 2, 2, 5, 5, 7, 13, 9, 6, 2, 20, 4;
# (2 2 2 5 5 7)
# (13 9 6 2 20 4)

.say for snip (* < 10, * < 20), 2, 2, 2, 5, 5, 7, 13, 9, 6, 2, 20, 4;
# (2 2 2 5 5 7)
# (13 9 6 2)
# (20 4)

.say for snip Int, 2, 2, 2, 5, 5, "a", "b", "c";
# (2 2 2 5 5)
# (a b c)
```

DESCRIPTION
===========

The `snip` distribution exports a single subroutine `snip` that mimics the functionality provided by [Haskell's span functionality](https://hackage.haskell.org/package/base-4.16.1.0/docs/Prelude.html#v:snip). But only if the core does not supply a `snip` subroutine already (which it may at some point in the future).

The `snip` subroutine takes a matcher much like `grep` does, which can be a `Callable` or any other object that can have the `ACCEPTS` method called on it. Different from the Haskell's `span` implementation, `snip` can take multiple matchers to snip the origin list in more than 2 parts.

AUTHOR
======

Elizabeth Mattijsen <liz@raku.rocks>

Source can be located at: https://github.com/lizmat/snip . Comments and Pull Requests are welcome.

If you like this module, or what I’m doing more generally, committing to a [small sponsorship](https://github.com/sponsors/lizmat/) would mean a great deal to me!

COPYRIGHT AND LICENSE
=====================

Copyright 2022 Elizabeth Mattijsen

This library is free software; you can redistribute it and/or modify it under the Artistic License 2.0.

