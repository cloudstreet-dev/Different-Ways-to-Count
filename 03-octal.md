# Chapter 3: Base-8 (Octal) — The Forgotten Middle Child

## Introduction: The In-Between Number System

Octal is the Jan Brady of number systems.

You've got binary—the fundamental language of computers, beloved by hardware engineers. You've got hexadecimal (coming next chapter)—the favorite of programmers everywhere, with its cool letters and efficient notation. And then you've got octal, sitting between them, occasionally useful, largely forgotten, muttering "Binary, binary, binary!" in frustration.

But octal has its moments. In the 1960s and 70s, before hexadecimal took over, octal was THE shorthand for binary. It still lingers in Unix file permissions, some programming contexts, and the occasional nostalgic coder's heart. Plus, it's mathematically elegant in its own right—a perfect stepping stone between binary and hexadecimal.

And here's a fun fact: if humans had evolved with eight fingers instead of ten (maybe we lost a finger in each hand to evolution, who knows), octal might have been our natural counting system, and we'd think base-10 was weird.

Welcome to base-8, where the numbers go 0, 1, 2, 3, 4, 5, 6, 7... and then 10.

## What Is Octal?

Octal (base-8) uses eight digits: **0, 1, 2, 3, 4, 5, 6, 7**

That's it. The digit "8" doesn't exist in octal, just like "2" doesn't exist in binary. When counting in octal, after 7 comes 10₈ (which equals eight in decimal).

The place values in octal are powers of 8:
- Rightmost place: 8⁰ = 1
- Next left: 8¹ = 8
- Next left: 8² = 64
- Next left: 8³ = 512
- Next left: 8⁴ = 4,096

Each position is worth **8 times** the position to its right.

## Why Octal Exists: It's All About Binary

Octal's main purpose is to be a shorthand for binary. Here's why that's useful:

Binary numbers get long fast. Look at this:
```
11010110101101110₂
```

Try reading that aloud. Try memorizing it. Try writing it without making a mistake. It's painful.

But here's the magic: **each octal digit represents exactly 3 binary digits**.

```
Binary:  011  010  110  101  101  110
Octal:    3    2    6    5    5    6
```

So 11010110101101110₂ = 326556₈

Much easier to read, write, and remember! And converting between octal and binary is trivial—you just group or ungroup by threes.

### Why Not Just Use Decimal?

Good question! Why invent octal when we already have decimal?

Because converting between binary and decimal is hard. There's no simple pattern. But converting between binary and octal? It's mechanical—just group by threes.

Compare:
- Binary ↔ Octal: Group by 3, done
- Binary ↔ Decimal: Division, remainders, powers of 2, addition... pain

Octal emerged as a convenient middle ground: more compact than binary, trivial to convert to/from binary.

## Counting in Octal

Let's count from 0 to 30 in octal and see the pattern:

```
Decimal    Octal
  0         0
  1         1
  2         2
  3         3
  4         4
  5         5
  6         6
  7         7
  8        10   ← rollover!
  9        11
 10        12
 11        13
 12        14
 13        15
 14        16
 15        17
 16        20   ← rollover again
 17        21
 18        22
 19        23
 20        24
 21        25
 22        26
 23        27
 24        30   ← rollover
```

The pattern: count 0-7, then roll over to 10₈. Count to 17₈, roll over to 20₈. Just like counting in base-10, but rolling over at 8 instead of 10.

## Place Value in Octal

Let's decode the octal number 3527₈:

```
  3     5     2     7
  ↓     ↓     ↓     ↓
 8³    8²    8¹    8⁰
512    64     8     1
```

To convert to decimal:
- 3 × 512 = 1,536
- 5 × 64 = 320
- 2 × 8 = 16
- 7 × 1 = 7
- **Total: 1,536 + 320 + 16 + 7 = 1,879₁₀**

So 3527₈ = 1879₁₀

Let's try another: 177₈

```
  1     7     7
  ↓     ↓     ↓
 8²    8¹    8⁰
 64     8     1
```

- 1 × 64 = 64
- 7 × 8 = 56
- 7 × 1 = 7
- **Total: 64 + 56 + 7 = 127₁₀**

So 177₈ = 127₁₀

Notice 177₈ has all 7s in the last two digits—it's the largest number you can represent with two octal digits (7 × 8 + 7 = 63), plus one more eight.

## Converting Decimal to Octal

