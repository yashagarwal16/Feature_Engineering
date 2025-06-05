
# 🔢 What is Ordinal Encoding?

**Ordinal Encoding** means turning categories (words) into numbers **based on their order**.

We use it when the categories have a clear ranking or sequence.

---

## Example: Education Level

Imagine these education levels:

```

High School < Bachelor < Master < PhD

```

We can assign numbers like this:

| Education Level | Number |
|-----------------|--------|
| High School     | 0      |
| Bachelor        | 1      |
| Master          | 2      |
| PhD             | 3      |

Now, the computer knows "PhD" is higher than "Master," which is higher than "Bachelor," and so on.

---

## Visual Representation:

| High School | Bachelor | Master | PhD |
|:-----------:|:--------:|:------:|:---:|
|     0       |    1     |   2    |  3  |

⬇️

| 0 | 1 | 2 | 3 |

This shows how each level is mapped to a number representing its order.

---

## When NOT to use Ordinal Encoding

If the categories don’t have any order, don’t use it.

For example:

```

Red, Green, Blue

```

Assigning numbers like 0, 1, 2 here is wrong because these colors don’t have a ranking.

For such data, use **One-Hot Encoding** instead.

---

## Quick Summary

- Use Ordinal Encoding for things with order (like education levels or sizes: small, medium, large).
- Don’t use it for things without order (like colors or countries).
```
