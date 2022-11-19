# Test Exec and Executables from Golang

Here's a trick I picked up from the Internetz for testing stuff that is
normally not testable using the Go (golang) testing framework. This
example tests a check for being run as a terminal or not. Unfortunately,
Go's coverage mechanics are far too primitive to ever catch this. The
idea is to actually use the temporarily created executable (in the
`/tmp` directory usually) as a would be standalone program containing
the code you want to test. Then you signal the calling test program what
state it is in by setting some sort of `TEST_*` environment variable and
using good 'ol UNIX return values to signal different error conditions
to the caller. Using this method can be used to test not only
stand-alone executables but full-blown web services by making
connections to the running program. It's quite a lot of scaffolding to
setup just for a test, but it shows that this stuff can be tested even
if their isn't an easy mock possibility available.

```go
// also coverage will never catch this test (oh well)
func TestIsTerminal_false(t *testing.T) {
	if os.Getenv("TEST_ISNOTTERM") == "1" {
		fmt.Println("out")
		if !IsTerminal() {
			os.Exit(20)
		}
		os.Exit(1)
	}
	exe := os.Args[0]
	cmd := exec.Command(exe, "-test.run=TestIsTerminal_false")
	cmd.Env = append(os.Environ(), "TEST_ISNOTTERM=1")
	cmd.StdoutPipe() // just enough to push into background
	err := cmd.Run()
	if e, ok := err.(*exec.ExitError); ok {
		t.Log(e.ExitCode())
		if e.ExitCode() != 20 {
			t.Errorf("exit %v: still a terminal", e.ExitCode())
		}
	}
}

```
