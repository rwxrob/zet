# Bash Script to Swap DNS (`/etc/resolv.conf`)

<https://youtu.be/o_U76-7LmTQ>

WARNING: ONLY DO THIS STUFF IN A CONTAINER FIRST!

1. What is DNS?
1. Why do I care? 
1. How would I do this by hand? 
1. How could we automate this?
1. Create a `toggleres` script
1. Start by `while read -r line` through file
1. Use "recursive descent" approach
1. Create states when in section
1. Add toggle state if statements
1. Use `continue` early to continue line parsing
1. Put into function
1. Write to temp file
1. Copy file over production file
