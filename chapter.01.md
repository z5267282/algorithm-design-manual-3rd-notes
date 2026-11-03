# chapter 01.

## finding counterexamples

### 1.1.

Negative numbers when added will get smaller.

```txt
a = -1, b = -2

a + b = -1 + (-2)
      = -3
      < min(-1, -2)
      < -2
```

### 1.2.

Change the sign of `a * b` and `min(a, b)`.

```txt
a = -1, b = 2

a * b = -1 * 2
      = -2
      < min(-1, 2)
      < -1
```

### 1.3.

Start from `t = d / s` and work from there. We want to try make a longer and
faster road faster than a shorter but slower road. Suppose there are two roads:
the Hume motorway and Parramatta road.

```txt
dist(hume) = 2 * dist(parra)
speed(hume) = 4 * speed(parra)

time(hume) = 2 * dist(parra) / 4 speed(parra)
           = dist(parra) / 2 * speed(parra)
           = 0.5 * (dist(parra) / speed(parra))
           = 0.5 * time(parra)
```

### 1.5.

#### 1.5.a.

Design a sack where you need to skip over a sequential item that fits e.g.

```txt
T=10, S={1,8,4,5}

algo:{1,8}
need:{1,4,5}
```

#### 1.5.b.

Design a sack where the largest items form the only solution e.g.

```txt
T=15, S={1,2,3,7,8}

algo:{1,2,3,7}
need:{7,8}
```

#### 1.5.c.

Flip part b. and design a sack where the smallest items form the only solution
e.g.

```txt
T=9, S={4,5,7}

algo:{7}
need:{4,5}
```

### 1.6.

Go for a tie: how do you pick when there are two largest subsets for the cover?

```txt
U5={1,2,3,4,5}

S1={1,3,5}
S2={1,4}
S3={2,3,5}
```

The answer is `{S3,S2}`. `S1` and `S3` both cover three elements but if you
pick `S1` you will be forced to pick `S2` and `S3` afterwards because there is
no single subset with the elements missing: 4 and 5.

## interview problems

### 1.32.

Keep adding the divisor until you hit the dividend and track the number of
iterations as the quotient. The faster way is using bit manipulation.

### 1.33.

Put all horses in groups say A to E. Race all groups and create these
orderings.

```txt
A1 A2 A3 A4 A5
B1 B2 B3 B4 B5
C1 C2 C3 C4 C5
D1 D2 D3 D4 D5
E1 E2 E3 E4 E5
```

Race all the first place horses.

```txt
A1 B1 C1 D1 E1
```

Suppose that creates the ordering. If it doesn't just change the letters of the
groups to make this ordering.

```
a b c d e
```

The fastest horse is a. The second fastest cannot be any horse in group E.
They are all slower than their group leader e who is also slower than d.

```txt
d > e > E2 > E3 > E4 > E5
```

Make a symmetric argument for group D

```txt
c > d > D2 > D3 > D4 > D5
```

The second and third horses could have come from group A but A3 is already
faster than A4 and A5 so they are definitely not contenders. You can make the
same argument

```txt
A1 A2 A3
B1 B2 B3 B4 B5
C1 C2 C3 C4 C5
```
