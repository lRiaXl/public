## matrix_transposition_4by3

### Instructions

- Define the structure matrix as a tuple of tuples of `i32`'s

- Define a function that calculate the transpose matrix of a 4x3 matrix (4 rows by 3 columns) which is a 3x4 matrix (3 rows by 4 columns).

- Note:

	- The transpose of a matrix `A` is the matrix `A'` where `A'`'s columns are `A`'s row and the rows are the columns:

Example:

```
( a b c )   __ transposition __>   ( a d g j )
( d e f )                          ( b e h k )
( g h i )                          ( c f i l )
( j k l )
```

- Matrix must implement Debug, PartialEq and Eq. You can use derive

- Remember that you're defining a library so you have to make public the elements that are going to be called from an external crate.

### Notions

[Chapter 7]( https://doc.rust-lang.org/stable/book/ch07-03-paths-for-referring-to-an-item-in-the-module-tree.html )

### Expected Function and Structs

```rust
pub struct Matrix4by3(
	pub (i32, i32, i32),
	pub (i32, i32, i32),
	pub (i32, i32, i32),
	pub (i32, i32, i32),
);

pub struct Matrix3by4(
	pub (i32, i32, i32, i32),
	pub (i32, i32, i32, i32),
	pub (i32, i32, i32, i32),
);

pub fn transpose(m: Matrix4by3) -> Matrix3by4 {
}
```

### Usage

Here is a posible program to test your function

```rust
fn main() {
	let matrix = Matrix4by3((1, 2, 3), (4, 5, 6), (7, 8, 9), (10, 11, 12));
    println!("Original matrix {:?}", matrix);
    println!("Transpose matrix {:?}", transpose(matrix));
}
```

And it's output:

```console
student@ubuntu:~/[[ROOT]]/test$ cargo run
Original matrix Matrix4by3((1, 2, 3), (4, 5, 6), (7, 8, 9), (10, 11, 12))
Transpose matrix Matrix3by4((1, 4, 7, 10), (2, 5, 8, 11), (3, 6, 9, 12))
student@ubuntu:~/[[ROOT]]/test$
```
