# To-do

Projects for later:

- Parser
  - Use [lalrpop](https://github.com/lalrpop/lalrpop)
  - Generics (`<...>`) modifies `<<` and `>>` tokens to shift out the first character of the token
- Type checker
  - This project is responsible for the type model.
  - It uses Hindley-Milner formula. Research:
    - https://www.reddit.com/r/rust/comments/jqm0rv/rust_type_checking/
    - https://rustc-dev-guide.rust-lang.org/type-inference.html
- Compiler to .wasm
- LSP (Language Server Protocol)
- Documentation tool
- Package manager
- GitHub Linguistic integration

Research:

- [Theory of name resolution](https://langdev.stackexchange.com/a/1129/606)

Due:

- Language reference (based or copy-pasted from Rust)
  - The following list items are updates, additions and removals. Besides them, after finishing copy-pasting the Rust reference, apply missing details from the language design.
  - Addition: declarative method macros (`o.f!()`).
    - It requires using `__self` instead of `self`.
    - The macro expands to `{let __self = o; ...}`.
  - Addition: the `Any` type, which is not any kind of structure.
  - Addition: `try` block (new scope for the `?` operator)
  - Addition: `_ {}` (inferred structure initializer)
  - Addition: structure fields with default value (`struct S { x: f64 = 0.0 }`)
  - Addition: `Delegate`
    - `From` (and therefore `Into`) is implemented for `Delegate`s to allow obtaining base.
  - Removal: No `...` in function types (variadic).
  - Addition: `mut` in tuple type fields.
  - Removal: `Deref`
  - Removal: `*v` (dereferencing operator)
  - Removal: `dyn`
  - Removal: `move`
  - Removal: `ref`
  - Removal: `unsafe`
  - Removal: lifetimes, but not the `'label` token. `'label` is used for loop labels only. `LIFETIME_OR_LABEL` token is now instead `LABEL_TOKEN`.
  - Removal: `extern crate`
  - Removal: `Vec` and `vec!` (just called array now)
  - Update: the brackets type is similiar to Rust's `Vec`. Unlike Rust, it has only one form, `[T]`.
  - Update: RustDoc is DSDoc and `rustdoc` is `divescript doc`.
  - Update: Function pointer types are now called function types, which work the same way as ActionScript `Function`.
  - Update: There is no `Fn`, `FnMut` or `FnOnce`.
- Language guidelines
  - Naming conventions
    - `static`, `const`, `let`
    - `_unused`
    - `_`: omitted