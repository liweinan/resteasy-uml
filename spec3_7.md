JAX-RS SPEC 3.7 shows us how to match a URI path to actual Java method:

> 1. Identify a set of candidate root resource classes matching the request
> 2. Obtain a set of candidate resource methods for the request
> 3. Identify the method that will handle the request

Here's the classes that RESTEasy used to implement the algorithm:

![RESTEasy classes](https://github.com/liweinan/resteasy-uml/blob/master/imgs/spec3.7.png)

We can see many relationships from above picture.

`Match` contains a `MethodExpression` and a `Matcher`. `Matcher` is default Java regexp engine class.

`MethodExpression` contains `parent : SegmentNode` and `invoker : ResourceInvoker`. It also contains a method `compareTo(expression : Expression)`.
