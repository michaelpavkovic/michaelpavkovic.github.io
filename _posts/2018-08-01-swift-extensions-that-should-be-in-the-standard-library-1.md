---
layout: post
title:  "Swift: Extensions That Should Be in the Standard Library #1 - forEachIndexed"
categories: swift extensions forEachIndexed
---
This is the start of a series on my blog where I will discuss extensions of generic constructs in the Swift programming language that should be part of its standard library.

Today's entry: `forEachIndexed`. In Swift, a `Collection`'s elements must be accessable by an indexed subscript. Because of this, it makes sense to provide a method to iterate through the `Collection` and provide the indices. 

The extension in mind is fairly self explanatory. It works exactly the same way as the built-in `forEach` method, except it provides the current element's index through a closure parameter. Since it operates on a `Collection`, it will work wherever `forEach` works. Languages such as Kotlin already include `forEachIndexed`, and it is a very handy feature.

Here is what I wrote to implement `forEachIndexed`:
```swift
extension Collection {
	/// Calls the given closure on each element in the sequence in the
	/// same order as the `forEach` method, providing the element's
	/// index in its collection on each iteration
	///
	/// - Parameter body: A closure that takes an element of the
	/// sequence and its index as parameters
	func forEachIndexed(_ body: (Element, Index) throws -> Void) rethrows {
		var currentIndex = startIndex
		
		for element in self {
			try body(element, currentIndex)
			
			currentIndex = index(after: currentIndex)
		}
	}
}
```