Like binary, we can use successive division, but divide by 8 instead of 2.

**Example 1:** Convert 83₁₀ to octal

```
83 ÷ 8 = 10 remainder 3
10 ÷ 8 = 1  remainder 2
 1 ÷ 8 = 0  remainder 1
```

Read remainders bottom to top: **123₈**

Verify: (1 × 64) + (2 × 8) + (3 × 1) = 64 + 16 + 3 = 83₁₀ ✓

**Example 2:** Convert 1000₁₀ to octal

```
1000 ÷ 8 = 125 remainder 0
 125 ÷ 8 = 15  remainder 5
  15 ÷ 8 = 1   remainder 7
   1 ÷ 8 = 0   remainder 1
```

Result: **1750₈**

Verify: (1 × 512) + (7 × 64) + (5 × 8) + (0 × 1) = 512 + 448 + 40 + 0 = 1000₁₀ ✓

## The Magic: Octal ↔ Binary Conversion

This is where octal shines. Converting between octal and binary is stupidly easy because 8 = 2³. Each octal digit represents exactly three binary digits.

### Octal to Binary: Replace Each Digit with 3 Bits

Each octal digit (0-7) maps to a 3-bit binary pattern:

```
Octal    Binary
  0       000
  1       001
  2       010
  3       011
  4       100
  5       101
  6       110
  7       111
```

Memorize this table. It's only 8 entries, and the pattern is just counting in binary from 0 to 7.

**Example:** Convert 352₈ to binary

```
  3      5      2
 011    101    010
```

Result: **011101010₂**

(You can drop the leading zero: 11101010₂)

**Example:** Convert 1750₈ to binary

```
  1      7      5      0
 001    111    101    000
```

Result: **001111101000₂** or **1111101000₂**

That's it! No calculation needed. Just replace each octal digit with its 3-bit equivalent.

### Binary to Octal: Group by Threes from the Right

Going the other way is equally simple:
1. Start from the rightmost bit
2. Group bits in sets of three
3. Convert each group to its octal digit

**Example:** Convert 11010110₂ to octal

```
Group by 3 (from right): 11 010 110
Add leading zero:       011 010 110
Convert to octal:         3   2   6
```

Result: **326₈**

**Example:** Convert 1111101000₂ to octal

```
Group by 3: 001 111 101 000
Convert:     1   7   5   0
```

Result: **1750₈**

This is why octal was popular in early computing. Assembly programmers could mentally convert between binary and octal instantly, making code easier to read and debug.

## Octal Arithmetic: Addition

Addition in octal follows the same pattern as other bases: carry when you reach or exceed 8.

```
  365₈
+ 427₈
------
```

Rightmost column: 5 + 7 = 12₁₀ = 14₈
- Write 4, carry 1

Middle column: 6 + 2 = 8, plus carried 1 = 9₁₀ = 11₈
- Write 1, carry 1

Left column: 3 + 4 = 7, plus carried 1 = 8₁₀ = 10₈
- Write 10

```
  ₁₁    (carries)
  365₈
+ 427₈
------
 1014₈
```

**Result: 1014₈**

Verify in decimal:
- 365₈ = (3×64) + (6×8) + (5×1) = 192 + 48 + 5 = 245₁₀
- 427₈ = (4×64) + (2×8) + (7×1) = 256 + 16 + 7 = 279₁₀
- 245 + 279 = 524₁₀
- 1014₈ = (1×512) + (0×64) + (1×8) + (4×1) = 512 + 0 + 8 + 4 = 524₁₀ ✓

### Mental Math Trick

When adding octal, remember:
- 7 + 1 = 10₈
- 6 + 2 = 10₈
- 5 + 3 = 10₈
- 4 + 4 = 10₈

Any sum ≥ 8 means subtract 8 and carry 1.

## Octal Arithmetic: Multiplication

Multiplication in octal requires an octal multiplication table. This is where octal starts to get tedious—you have to learn a new times table.

```
Octal multiplication table (partial):
  3 × 4 = 14₈  (12₁₀)
  5 × 6 = 36₈  (30₁₀)
  7 × 7 = 61₈  (49₁₀)
```

Let's multiply 24₈ × 3₈:

```
  24₈
×  3₈
-----
```

- 4 × 3 = 12₁₀ = 14₈ (write 4, carry 1)
- 2 × 3 = 6, plus carried 1 = 7

