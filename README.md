amf
===

[![Crates.io: amf](http://meritbadge.herokuapp.com/amf)](https://crates.io/crates/amf)
[![Documentation](https://docs.rs/amf/badge.svg)](https://docs.rs/amf)
[![Build Status](https://travis-ci.org/sile/amf.svg?branch=master)](https://travis-ci.org/sile/amf)
[![Code Coverage](https://codecov.io/gh/sile/amf/branch/master/graph/badge.svg)](https://codecov.io/gh/sile/amf/branch/master)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

A Rust Implementation of AMF (Action Media Format).


Documentation
-------------

See [RustDoc Documentation](https://docs.rs/amf/).

Example
-------

Following code decodes a AMF0 encoded value read from the standard input:

```rust
// file: examples/decode_amf0.rs
extern crate amf;

use std::io;
use amf::{Value, Version};

fn main() {
    let mut input = io::stdin();
    let amf0_value = Value::read_from(&mut input, Version::Amf0).unwrap();
    println!("VALUE: {:?}", amf0_value);
}
```

An execution result:

```bash
$ cat src/testdata/amf0-number.bin | cargo run --example decode_amf0
VALUE: Amf0(Number(3.5))
```

References
----------

- [AMF0 Specification](http://download.macromedia.com/pub/labs/amf/amf0_spec_121207.pdf)
- [AMF3 Specification](https://www.adobe.com/content/dam/acom/en/devnet/pdf/amf-file-format-spec.pdf)
- [Action Message Format - Wikipedia](https://en.wikipedia.org/wiki/Action_Message_Format)
