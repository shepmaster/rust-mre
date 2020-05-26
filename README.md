# Producing a [Minimal, Reproducible Example][mre] (MRE) for Rust code

Questions on Stack Overflow that seek debugging help ("why isn't this
code working?") must include the shortest code necessary to reproduce
it in the question itself. Without it, the question is off-topic and
is likely to be closed. Here are some common points to follow to
reduce your code to create a good MRE:

- Try to run your code in a different environment.
  - On the [Rust Playground][play]
  - In a separate Cargo project

- If your code fails to compile, include a copy of the error message,
  preferably complete and unmodified from the compiler's output.

- Remove unused
   - crates
   - modules
   - types
   - enum variants / members
   - struct members
   - function arguments / return values

- Combine modules in multiple files into a single file by rewriting:

    ```rust
    mod foo;
    ```

    as

    ```rust
    mod foo { /* contents of foo.rs */ }
    ```

- Replace complete or partial statements or entire function bodies
  with the macro `unimplemented!()`.

- Replace expressions and variables with hard-coded values. For
  example, replace a boolean value with `true` or `false`.

- Remove containing loops and conditional flow statements.

Remember that some steps might "unlock" other steps; try to apply each
step in turn until no steps can be followed! Ensure that your error
continues to occur after each change to avoid going down the wrong
path.

There's also some information that you should provide about your code:

- It will be assumed that you are using the current stable version of
  Rust. If you are not using this version of Rust, state your
  version. This can be found by running `rustc --version`.

- If you are using crates, state the versions of every crate that you
  are using. This can be found in your Cargo.lock file.

[mre]: https://stackoverflow.com/help/minimal-reproducible-example
[play]: https://play.rust-lang.org/
