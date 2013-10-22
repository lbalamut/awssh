Makes SSHing to AWS instances less painful

Setup
=====

Create a file named config.json in one of the standard configuration directories
(eg. /etc/awssh for system stuff, ~/.config/awssh for user stuff), inspiring
yourself from config.json.dist . The column names can be any of the toplevel
properties of an object in an "instance_set" as decribed in
[here [1]](http://docs.aws.amazon.com/AWSRubySDK/latest/AWS/EC2/Client.html#describe_instances-instance_method).
The special "tag:" prefix can be used to show one of the tags.

To setup some SSH keys, create a folder names "keys" next to the config.json
file, and either copy or symlink there the SSH keys that are used to SSH to your
instances. The filename should be ssh-username@key-name.pem, so for example,
if your key is named "my_key" in amazon and the user to SSH as is "ec2-user",
you'd name the file ec2-user@my_key.pem.

Use
===

Just put the script somewhere in your path and run it, optionally passing the
AWS region to use as a parameter.

TODO
====
- Automatically download and setup private keys from AWS when possible.

---
[1] http://docs.aws.amazon.com/AWSRubySDK/latest/AWS/EC2/Client.html#describe_instances-instance_method
