## Linux Commands that I should really just be remembering by now

`sudo tcpdump host <host>`, e.g. <host> = subdomain.domain.org
 - check traffic going to a certain host
 
`yes`
 - bobbing bird as a command. Not to be confused with typing `yes` when doing ssh related things. 
 - will just keep saying `yes` forever. Not useful for installation wizards unless you like toolbars. 
 
`cat <whatnot> | sort | uniq -c | sort -n`
 - sort and count an output, then order by instances of the lines (`-n` for numeric sorting)
 
 ### Git

`git grep <thing>`
 - grep through git for a thing. Can be faster that `grep <thing>` because of local non-git files
 
`git grep <thing> $(git rev-list --all)`
 - grep all commits 
 

