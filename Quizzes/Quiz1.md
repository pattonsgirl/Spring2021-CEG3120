# Quiz 1

1. In what file can I put ssh configurations for how I want to connect to the remote system? 

Configurations can include the username, the IP address of the system, and which private key I want to use.

- `~/.ssh/config`
- [see sample here](../config-files/.ssh/config)

2. I have an environment variable:

`HELLO="I am here"`

How do I call this variable to get the value?

- `printenv HELLO`
- `$HELLO`

3. -r-xrw---x sue hr bubbles.txt

What permissions does sue have for bubbles.txt?

- sue has `read` and `execute` permissions
- hr has `read` and `write` permissions
- other (everyone else) has `execute` permissions

4. What is the subnet mask corresponding to the following: `124.23.21.55/16`

- The first 16 bits are set.  Each set of binary 8 corresponds to decimal 255.
- The subnet mask / netmask is: `255.255.0.0`
- Which means all IPs matching this rule start with `124.23....`

5. What does the following do?

`git clone git@github.com:blah/project1.git`

- `git clone` clones the repository hosted at github.com by the git user into the folder project1
- This particular connection assumes that the public key of the system making the clone request is uploaded to github.com - could think of this as `~/.ssh/authorized_keys`