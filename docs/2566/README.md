# Batch is SO much more important than "cloud native"

Monday, May 6, 2024, 1:51:30PM EDT

Recent buzz has confirmed what I've felt since I took a job as a Kubernetes Infrastructure Engineer: Kubernetes kinda sucks. VMs are better.

More importantly, as I've implemented the core building blocks of a business critical API allowing our enterprise applications to submit and manage huge machine learning models and different jobs it has become increasingly obvious that "batch" is where the action is—especially in a post-machine-learning revolution. In fact, OpenPBS is far more important to the future of enterprise computing than Kubernetes ever will be.

What the hell is "batch"? It is a core architecture business pattern that has been around since the days of mainframe computing. It's simple, really. Send a big job to a resource to work on and periodically check on it until its done and have a place to see what it has created (it's "artifacts"). Batch jobs are characterized by work that takes several hours—or even days—to complete.

Kubernetes was never designed for "batch" jobs. Every attempt to bring these patterns into Kubernetes has miserably failed. Kubernetes is fundamentally about providing services—specifically "micro-services" as originally championed by Amazon. But services are fundamentally less important to an organization in 2024 than the models created from long-running machine-learning batch jobs. In fact, services are downright trivial in comparison with regard to value. Practically any web server can front a query to a model generated from batch processing. This is putting architectural pressure on the middle layers to get even simpler and more efficient. Kubernetes is moving in the exact opposite—and wrong—direction including completely stupid things like KubeVirt. I predict several major enterprises will throw out Kubernetes completely in the coming five years and replace it with cookie-cutter services that are specifically designed to front the jewels, the results of data models processed on the core IT infrastructure running "in batch." Who knows, we might even see a resurgence of *real* interest in mainframe options since nothing—not even 0xide—can compete with the raw batch process power available in old-school mainframe systems.

* OpenPBS Open Source Project  
  <https://openpbs.org/>
* https://thenextweb.com/news/the-future-of-cloud-native-kubernetes
