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

Race all horces in groups of 5 and get orderings `G(group,place)`.

```txt
G(1,1) > G(1,2) > G(1,3) > G(1,4) > G(1,5)
G(2,1) > G(2,2) > G(2,3) > G(2,4) > G(2,5)
G(3,1) > G(3,2) > G(3,3) > G(3,4) > G(3,5)
G(4,1) > G(4,2) > G(4,3) > G(4,4) > G(4,5)
G(5,1) > G(5,2) > G(5,3) > G(5,4) > G(5,5)
```

Race all horses that finished first.

```txt
G(1,1), G(2,1), G(3,1), G(4,1), G(5,1)
```

The winner of that race is the fastest horse and note the group of the winner
`W`.

The second fastest horse either came from `W` or another group. If it came from
another group it definitely did not beat its group winner. If it came from the
winning group then it would have been the next fastest horse so `G(W,2)`.

So we need to race `G(W,2)` and the remaining 4 `G(L,1)`s for all losing groups
`L`. The winner of that race is the second fastest horse.
