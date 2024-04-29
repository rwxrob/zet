# Best practice for building Go projects from private/innersource repos

* ~~Create an SSH key pair and add deployment key to each private pkg repo~~
* ~~Authorize additional SSH public key for main account~~
* Create pseudo-account and add as read-only collaborator to every private pkg repo

The only viable option where multiple private/innersource Go repos are involved is to create a pseudo-account with at least one ssh key pair to authenticate to that account and bake the priv key into all CI/CD that needs to pull down the private stuff for its builds. The pseudo-account itself is the security umbrella and only granted limited access to the private repos so that it can read them. If the pseudo-account private key is compromised at worst only read access to the source happens (preventing malicious trojans, etc.). While it is annoying to change the private key in all GitHub actions in such a case it is better than doing the same with a more privileged account.

* How to Use a Private Go Module in Your Own Project \| DigitalOcean  
  <https://www.digitalocean.com/community/tutorials/how-to-use-a-private-go-module-in-your-own-project>
