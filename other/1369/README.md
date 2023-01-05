# Docker-Compose + Kompose = Kubernetes YAML

Sometimes it is just easier to capture everything in an application with
`docker-compose.yaml` instead of all the more verbose Kubernetes YAML
resource files. The `kompose` command helps out with this, but keep in
mind, this only works for *very* simple translations. Anything worth
using `docker-compose` for in actuality will probably have too much
variance for `kompose` to handle. In those cases it's better to just
write Kubernetes resource manifest files instead. 

Related:

* Kubernetes Tutorial : Learn how to use Kompose  
  <https://www.upnxtblog.com/index.php/2018/08/16/kubernetes-tutorial-learn-how-to-use-kompose/>
* Kubernetes + Compose = Kompose  
  <https://kompose.io/>
