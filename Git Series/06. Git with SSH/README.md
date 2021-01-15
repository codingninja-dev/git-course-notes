<h1 align='center'>~ Git with SSH ~</h1>

<h3>Git with HTTPS</h3>
<p>If you use the Git version control system with a service such as GitHub, GitLab or Bitbucket to host and manage your projects source codes, you know that by default Git connects to remotes using the HTTPS protocol, which requires you to enter username and password every time you run a command such as git pull or git push.</p>

<h3>Git with SSH Key Authentication</h3>
<p>Using the SSH protocol, you can connect and authenticate to servers to use their services. The three mentioned services above allow Git to connect via SSH instead of HTTPS. Connecting with public key encryption dispenses typing username and password for every Git command.</p>

<h3>How SSH key authentication works</h3>
<p>SSH public key authentication works with generating a pair of keys consisting of public and private keys. These keys are known as encryption keys. SSH uses these pair of keys to initiate a secure handshake between remote parties. The public key is shared with GitHub, GitLab or Bitbucket and used to verify the initial ssh connection. The private key is kept safe and secure on your system.</p>

<p>To get ssh up and running on your machine visit <a href="https://support.atlassian.com/bitbucket-cloud/docs/set-up-an-ssh-key/">here</a> to get more information on generating your keys and getting it setup.</p>

<h3>Using Bash Profile File</h3>

<p>If you don't want to manually add your private key everytime you start up your git bash command prompt you can add a few commands to the bash profile in your home directory so you can autoload it when the command line starts. Adjust accordingly depending on your needs.</p>

```
// .bash_profile file
echo '~ Loading PPK Key ~'
eval $(ssh-agent)
ssh-add ~/.ssh/id_rsa
echo '~ Routing to Desktop ~'
cd ~/Desktop/
```
