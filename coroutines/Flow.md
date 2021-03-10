# [Flow](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines.flow/-flow/)
An asynchronous data stream that sequentially emits values and completes normally or with an exception.

*Intermediate operators* are applied to the *upstream* flow or flows and return a *downstream* flow. Intermediate operations do not execute any code in the flow and are not suspending functions themselves. They only set up a chain of operations for future execution and quickly return. This is known as a *cold flow* property.

*Terminal operators* starts collection. They are applied to the upstream flow and trigger execution of all operations.

By default, flows are sequential and all flow operations are executed sequentially in the same coroutine

The `Flow` interface does not carry information whether a flow is a *cold* stream that can be collected repeatedly and triggers execution of the same code every time it is collected, or if it is a hot stream that emits different values from the same running source on each collection.

## Flow constraints
* Context preservation.
* Exception transparency.

## [업스트림 (네트워크)](https://ko.wikipedia.org/wiki/%EC%97%85%EC%8A%A4%ED%8A%B8%EB%A6%BC_(%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC))

By default, flows are *sequential* and all flow operations are executed sequentially in the same coroutine, with an exception for a few operations specifically designed to introduce concurrency into flow execution such as [buffer](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines.flow/buffer.html) and [flatMapMerge](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines.flow/flat-map-merge.html).

## [Reactive streams](http://www.reactive-streams.org/)
### [Reactive Streams](https://github.com/reactive-streams/reactive-streams-jvm/blob/v1.0.3/README.md)
