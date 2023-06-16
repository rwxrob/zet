# You cannot change stop and start to get minikube --extra-args

Learned the hard way that to get `--extra-args` changes to take using `minikube` that I have to destroy (not stop) and then restart with the extra arguments for them to be cached.