Result: **74₈**

Verify: 24₈ = 20₁₀, 3₈ = 3₁₀, 20 × 3 = 60₁₀ = 74₈ ✓

Honestly? Most people convert to decimal, multiply, and convert back. Octal multiplication tables are not commonly memorized anymore.

## Octal in Unix File Permissions

The most common place you'll see octal today is Unix/Linux file permissions.

When you see:
```
chmod 755 filename
```

That 755 is octal! Each digit represents permissions for a different group:
- First digit (7): Owner permissions
- Second digit (5): Group permissions
- Third digit (5): Others permissions

Each octal digit represents 3 binary bits (permission flags):
- Bit 1 (4): Read permission
- Bit 2 (2): Write permission
- Bit 3 (1): Execute permission

```
7₈ = 111₂ = read(4) + write(2) + execute(1) = all permissions
5₈ = 101₂ = read(4) + execute(1) = read and execute only
0₈ = 000₂ = no permissions
```

So `chmod 755` means:
- Owner: read, write, execute (7)
- Group: read, execute (5)
- Others: read, execute (5)

Other common permission combinations:
- 644: rw-r--r-- (files: owner can edit, others can read)
- 755: rwxr-xr-x (programs: owner can edit/run, others can run)
- 777: rwxrwxrwx (everyone can do everything—usually bad security!)
- 600: rw------- (only owner can read/write—good for private keys)

The octal notation is compact and unambiguous. It's easier to type `chmod 755` than `chmod u=rwx,g=rx,o=rx`.

## Octal in Programming

Many programming languages support octal literals, usually with a leading zero:

```c
int x = 0755;  // Octal 755 = 493₁₀
```

**Warning:** This causes bugs! Look at this code:

```c
int day = 08;  // ERROR! 8 is not a valid octal digit
int month = 09;  // ERROR! 9 is not a valid octal digit
```

Trying to use leading zeros for "pretty formatting" can break if the number contains 8 or 9. Many modern style guides forbid leading zeros (except for a literal 0) because of this ambiguity.

Python 2 used leading zeros for octal:
```python
x = 0755  # Octal in Python 2
```

Python 3 requires explicit notation:
```python
x = 0o755  # Octal in Python 3
```

The "0o" prefix makes it clear: "zero-oh for octal."

## Why Hexadecimal Defeated Octal

If octal is such a nice shorthand for binary, why don't we use it more?

**Computer word sizes.**

Early computers (1960s) had 12-bit, 18-bit, and 36-bit words. These divide evenly by 3, making octal perfect:
- 12 bits = 4 octal digits
- 18 bits = 6 octal digits
- 36 bits = 12 octal digits

But modern computers settled on powers of 2:
- 8 bits = 1 byte
- 16 bits = 2 bytes
- 32 bits = 4 bytes
- 64 bits = 8 bytes

8 bits doesn't divide evenly by 3. We'd need 2.666... octal digits to represent a byte. Ugly.

But 8 bits divides perfectly by 4, and each hexadecimal digit (base-16) represents 4 bits. So:
- 8 bits = 2 hex digits
- 16 bits = 4 hex digits
- 32 bits = 8 hex digits
- 64 bits = 16 hex digits

Perfect! Hexadecimal (next chapter) won because it maps cleanly to byte-oriented architectures.

Octal lingers in Unix permissions because those were designed in the 1970s when octal was still common, and changing them now would break billions of scripts and decades of muscle memory.

## Mental Conversion Trick: Octal ↔ Decimal

For small numbers, you can convert octal to decimal mentally:

**Octal to Decimal:**
- Multiply the left digit by 8, add the next digit, repeat

Example: 237₈
- 2 × 8 = 16
- 16 + 3 = 19
- 19 × 8 = 152
- 152 + 7 = 159₁₀

So 237₈ = 159₁₀

This is called Horner's method, and it works for any base.

**Decimal to Octal:**
- Repeatedly divide by 8, collect remainders

We covered this earlier, but it's worth repeating: for mental math, you can often factor out powers of 8.

Example: Convert 100₁₀ to octal
- 100 ÷ 8 = 12 remainder 4
- 12 ÷ 8 = 1 remainder 4
- 1 ÷ 8 = 0 remainder 1
- Result: 144₈

## Practice Problems

**Decimal ↔ Octal:**
1. Convert 64₁₀ to octal
2. Convert 511₁₀ to octal
3. Convert 345₈ to decimal
4. Convert 777₈ to decimal

