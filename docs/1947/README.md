# Strager concludes not to proceed with Rust, for now

Strager is a very no-nonsense Twitch streamer. He's not easily swayed by every trend that comes along, a very objective, and stoic individual (from whom wack-jobs like me can often learn from). So when he does his own comparison of Rust and C++ compilation times, everyone should pay attention. His conclusion? As one member of my community put it, "Spoiler: Strager wasn't pleased with Rust." You should definitely read his article for yourself. Here's my favorite parts:

::: Quote

(Of course, the reference to the XKCD "My code's compiling" comic.)

Conclusion

Are compilation times a problem with Rust? Yes. There are some tips and tricks to speed up builds, but I didn't find the magical order-of-magnitude improvements which would make me happy developing in Rust.

Are build times as bad with Rust as with C++? Yes. And for bigger projects, development compile times are worse with Rust than with C++, at least with my code style.

Looking at my hypotheses, I was wrong on all counts:

* The Rust port had more lines than the C++ version, not fewer.
* For full builds, compared to Rust, C++ builds took about the same amount of time (17k SLOC) or took less time (100k+ SLOC), not longer.
* For incremental builds, compared to C++, Rust builds were sometimes shorter and sometimes longer (17k SLOC) or much longer (100k+ SLOC), not always longer.

Am I sad? Yes. During the porting process, I have learned to like some aspects of Rust. For example, proc macros would let me replace three different code generators, simplifying the build pipeline and making life easier for new contributors. I don't miss header files at all. And I appreciate Rust's tooling (especially Cargo, rustup, and miri).

I decided to not port the rest of quick-lint-js to Rust. But... if build times improve significantly, I will change my mind! (Unless I become enchanted by Zig first.)

:::

* Is coding in Rust as bad as in C++?  
  <https://quick-lint-js.com/blog/cpp-vs-rust-build-times/>
