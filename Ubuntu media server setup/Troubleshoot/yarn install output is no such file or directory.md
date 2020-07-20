# Yarn install cmd results in error 'No such file or directory: 'install'

# TLDR
```
sudo apt remove cmdtest
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update && sudo apt install yarn
```


# Cause
Running cmd
```
sudo apt install yarn
```
Causes ubuntu to install cmdtest instead of yarn.
So delete by
```
sudo apt remove cmdtest
```
and follow official yarn [installation guide](https://classic.yarnpkg.com/en/docs/install/#debian-stable)