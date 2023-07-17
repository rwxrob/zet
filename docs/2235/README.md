# Stop requiring tokens be environment variables!

I don't know what is with this generation of programmers who think it is safe to put tokens and secrets in environment variables, even if there is separation of environment based on user login preventing multi-user systems from giving these all up to anyone on the system. It's still a fucking horrible idea! Every time someone requires this I have to go to extreme lengths to ensure that my environment is never spilled to my screen. If these idiot developers had done the right thing---requiring these tokens be saved into files instead---then I can be sure to not show those files, which is much less risky. I'm vary sad to say that `charmbraclet/mods` (one of my favorite recent project discoveries) practices this absolutely brain-dead practice. Personally, I think it is container sickness. Docker was so FUCKING idiotic to make passing environment variables to container instances as the only fucking way to communicate with a new instance of a container that now everyone thinks passing *anything* in these horribly insecure env variables is just fine.

In fact, these idiots who wrote this interface to ChatGPT didn't even both to check if this was a good idea. If they had, this is what they would have seen:

```sh
$ mods -f 'is it safe to store passwords and tokens in environment variables?'
No, it is not safe to store passwords and tokens directly in environment variables. While environment variables provide a convenient way to store configuration data, they are not designed to securely store sensitive information such as passwords and tokens.

Storing passwords and tokens in environment variables can expose them to potential security risks. Environment variables are easily accessible to any process running on the same machine, making it easier for unauthorized users or malicious programs to access this sensitive data.

To enhance security, it is recommended to use secure storage mechanisms specifically designed for sensitive data, such as a dedicated password manager or a secure key vault. These tools provide additional layers of protection, including encryption and access control, to safeguard sensitive information from unauthorized access.
```
