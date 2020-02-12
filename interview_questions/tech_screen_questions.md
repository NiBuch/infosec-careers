# Technical Screen Questions
------
These are basic questions used to screen technical competency. They'll often be asked by 
recruiters, HR staff, and other non-technical personnel to weed out candidates before interviewing with a 
hiring manager.

Bear in mind that for many of these, the recruiter is reading from a script. Don't be thrown off if they tell 
you an answer is incorrect, when you know it's right.

------
### Linux Proficiency
------

+ ##### How do you view a list of running processes in Linux?
Most of the time they're looking for `ps`, but some will also accept `top`.

+ ##### Where is a user's bash command history stored?
In-memory until the user logs out, at which point it's written into `.bash_history` in the user's home 
directory.

+ ##### If I run `chmod 765` on a file, what permissions did I give it?
Remember that each digit in the permissions corresponds to the `owner`, `group`, and `all users` groups 
in Linux. The individual numbers are the decimal representation of the permissions granted to that user 
group, where 'Read', 'Write', and 'Execute' correspond to the high-order, middle, and low-order bits, 
respectively. Tools like [chmod-calculator.com](http://chmod-calculator.com/) can help you figure out what 
privileges different permission values grant.
    
   For `chmod 765`:  
   - `owner` has permissions `7`, or Read, Write, and Execute  
   - `group` has permissions `6`, or Read and Write  
   - `all users` have permissions `5`, or Read and Execute

+ ##### Write a regular expression for an IPv4 address.

   |-------------------------------|--------------------------|
   | All (and only) valid IPv4 | `(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)` |
   | RFC1918 Class A | `(10)(\.([2]([0-5][0-5]|[01234][6-9])|[1][0-9][0-9]|[1-9][0-9]|[0-9])){3}` |
   | RFC1918 Class B | `(172)\.(1[6-9]|2[0-9]|3[0-1])(\.(2[0-4][0-9]|25[0-5]|[1][0-9][0-9]|[1-9][0-9]|[0-9])){2}` |
   | RFC1918 Class C | `(192)\.(168)(\.(25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9][0-9]|[0-9])){2}` |
   | All RFC1918 (prefixes) | `(^127\.)|(^10\.)|(^172\.1[6-9]\.)|(^172\.2[0-9]\.)|(^172\.3[0-1]\.)|(^192\.168\.)` |
   |-------------------------------|--------------------------|

Sometimes you can get away with `(?:[0-9]{1,3}\.){3}[0-9]{1,3}` but in an interview, it will often come off as too broad/lazy.


