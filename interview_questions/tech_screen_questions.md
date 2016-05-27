# Technical Screen Questions
======

These are basic questions used to screen technical competency. They'll often be asked by 
recruiters, HR staff, and other non-technical personnel to weed out candidates before interviewing with a 
hiring manager.

Bear in mind that for many of these, the recruiter is reading from a script. Don't be thrown off if they tell 
you an answer is incorrect, when you know it's right.

### Linux Proficiency

+ ##### How do you view a list of running processes in Linux?
Most of the time, they're looking for `ps`, but will some will also accept `top`.

+ ##### Where is a user's bash command history stored?
In-memory until the user logs out, at which point it's written into `.bash_history` in the user's home 
directory.

+ ##### If I run `chmod 765` on a file, what permissions did I give it?
Remember that each digit in the permissions corresponds to the `owner`, `group`, and `all users` groups 
in Linux. The individual numbers are the decimal representation of the permissions granted to that user 
group, where 'Read', 'Write', and 'Execute' correspond to the high-order, middle, and low-order bits, 
respectively. 
    
   For `chmod 765`:  
   - `owner` has permissions `7`, or Read, Write, and Execute  
   - `group` has permissions `6`, or Read and Write  
   - `all users` have permissions `5`, or Read and Execute  

