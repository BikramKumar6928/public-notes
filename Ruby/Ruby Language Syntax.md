#ruby #notes 

## Variables

### Local Variables

```ruby
def function
	variable = 10 # the name can begin with lowercase or `_`
end
```

### Instance Variables

```ruby
class Customer
	@cust_id # the instance variable name must begin with a `@`
end
```


### Class Variables

```ruby
class Customer 
	@@no_of_customers = 0 # The name must begin with `@@`.
end
```

### Global Variables
```ruby
$global_variable = 10
```

Note:- Do not use global variables. Makes things hard to follow.


### Constants

If the constant is defined inside class, it will be visible inside class but nowhere else.

If the constant is defined outside class, it will be visible everywhere.

```ruby
class Example
	VAR1 = 100 # The name must be in all caps.
	VAR2 = 200
	def show
		puts "Value of first Constant is #{VAR1}"
		puts "Value of second Constant is #{VAR2}"
	end
end
```

## Class

```ruby
class Customer
	@@no_of_customers = 0 
	def initialize(id, name, addr) 
		@cust_id = id # the instance variable name must begin with a `@`
		@cust_name = name 
		@cust_addr = addr 
	end 
end
```

## Creating new objects

```ruby
def function
	customer1 = Customer.new("1", "name", "multi word address")
end
```

### Numbers in Ruby

This is a valid number

```ruby
1_234 # Fixnum decimal with underline
```

### Pseudo Variables in Ruby

- `self` : Equivalent to `this` in Java.
- `nil`: Equivalent to `null` in Java.

### Arrays

```ruby
ary = [ "fred", 10, 3.14, "This is a string", "last element", ] 
ary.each do |i| 
	puts i 
end
```

### Hashes 

Hashes behave like maps in Java.

```ruby
hsh = colors = { "red" => 0xf00, "green" => 0x0f0, "blue" => 0x00f } 
hsh.each do |key, value|
	print key, " is ", value, "\n" 
end
```

### Ranges

Ranges express a range of numbers

```ruby
(10..15).each do |n| 
	print n, ' ' 
end
```


## Operators

### Arithmatic Operators

- `**` : Operator for exponentiation. Similar to `Math.pow()` .

### Logical Operators

- `<=>` : Combined comparison operator. Returns 0 if first operand equals second, 1 if first operand is greater than the second and -1 if first operand is less than the second.
  
	Example: `10 <=> 20` returns `-1` .

- `.eql?` : True if the receiver and argument have both the same type and equal values.

	Example: `1 == 1.0` returns true, but `1.eql?(1.0)` is false.

- `equal?` : True if the receiver and argument have the same object id.

	Example: if aObj is duplicate of bObj then aObj == bObj is true, 
	a.equal? bObj is false
	but a.equal? aObj is true.

### Parallel Assignment

This assigning of variables can be replaced by a single line using parallel assignment.

```ruby
a = 10
b = 20
c = 30

# The below is equivalent to above

a, b, c = 10, 20, 30
```