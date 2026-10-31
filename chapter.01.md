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

### 1.4.

A trivial question if you defy geography e.g.

```txt
a -> b: 100km

a -> c: 1km
c -> b: 1km

then a->c->b = 2km whereas a->b = 100km
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
