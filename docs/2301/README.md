# Example-based testing even with complicated network deps

I really love example-based testing in Go. I mean, you get documentation for free. Why wouldn't you do that? It absolutely astounds me how many substantial Go projects have absolutely zero example-based tests even though the test code could easily have been written to use them. What a wasted opportunity to make those code bases easier to grok for developers everywhere.

There's one problem though, and it doesn't just affect example-based tests. It affects *all* testing. Sometimes the testing depends heavily on specifics in an environment, in fact, usually the most important testing requires this. This is why containerized testing is such a thing. All the services being tested can be contained and tested without maintaining a complicated lab that would have to be reconfigured for every test.

Example-based tests actually provide a middle ground in this scenario. Whether with a containerized test environment, or just local setup to accomplish the test an example-based test can be written to cover the situation and then the `// Output:` line can be changed to `/// Output:` disabling it while keeping it in the documentation. Then someone reading the example will infer what is needed to create their own testable environment. This allows me to use runnable unit tests during live development and keep the example without the need to comment out or remove later.

The great thing about the `//` and `///` is that I only have to change one character to re-enable the test when I want to modify and test that specific thing. This is *way* easier than commenting out the entire test code and leaves it visible in the documentation.