**Binary ↔ Octal:**
5. Convert 11011101₂ to octal
6. Convert 1111111₂ to octal
7. Convert 476₈ to binary
8. Convert 1234₈ to binary

**Octal Arithmetic:**
9. 234₈ + 567₈ = ?
10. 777₈ + 1₈ = ?

<details>
<summary>Answers</summary>

**Decimal ↔ Octal:**
1. 64₁₀ = 100₈ (exactly 8²)
2. 511₁₀ = 777₈ (8³ - 1)
3. 345₈ = (3×64) + (4×8) + (5×1) = 192 + 32 + 5 = 229₁₀
4. 777₈ = (7×64) + (7×8) + (7×1) = 448 + 56 + 7 = 511₁₀

**Binary ↔ Octal:**
5. 11011101₂ → 011 011 101 → 335₈
6. 1111111₂ → 001 111 111 → 177₈
7. 476₈ → 100 111 110 → 100111110₂
8. 1234₈ → 001 010 011 100 → 1010011100₂

**Octal Arithmetic:**
9. 234₈ + 567₈:
   - 4 + 7 = 11₁₀ = 13₈ (write 3, carry 1)
   - 3 + 6 = 9, +1 = 10₁₀ = 12₈ (write 2, carry 1)
   - 2 + 5 = 7, +1 = 8₁₀ = 10₈ (write 10)
   - Result: 1023₈

10. 777₈ + 1₈ = 1000₈ (just like 999₁₀ + 1 = 1000₁₀)

</details>

## Octal Patterns and Properties

**Pattern 1: Powers of 8**
- 8¹ = 10₈
- 8² = 100₈
- 8³ = 1000₈

Just like in decimal, multiplying by the base adds a zero.

**Pattern 2: All 7s**
- 7₈ = 7₁₀
- 77₈ = 63₁₀ (8² - 1)
- 777₈ = 511₁₀ (8³ - 1)

All 7s in octal equals 8ⁿ - 1 in decimal.

**Pattern 3: Doubling**
In octal, doubling doesn't have the simple "shift left" property of binary, but there's still a pattern:
- 2 × 1₈ = 2₈
- 2 × 2₈ = 4₈
- 2 × 3₈ = 6₈
- 2 × 4₈ = 10₈ (rolls over!)
- 2 × 5₈ = 12₈
- 2 × 6₈ = 14₈
- 2 × 7₈ = 16₈

## When to Use Octal Today

Honest answer? Not often.

**Use octal when:**
- Setting Unix file permissions (`chmod 644`)
- Working with legacy systems from the 1960s-70s
- Certain embedded systems that use 6-bit, 12-bit, or other 3-divisible architectures
- You want to confuse people (April Fools code, maybe?)

**Don't use octal when:**
- You have literally any other choice
- Working with modern byte-oriented data
- Trying to communicate with normal humans

Octal's main value today is educational. It teaches you:
- How positional systems work with different bases
- The relationship between binary and higher bases
- Why some numbering choices persist (Unix permissions)
- Computer history and how standards evolve

## The Octal Joke

Octal walks into a bar. The bartender says, "Sorry, we're base-10 here."

Octal says, "That's okay, I'm 21 anyway."

(21₈ = 17₁₀... still underage. Sorry, Octal.)

## Conclusion: Respect the Middle Child

Octal is the weird artifact of computing history that refuses to fully die. It's not as fundamental as binary, not as practical as hexadecimal, not as intuitive as decimal. But it carved out its niche, and in certain corners of the computing world, it persists.

Understanding octal gives you historical context for why computing evolved the way it did. It shows you how number systems can be purpose-built for specific needs (compact binary representation) and then fade when those needs change (byte-oriented architectures).

Plus, now you can actually understand what `chmod 755` means instead of just copying it from Stack Overflow. That's worth something, right?

In our next chapter, we'll explore hexadecimal—octal's more popular sibling that stole the spotlight and never looked back. Where octal uses 3 bits per digit, hexadecimal uses 4. Where octal stopped at 7, hexadecimal keeps going all the way to... well, F.

Get ready for a number system that uses letters as digits. Things are about to get weird.

---

**Coming Up Next:** Chapter 4 - Hexadecimal: Programmer's Best Friend (where we learn that DEADBEEF is a perfectly valid number)
