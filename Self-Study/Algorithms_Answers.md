1a. At it's most basic, the while loop would make this an O(n) runtime. Given it would only run 4 times due to the way exponents increase, one might argue it could be O(c), but let's not go there.
    example:
        initializes as a = 0, n = 3
        first pass: a = 9, n^3 = 27
        second pass: a = 18, n^3 = 27
        third pass: a = 27, n^ 27
        fourth pass: a = 36, n^3 = 27

1b. This would be O(n^4) due to the 4 deep nest of for loops going on. The inner most loop could potentially shave some time off due to it's range being (3, 13) to start, but nothing that I think wouldn't result in something significant.

1c. As written, this would be an O(c) due to crashing on the first recursion attempt because bunnyEars != bunnieEars. In the spirit in which this was written though, I believe this would be an O(n), as we don't have anything particularly exciting going with what basically amounts to the recursive version of a loop and an adder.
def bunnieEars(bunnies):
    if bunnies == 0:
        return 0

    return 2 + bunnyEars(bunnies-1)

bunnyEars(2) -> 2 + bunnyEars(1) -> 2 + bunnyEars(0) -> 0 = 4

2. We could tackle this problem in a similar manner to a binary search, where we start dropping eggs from floor n // 2, then if it does break, we take the sublist of the lower half of the building, drop one from it's middle, etc, etc. If the egg does not break from the original n // 2, we take the sublist of the upper half of floors, drop the egg from the middle room of that, then choose the next floor depending on the result. This would result in an O(log n) runtime due to the halving of the data set with each successive attempt.
