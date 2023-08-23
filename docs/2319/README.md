# The reason to use non-pointer receivers when possible

I finally see why non-pointer receivers are generally preferred whenever possible. Pointer receiver methods may *never* be used when someone wants to override the interface (since interfaces always use non-pointers). This is the very reason that `fmt.Stringer` was implemented the way it was. Moral of the story: always use non-pointer receivers unless you *really* know you are going to need them.

## ChatGPT response

The fmt.Stringer interface in Go is defined with a value receiver instead of a pointer receiver for a few reasons:

1. Compatibility: When the fmt package was created, it was decided that the Stringer interface should be compatible with any type. Accepting a value receiver allows any type to satisfy the Stringer interface without requiring a pointer receiver. This means that it is possible to use types defined in other packages as Stringer implementations.

2. Simplicity: By using a value receiver, the interface becomes simpler to use since it accepts values directly without requiring the creation of a pointer. It also simplifies the implementation of the interface for types that already have value semantics.

3. Safety: A value receiver ensures that the Stringer interface does not accidentally modify the state of the object it operates on. The Stringer interface is primarily used for generating human-readable string representations of values and should not modify any underlying state.

However, it's worth noting that there are cases where implementing the Stringer interface with a pointer receiver might be necessary or beneficial, especially if the implementation requires modifying the state of the object. But for most use cases, a value receiver is sufficient and provides a simpler and safer approach.

