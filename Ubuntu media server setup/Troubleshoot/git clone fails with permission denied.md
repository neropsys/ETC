# Git clone fails with permission denied, but successfully authenticates


# TLDR;
[Have git use specific keys](https://stackoverflow.com/a/59074070)  
I had multiple keys which caused the issue.
Git uses private key named 'id_rsa' as default, but I name private keys based on their usage.


# Details
Github provides general information about authorization issues right [here](https://docs.github.com/en/github/authenticating-to-github/error-permission-denied-publickey)

But as for me I was already familiar with using public keys.
Which means I already added keys to my github account, checked the link above and still couldn't find ways to resolve it.

Few minutes of Googling, and I found that git uses key named 'id_rsa' as default, which I don't have.

So I just ran command below to specify which keys to use
```
git clone git@provider.com:userName/projectName.git --config core.sshCommand="ssh -i ~/location/to/private_ssh_key"
```
And set keys permission as u+x
```
chmod u+x /Users/someone/.ssh/id_rsa
```

