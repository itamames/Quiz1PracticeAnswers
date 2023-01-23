# Quiz1PracticeAnswers

1. (a) O(n), indexOf must search entire string potentially
   (b) O(1), equals will either find the lengths are different or
    it finds the first characters different (either answer is ok)

2. (a) O(n<sup>2</sup>) - outer loop: n times, inner loop: n/2 times, n*n/2 = O(n<sup>2</sup>)
   (b) O(n) - outer loop: 50 times, inner loop: n/3 times, 50 n/3 = O(n)
   (c) O(m log n)
      * outer loop: m times
      * inner loop: log<sub>2</sub>n times
      * m * log2 n = O(m log n)


   (d) O(m<sup>2</sup> 
      * first loop: m<sup>2</sup> times
      * second loop: m times.  
      * m<sup>2</sup> + m =O(m<sup>2</sup>)

3. (a) O(n). There are n-1 adjacent pairs to test in worst case.
   (b) O(1). a[0] and a][1] might be equal causing method to return
   after first comparison.

4. (a) 
      * Number of operations when n=8: 8<sup>2</sup> = 64
      * Number of operations when n=16: 16<sup>2</sup> = 256
      * Number of additional operations: 256-64=192

   (b) 
      * Number of operations when n=8: log<sub>2</sub> 8 = 3
      * Number of operations when n=16: log<sub>2</sub> 16 = 4
      * Number of additional operations: 4-3=1

   (c) 
      * Number of operations when n=8: 2<sup>8</sup> = 256
      * Number of operations when n=16: 2<sup>16</sup> = 65536
      * Number of additional operations: 65536-256=65280


5. (a) O(n<sup>2</sup>). When i=1, 1 sum is computed, when i=2, 2 sums are
   computed, when i=3, 3 sums are computed,...

   Total number of sums computed = 1 + 2 + ... + (n-1) = n(n-1)/2 = O(n<sup>2</sup>)

   (b) Two possibilities:

   * Start with i = 0 and j = length-1.
   * Compute total = a[i] + a[j].
   * If total > sum, then subtract 1 from j
      * otherwise add 1 to i.
   * Repeat until you find the correct sum or i == j.
   
      * --> This is O(n) since you always subtract 1 from j or add 1 to i
   so the difference between i and j must decrease by 1 each iteration
   until it reaches 0 after n iterations.

   OR

   For each a[i], use binary search to find sum-a[i].
   * --> This is O(n log n) since each search is logarithmic, and you
   do the search once for each value in the array.

6. (a) 
   Formal definition states that for function to be O(n^2), we must
   find some c > 0 and n0 > 0 such that c*n<sup>2</sup> > 6n<sup>2</sup> + 15n + 75, for all n > n0.

   * Find intersection point at n0 by setting both sides equal to each other.
   
      c*n0<sup>2</sup> = 6n0<sup>2</sup> + 15n0 + 75
   
   * Divide by n0<sup>2</sup>

      c = 6 + 15/n0 + 75/n0<sup>2</sup>
   * Pick a value for n0 > 0, then solve for c.
      * Any positive value of n0 will do. I chose n0 = 5:

         c = 6 + 3 + 3 = 12

   * This means that 12n<sup>2</sup> > 6n<sup>2</sup> + 15n + 75 for n > 5.
   Thus 6n<sup>2</sup> + 15n + 75 = O(n<sup>2</sup>).

   (b) 
   Since c*n<sup>3</sup> grows faster than c*n<sup>2</sup>, n<sup>3</sup> will always be an upper-bound
   for T(n) for n > n0.  So T(n) = O(n<sup>3</sup>) also.

   (c) 
   Since c*n does not grow faster than c*n<sup>2</sup>, there will be some point where T(n) will grow larger than c*n, no matter what c we use.

   Another way to put it, as n and T(n) grow, since T(n) is quadratic and n is linear, the straight line can't always stay above the T(n) since T(n)
   grows at a faster rate.  So T(n) cannot be O(n).
   
