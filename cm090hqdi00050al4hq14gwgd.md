---
title: "How to Implement Enums in Go: Step-by-Step Guide"
seoTitle: "Enums in Go: Step-by-Step Implementation Guide"
seoDescription: "Implement Go enums using constants and custom types. Learn best practices for type safety and readability"
datePublished: Sun Aug 25 2024 03:30:33 GMT+0000 (Coordinated Universal Time)
cuid: cm090hqdi00050al4hq14gwgd
slug: how-to-implement-enums-in-go-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1724520447908/a8e312a5-995d-47b1-ba51-1621eb463d2a.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1724520476075/7f58dc48-532f-4597-b3fe-1d327f347585.png
tags: go

---

Go, also known as Golang, is a statically typed, compiled language designed for simplicity and efficiency. One feature Go doesn't have natively, unlike many other programming languages, is support for enumerated types or "enums." However, you can implement a similar pattern in Go using constants and custom types. This article will guide you through the process of creating and using enums in Go, helping you avoid common pitfalls and take full advantage of Go's type safety.

### What Are Enums?

Enums (short for "enumerations") are a way to define a collection of related constants in many programming languages. These constants are often used to represent a set of predefined values, such as the states of an order in an e-commerce system (e.g., Received, Confirmed, Prepared, Delivered). Enums improve code readability and help prevent errors by restricting values to a specific set.

### Go's Approach to Enums

Go doesn't have built-in support for enums like languages such as Java or C#. However, Go's type system allows you to create similar functionality using constants and custom types. This approach provides type safety and helps prevent common errors, such as assigning an invalid value to a variable.

### Implementing Enums in Go

Let's walk through the process of creating enums in Go, step by step.

#### 1\. Define a Custom Type

First, define a custom type that will represent your enum values. This type can be based on any built-in Go type, but it's common to use `int` or `string`.

```go
type OrderStatus int
```

In this example, `OrderStatus` is a custom type based on the `int` type. This custom type will hold our enum values.

#### 2\. Define Constants Using `iota`

Go's `iota` identifier is a handy way to create a sequence of related constants. It's often used in enum-like patterns.

```go
const (
    Received  OrderStatus = iota // 0
    Confirmed                    // 1
    Prepared                     // 2
    Delivered                    // 3
)
```

Here, we're using `iota` to automatically assign increasing integer values to each constant, starting from `0`. This approach is clean and concise, ensuring that the constants are logically ordered.

#### 3\. Use the Enum in Your Code

Now that you've defined your enum, you can use it in your code just like any other type.

```go
func changeOrderStatus(status OrderStatus) {
    fmt.Println("Changing order status to", status)
}

func main() {
    changeOrderStatus(Received)
}
```

In this example, the `changeOrderStatus` function takes an `OrderStatus` as a parameter. The function then prints the current order status to the console. When you run this code, it will output:

```plaintext
Changing order status to 0
```

This output corresponds to the integer value of `Received`, which is `0`.

### Improving Readability with String Representation

By default, when you print an enum value in Go, you get the underlying integer or string value. While this is functional, it isn't very human-readable. To improve this, you can implement the `Stringer` interface, which allows you to define a custom string representation for your enum.

```go
func (status OrderStatus) String() string {
    switch status {
    case Received:
        return "Received"
    case Confirmed:
        return "Confirmed"
    case Prepared:
        return "Prepared"
    case Delivered:
        return "Delivered"
    default:
        return "Unknown"
    }
}
```

With this implementation, when you print an `OrderStatus`, you'll get a meaningful string instead of just an integer.

```go
func main() {
    fmt.Println(Received)  // Output: Received
    fmt.Println(Confirmed) // Output: Confirmed
}
```

### Using String-Based Enums

If you prefer to work with strings directly, you can define your enum values as strings. This approach is particularly useful when you need to work with values that must be human-readable or when interacting with external systems, such as APIs.

```go
type OrderStatus string

const (
    Received  OrderStatus = "received"
    Confirmed OrderStatus = "confirmed"
    Prepared  OrderStatus = "prepared"
    Delivered OrderStatus = "delivered"
)
```

With this approach, the enum values are strings instead of integers. This method is just as effective and provides better readability in certain contexts.

### Best Practices for Enums in Go

1. **Use Custom Types:** Always define a custom type for your enums. This practice ensures type safety and prevents accidental misuse of enum values.
    
2. **Leverage** `iota`: When using integer-based enums, `iota` simplifies the process of assigning values and makes your code cleaner.
    
3. **Implement the** `Stringer` Interface: Providing a string representation for your enums enhances readability, especially in debugging and logging.
    
4. **Consider String-Based Enums for Readability:** When working with enums that are exposed to users or external systems, string-based enums can improve clarity.
    

### Conclusion

While Go doesn't have native enum support, you can effectively implement enum-like functionality using constants and custom types. By following the best practices outlined in this guide, you'll be able to create clear, type-safe, and maintainable code.