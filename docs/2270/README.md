# Common interface or messaging bus, or both?

I'm at a crossroads in design of this concurrent Cozy tool, there are a lot of ways to achieve concurrency and pluggable, agents that maintain connections and interactions with the different services out there.

One way is to create a common Agent interface that required `context.Context` to be passed. I think this is generally known as the "middleware" approach. Gin, echo, and pretty much all middleware platforms do this so integrating into existing frameworks is easier if this design is followed.

Another way is to grow-your-own messaging bus. The advantage of this is that all the agents can publish and subscribe events and behave independently while maintain flexible communication peer-to-peer within the controller itself. This is a much more sustainable and performant approach but is quite a bit more complex to implement.

The question is which one to use?

Perhaps we could use both. If we define an Agent interface we can still add a messaging bus with a specific extension to the Agent interface later to deal with those communications. This would allow creators of controllers to decide for themselves how they want to design the controller, using a framework, or their own.
