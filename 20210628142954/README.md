# CmdBox to Use Godoc for Description

Realized that a lot of the CmdBox fields are redundant and would be
needed in the `doc.go` file as Godoc documentation as well, so rather
than force a copy and paste of nearly the same information I should just
use GoDoc for the `x.Description` and add a generator from `cmdbox`
command (to eventually come).
