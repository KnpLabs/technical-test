# Technical test

The goal of these exercises is to allow a reflexion about choosen solutions and to discuss between us during the technical interview. There is not only ONE correct solution.

## First exercise : Binary chop

> A binary chop (sometimes called the more prosaic binary search) finds the position of value in a sorted array of values.
> It achieves some efficiency by halving the number of items under consideration each time it probes the values: in the
> first pass it determines whether the required value is in the top or the bottom half of the list of values.
> In the second pass in considers only this half, again dividing it in to two. It stops when it finds the value it is
> looking for, or when it runs out of array to search.
> -- <cite>http://codekata.com/kata/kata02-karate-chop/</cite>

Write a binary search function that takes an integer search target and a sorted array of integers. It should return the integer index of the target in the array, or -1 if the target is not in the array.

The signature will logically be:

```bash
binaryChop(int, array_of_int)  -> int
```

Here is the Test::Unit code. The tests assume that array indices start at zero. You’ll probably have to do a couple of global search-and-replaces to make this compile in your language of choice (unless your enlightened choice happens to be Ruby).

```ruby
def test_knpFunction
  assert_equal(-1, knpFunction(3, []))
  assert_equal(-1, knpFunction(3, [1]))
  assert_equal(0,  knpFunction(1, [1]))
  #
  assert_equal(0,  knpFunction(1, [1, 3, 5]))
  assert_equal(1,  knpFunction(3, [1, 3, 5]))
  assert_equal(2,  knpFunction(5, [1, 3, 5]))
  assert_equal(-1, knpFunction(0, [1, 3, 5]))
  assert_equal(-1, knpFunction(2, [1, 3, 5]))
  assert_equal(-1, knpFunction(4, [1, 3, 5]))
  assert_equal(-1, knpFunction(6, [1, 3, 5]))
  #
  assert_equal(0,  knpFunction(1, [1, 3, 5, 7]))
  assert_equal(1,  knpFunction(3, [1, 3, 5, 7]))
  assert_equal(2,  knpFunction(5, [1, 3, 5, 7]))
  assert_equal(3,  knpFunction(7, [1, 3, 5, 7]))
  assert_equal(-1, knpFunction(0, [1, 3, 5, 7]))
  assert_equal(-1, knpFunction(2, [1, 3, 5, 7]))
  assert_equal(-1, knpFunction(4, [1, 3, 5, 7]))
  assert_equal(-1, knpFunction(6, [1, 3, 5, 7]))
  assert_equal(-1, knpFunction(8, [1, 3, 5, 7]))
end
```

## Second exercise

Write unit tests you seem necessary for this particular function :

```javascript
  const italianGuy = (number) => {
    let n1 = 0
    let n2 = 1
    let sum = 0

    for (let i = 2; i <= number; i++){
      sum = n1 + n2
      n1 = n2
      n2 = sum
    }

    return number ? n2 : n1
  }
```
