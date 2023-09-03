# To-do

Projects for later:

- Highlighter
- Parser
  - Use [lalrpop](https://github.com/lalrpop/lalrpop)
  - Generics (`<...>`) modifies `<<` and `>>` tokens to shift out the first character of the token
- Type checker
  - This project is responsible for the type model.
  - It uses Hindley-Milner formula. Research:
    - https://www.reddit.com/r/rust/comments/jqm0rv/rust_type_checking/
    - https://rustc-dev-guide.rust-lang.org/type-inference.html
- Compiler to AVM bytecode
- LSP (Language Server Protocol)
- Documentation tool
- Package manager
- GitHub Linguistic integration

Research:

- [Theory of name resolution](https://langdev.stackexchange.com/a/1129/606)

Due:

- Language reference (based or copy-pasted from Rust)
  - The following list items are updates, additions and removals. Besides them, after finishing copy-pasting the Rust reference, apply missing details from the language design.
  - Addition: Do not allow `Option<Option<T>>` (`Option` of `Option`).
  - Addition: declarative method macros (`o.f!()`).
    - It requires using `__self` instead of `self`.
    - The macro expands to `{let __self = o; ...}`.
  - Addition: Structure constructor method
  - Addition: `super()` to construct super class
  - Addition: `super.f()`
  - Addition: `extern` modifier on `struct`
  - Addition: `extern` modifier on `trait`
  - Addition: the `Any` type, which is not any kind of structure.
  - Simplification: `extern` on `fn` is simplified to contain no ABI
  - Addition: `try` block (new scope for the `?` operator)
  - Addition: `macro` (from the [Rust declarative macros proposal](https://github.com/rust-lang/rfcs/blob/master/text/1584-macros.md))
    - Two forms
      - Single example (parentheses followed by either `=>` or block)
      - Comma-separated examples
  - Addition: `_ {}` (inferred structure initializer)
  - Addition: structure fields with default value (`struct S { x: f64 = 0.0 }`)
  - Addition: `Delegate`
    - `From` (and therefore `Into`) is implemented for `Delegate`s to allow obtaining base.
  - Addition: `...` in function types (variadic).
  - Addition: `mut` fields in `struct` and `enum` variants
  - Addition: `mut` tuple elements (in tuple types, tuple structures and tuple variants)
  - Removal: No generic `const` parameters
  - Removal: `Deref`
  - Removal: `*v` (dereferencing operator)
  - Removal: `dyn`
  - Removal: `move`
  - Removal: `ref`
  - Removal: `unsafe`
  - Removal: `macro_rules!` (`macro` is used instead)
  - Removal `union`
  - Removal: lifetimes, but not the `'label` token. `'label` is used for loop labels only. `LIFETIME_OR_LABEL` token is now instead `LABEL_TOKEN`.
  - Removal: `#[no_mangle]`
  - Removal: `extern crate`
  - Removal: `Vec` and `vec!` (just called array now)
  - Update: variadic functions: only extern functions can be variadic.
  - Update: the brackets type is similiar to Rust's `Vec`. Unlike Rust, it has only one form `[T]` and is equivalent to `Array<T>`.
  - Update: RustDoc is DS Doc and `rustdoc` is `dsdoc`.
  - Update: Function pointer types are now called function types, which work the same way as ActionScript `Function`.
  - Update: There is no `Fn`, `FnMut` or `FnOnce`.
- Language guidelines
  - Naming conventions
    - `static`, `const`, `let`
    - `_unused`
    - `_`: omitted