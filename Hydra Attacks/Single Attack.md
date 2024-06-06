1. How to Perform a Single Username/Password Attack with Hydra

Here is the syntax:

$ hydra -l <username> -p <password> <server> <service>

$ hydra -l molly -p butterfly 10.10.137.76 ssh
