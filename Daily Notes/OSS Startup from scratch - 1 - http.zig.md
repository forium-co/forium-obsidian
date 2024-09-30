---
tags:
  - zig
  - blog
  - forium
date: 27 Sep, 2024
---
Time: 16 hours of work

## Copying Karl Seguin's work
One of the most prolific tinkerer of zig is Karl. So, to achieve my goal of building the best community platform, I am going to take Karl's work and make
it reach the vast atmosphere of internet lurkers.

So, let's start with `http.zig`

# Contents:
1. Zig on your machine - installing and running Zig
2. Writing the build system for http.zig
3. File-by-file writing
	0. How do we proceed.
	1. `url.zig` and it tests
	2. ``
4. Writing tests
5. Running wrk benchmarks.

---
## Intro to Zig and running it locally

- Zig is a general-purpose programming language designed for systems programming, known for its simplicity, performance, and safety features.
- It was created by Andrew Kelley, with a focus on providing explicit control over code behavior, making it ideal for low-level tasks such as operating
	- systems, game engines, or performance-critical applications.
	
#### Key features of Zig:
1. **Manual Memory Management**: Zig offers explicit control over memory without the automatic garbage collection found in higher-level languages like Go or Python.
2. **Error Handling**: Instead of exceptions, Zig uses a robust error handling mechanism with the try keyword, making it easier to track and manage errors without performance penalties.
3. **Compile-time Execution**: Zig supports compile-time code execution, enabling optimizations and checks while the program is being compiled.
4. **Cross-compilation**: The language has built-in support for cross-compilation, allowing developers to easily target multiple platforms from a single system.
5. **No Hidden Control Flow**: There are no hidden allocations or function calls, so the programmer has full visibility and control over what the code is doing.
6. **Interop with C**: Zig can seamlessly interoperate with C code, allowing for easy integration with existing C libraries or codebases.

Zig aims to provide a balance between high performance and safety, making it attractive for developers who want low-level control while avoiding some of the pitfalls of languages like C or C++.

Relevant links:
- [Home ⚡ Zig Programming Language](https://ziglang.org/)
- Learn Zig: [Welcome | zig.guide](https://zig.guide/) 
- Ask questions: [Ziggit - A Zig community](https://ziggit.dev/)(whose clone we are making now)
- Some Zig exercises: [Site Unreachable](https://ziglings.org/)

## Zig vs Rust

Zig and Rust are systems programming languages with different design goals. Zig's advantages over Rust include:

- Easier to learn and use
- More flexible and lenient borrowing rules
- Faster compile times
- Better support for dynamic memory allocation
- More extensive standard library

Zig offers simplicity, manual memory control, and seamless C interoperability, making it ideal for low-level, performance-critical systems. It has built-in cross-compilation and powerful compile-time execution. Rust, while more complex, provides stronger safety guarantees through its ownership and borrowing model, preventing many memory-related bugs. Choose Zig for manual control and simplicity, and Rust for safety and a larger ecosystem.

---
### Zig Arena Allocator
**Arena Allocation in Zig**

Arena allocation is a memory management technique used in Zig to efficiently allocate and deallocate memory for a group of objects. An arena is a contiguous block of memory that can be used to allocate objects of varying sizes.

**Why Use Arena Allocation?**

Arena allocation is useful when you need to allocate and deallocate many objects of different sizes, such as in a game or a scientific simulation. It provides several benefits:

* **Efficient memory allocation**: Arena allocation reduces the overhead of individual memory allocations and deallocations.
* **Reduced fragmentation**: Arena allocation helps to reduce memory fragmentation by allocating objects in a contiguous block.
* **Simplified memory management**: Arena allocation simplifies memory management by allowing you to allocate and deallocate objects in a single step.

**Example: Creating an Arena**

Here's an example of creating an arena in Zig:
```rust
const std = @import("std");

pub fn main() !void {
    var arena = std.heap.ArenaAllocator.init(std.heap.page_allocator);
    defer arena.deinit();

    var allocator = &arena.allocator;
    // ...
}
```
In this example, we create an arena allocator using the `std.heap.ArenaAllocator` type. We then initialize the arena using the `init` method, passing in the `std.heap.page_allocator` as the underlying allocator. Finally, we create a reference to the arena's allocator using the `allocator` field.

**Example: Allocating Objects in an Arena**

Here's an example of allocating objects in an arena:
```rust
const std = @import("std");

pub fn main() !void {
    var arena = std.heap.ArenaAllocator.init(std.heap.page_allocator);
    defer arena.deinit();

    var allocator = &arena.allocator;

    var obj1 = try allocator.alloc(u8, 10);
    var obj2 = try allocator.alloc(u32, 5);

    // Use obj1 and obj2...
}
```
In this example, we allocate two objects in the arena using the `alloc` method. The first object is an array of 10 `u8` values, and the second object is an array of 5 `u32` values.

**Example: Deallocating an Arena**

Here's an example of deallocating an arena:
```rust
const std = @import("std");

pub fn main() !void {
    var arena = std.heap.ArenaAllocator.init(std.heap.page_allocator);
    defer arena.deinit();

    var allocator = &arena.allocator;

    var obj1 = try allocator.alloc(u8, 10);
    var obj2 = try allocator.alloc(u32, 5);

    // Use obj1 and obj2...

    // Deallocate the arena
    arena.deinit();
}
```
In this example, we deallocate the arena using the `deinit` method. This will deallocate all objects allocated in the arena.

Note that when you deallocate an arena, all objects allocated in the arena are also deallocated. This is why arena allocation is often used for objects that have a short lifetime, such as in a game or scientific simulation.

For more on this consult: 

---
### Running Zig locally and cross-compiling it

........to be written later.........
**`TODO`**

---
# http.zig journey: Let's start it with the build system




