# Go Firebase API/SDK uses much simpler design

>1. Asynchronous listeners: Data stored in a Firebase Realtime Database is retrieved by attaching an asynchronous listener to a database reference. The listener is triggered once for the initial state of the data and again anytime the data changes. An event listener may receive several different types of events. This mode of data retrieval is supported in Java, Node.js and Python Admin SDKs.
>2. Blocking reads: Data stored in a Firebase Realtime Database is retrieved by invoking a blocking method on a database reference, which returns the data stored at the reference. Each method call is a onetime operation. That means the SDK does not register any callbacks that listen to subsequent data updates. This model of data retrieval is supported in Python and Go Admin SDKs.

Yet another reason to use Go instead of Node/Typescript. By using blocking reads the control of the concurrency model implemented is entirely left in the hands of the developer and not forced on them.

Besides, the blocking read design is always easier to grok when looking at it, one query, one result. If you cannot wait around, background it. It's up to you.

