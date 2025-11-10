# Chapter 4: Base-16 (Hexadecimal) — Programmer's Best Friend

## Introduction: When Numbers Need Letters

Quick question: What comes after 9?

If you answered "10," you're thinking in base-10. If you answered "A," congratulations—you're thinking in hexadecimal, and you might be a programmer.

Hexadecimal (often abbreviated as "hex") is base-16, which means it uses **sixteen** different digits. But here's the problem: we only have ten numeral symbols (0-9). So hexadecimal does something audacious: it recruits letters.

The hexadecimal digits are: **0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F**

Yes, those are letters. Yes, they count as numbers in this system. No, it's not as weird as it sounds once you get used to it.

A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.

And then after F comes 10₁₆ (which equals sixteen in decimal).

Hexadecimal is the dominant number system in programming (after decimal, obviously). It's how we represent:
- Memory addresses
- Color codes
- Binary data
- Error codes
- Cryptographic hashes
- MAC addresses

If you've ever seen something like `#FF5733` (a color), `0xDEADBEEF` (a programmer meme), or `192.168.0.1:8080` (an IP address with a port), you've encountered hexadecimal.

This chapter will make hex your friend. By the end, you'll see `FF` and think "255" without hesitation. You'll understand why programmers love it, and you might even start thinking "that's such a nice round number" when you see `0x100`.

## Why Base-16?

Remember from the previous chapter: octal (base-8) was popular because each octal digit represents 3 binary bits. Hexadecimal is popular because **each hex digit represents exactly 4 binary bits**.

And 4 bits is special because:
- 8 bits = 1 byte = 2 hex digits (perfect!)
- 16 bits = 2 bytes = 4 hex digits
- 32 bits = 4 bytes = 8 hex digits
- 64 bits = 8 bytes = 16 hex digits

Modern computers are byte-oriented. Everything is stored in bytes (8-bit chunks). Hexadecimal maps perfectly to this architecture. Want to represent a byte? Use exactly two hex digits: 00 to FF.

This makes hex invaluable for:
- **Reading memory dumps**: Instead of 11111111 (binary) or 377 (octal), you write FF
- **Specifying colors**: Instead of "red=255, green=87, blue=51", you write #FF5733
- **Expressing large binary values compactly**: 0xFFFFFFFF instead of 11111111111111111111111111111111

Hexadecimal is the Goldilocks base: not too verbose (like binary), not too disconnected from binary (like decimal), just right.

## The Hexadecimal Digits

Let's establish the hex alphabet with its decimal equivalents:

```
Hex    Decimal    Binary
 0        0        0000
 1        1        0001
 2        2        0010
 3        3        0011
 4        4        0100
 5        5        0101
 6        6        0110
 7        7        0111
 8        8        1000
 9        9        1001
 A       10        1010
 B       11        1011
 C       12        1100
 D       13        1101
 E       14        1110
 F       15        1111
```

**Memorize this table.** Seriously. You need to know that A = 10, B = 11, etc., as instinctively as you know 5 + 5 = 10.

The letters are always uppercase in formal contexts (A, not a), though programmers are lazy and often use lowercase. Both are acceptable; consistency matters more than case.

## Counting in Hexadecimal

Let's count from 0 to 32 in hex:

```
Decimal    Hex
  0         0
  1         1
  2         2
  3         3
  4         4
  5         5
  6         6
  7         7
  8         8
  9         9
 10         A
 11         B
 12         C
 13         D
 14         E
 15         F
 16        10    ← rollover!
 17        11
 18        12
 19        13
 20        14
 21        15
 22        16
 23        17
 24        18
 25        19
 26        1A
 27        1B
 28        1C
 29        1D
 30        1E
 31        1F
 32        20
```

The pattern: count 0-9, then A-F, then roll over to 10₁₆.

After 1F comes 20. After 2F comes 30. After FF comes 100₁₆ (which is 256₁₀).

## Place Value in Hexadecimal

Place values in hexadecimal are powers of 16:

```
... 16⁴    16³    16²   16¹   16⁰
    65536  4096   256   16    1
```

Let's decode 3A7₁₆:

```
  3     A     7
  ↓     ↓     ↓
16²   16¹   16⁰
256    16     1
```

- 3 × 256 = 768
- A (10) × 16 = 160
- 7 × 1 = 7
- **Total: 768 + 160 + 7 = 935₁₀**

So 3A7₁₆ = 935₁₀

Let's try a more famous hex number: CAFE₁₆ (yes, programmers use food names)

```
  C      A      F      E
  ↓      ↓      ↓      ↓
16³    16²    16¹    16⁰
4096   256     16      1
```

- C (12) × 4096 = 49,152
- A (10) × 256 = 2,560
- F (15) × 16 = 240
- E (14) × 1 = 14
- **Total: 49,152 + 2,560 + 240 + 14 = 51,966₁₀**

So CAFE₁₆ = 51,966₁₀

## Converting Decimal to Hexadecimal

Use successive division by 16, collecting remainders:

**Example 1:** Convert 255₁₀ to hex

```
255 ÷ 16 = 15 remainder 15 (F)
 15 ÷ 16 = 0  remainder 15 (F)
```

Read remainders bottom to top: **FF₁₆**

This makes sense! 255 is the maximum value for a byte, which is exactly FF in hex.

**Example 2:** Convert 1000₁₀ to hex

```
1000 ÷ 16 = 62 remainder 8
  62 ÷ 16 = 3  remainder 14 (E)
   3 ÷ 16 = 0  remainder 3
```

Result: **3E8₁₆**

Verify: (3 × 256) + (14 × 16) + (8 × 1) = 768 + 224 + 8 = 1000₁₀ ✓

**Example 3:** Convert 65535₁₀ to hex

```
65535 ÷ 16 = 4095 remainder 15 (F)
 4095 ÷ 16 = 255  remainder 15 (F)
  255 ÷ 16 = 15   remainder 15 (F)
   15 ÷ 16 = 0    remainder 15 (F)
```

Result: **FFFF₁₆**

That's the maximum value for two bytes (16 bits)—all bits set to 1.

## The Magic: Hexadecimal ↔ Binary Conversion

Just like octal, converting between hex and binary is trivial because 16 = 2⁴. Each hex digit represents exactly four binary bits.

We already saw the conversion table. Let's use it:

### Hexadecimal to Binary: Replace Each Digit with 4 Bits

**Example:** Convert 2F₁₆ to binary

```
  2       F
0010    1111
```

Result: **00101111₂** (or just 101111₂)

**Example:** Convert A3B₁₆ to binary

```
  A       3       B
1010    0011    1011
```

Result: **101000111011₂**

**Example:** Convert DEADBEEF₁₆ to binary (a famous programmer's hex number)

```
  D       E       A       D       B       E       E       F
1101    1110    1010    1101    1011    1110    1110    1111
```

Result: **11011110101011011011111011101111₂**

That's 32 bits (4 bytes), which fits nicely in a 32-bit integer. The hex version is much easier to read!

### Binary to Hexadecimal: Group by Fours from the Right

**Example:** Convert 11010110₂ to hex

```
Group by 4 (from right): 1101 0110
Convert to hex:            D    6
```

Result: **D6₁₆**

**Example:** Convert 111111111₂ to hex

```
Add leading zeros:     0001 1111 1111
Convert to hex:          1    F    F
```

Result: **1FF₁₆** (which is 511₁₀)

This conversion is so easy that programmers do it in their heads all the time. See binary? Group by fours, convert. See hex? Expand to four bits each. Done.

## Common Hex Values to Memorize

Certain hex numbers appear constantly in programming:

```
Decimal    Hex      Significance
  0        0x00     Zero/null
  1        0x01     One
 10        0x0A     Ten (note the A)
 15        0x0F     Half a byte (low nibble full)
 16        0x10     Sixteen
 255       0xFF     Maximum byte value (11111111₂)
 256       0x100    One more than a byte
 4095      0xFFF    12 bits all set
 65535     0xFFFF   Maximum 16-bit value
```

Note the "0x" prefix—that's how most programming languages indicate "this is hexadecimal." The "x" stands for "hexadecimal."

## Hexadecimal Arithmetic: Addition

Addition in hex: carry when you reach 16 (or 10₁₆, if you think in hex).

```
  3A₁₆
+ 2F₁₆
------
```

Rightmost column: A (10) + F (15) = 25₁₀ = 19₁₆
- Write 9, carry 1

Left column: 3 + 2 = 5, plus carried 1 = 6

```
   ₁     (carry)
  3A₁₆
+ 2F₁₆
------
  69₁₆
```

Verify in decimal:
- 3A₁₆ = 58₁₀
- 2F₁₆ = 47₁₀
- 58 + 47 = 105₁₀
- 69₁₆ = (6 × 16) + 9 = 96 + 9 = 105₁₀ ✓

Let's try a harder one:

```
  FF₁₆
+ 01₁₆
------
```

Rightmost: F (15) + 1 = 16₁₀ = 10₁₆
- Write 0, carry 1

Left: F (15) + carried 1 = 16₁₀ = 10₁₆
- Write 10

```
  ₁₁    (carries)
  FF₁₆
+ 01₁₆
------
 100₁₆
```

This makes sense: FF₁₆ = 255₁₀, and 255 + 1 = 256₁₀ = 100₁₆.

## Hexadecimal Arithmetic: Subtraction

Subtraction: borrow 16 when needed.

```
  A5₁₆
- 3C₁₆
------
```

Rightmost: 5 - C (12)? Can't do it. Borrow 16 from the left.
- 15 (5 + 16) - 12 = 3... wait, let me recalculate: 5 + 16 = 21₁₀, 21 - 12 = 9

Wait, that's not right. Let's think in hex:
- 5 - C: Can't do it
- Borrow 1 (which is 16₁₀) from the left position
- 15₁₆ (which is 21₁₀) - C (12₁₀) = 9
- But wait, in hex: 15₁₆ - C = ?

Actually, let's be clearer. When we borrow in hex:
- 5 becomes 15₁₆ (that's 1 × 16 + 5 = 21₁₀)
- 15₁₆ - C₁₆: (21₁₀ - 12₁₀) = 9₁₀ = 9₁₆

Left column: A becomes 9 (after borrowing), 9 - 3 = 6

```
  A5₁₆
- 3C₁₆
------
  69₁₆
```

Verify: A5₁₆ = 165₁₀, 3C₁₆ = 60₁₀, 165 - 60 = 105₁₀ = 69₁₆ ✓

Hex arithmetic is tricky because you need to think in base-16 while your brain wants base-10. Most people just convert to decimal, calculate, and convert back.

## Hexadecimal in Color Codes

One of the most visible uses of hex is in web colors. You've seen things like:

```
#FF0000  (red)
#00FF00  (green)
#0000FF  (blue)
#FFFFFF  (white)
#000000  (black)
#FF5733  (orange-red)
```

The format is `#RRGGBB`:
- First two hex digits: Red intensity (00-FF = 0-255)
- Next two hex digits: Green intensity (00-FF = 0-255)
- Last two hex digits: Blue intensity (00-FF = 0-255)

**Example:** Decode #FF5733

```
FF (red) = 255 (full red)
57 (green) = 87 (moderate green)
33 (blue) = 51 (low blue)
```

Result: A orangish-red color (heavy on red, some green, minimal blue).

**Example:** What color is #00FFFF?

```
00 (red) = 0
FF (green) = 255
FF (blue) = 255
```

Green + Blue = Cyan!

Some common colors:
```
#FF0000 = Red
#00FF00 = Green (or Lime)
#0000FF = Blue
#FFFF00 = Yellow (Red + Green)
#FF00FF = Magenta (Red + Blue)
#00FFFF = Cyan (Green + Blue)
#FFFFFF = White (all colors full)
#000000 = Black (no color)
#808080 = Gray (half of everything)
```

Sometimes you'll see shorthand: `#F00` means `#FF0000`. Each digit is doubled.

## Hexadecimal in Memory Addresses

Computer memory is addressed in bytes. Memory addresses are typically displayed in hex.

Example memory dump:
```
Address     Data
0x00000000  48 65 6C 6C 6F  "Hello"
0x00000005  20 57 6F 72 6C  " Worl"
0x0000000A  64 21 00 00 00  "d!..."
```

Each address is in hex. Each byte of data is shown as a two-digit hex value.

Let's decode 0x00000005's data: `20 57 6F 72 6C`

These are ASCII character codes (in hex):
- 20₁₆ = 32₁₀ = space character
- 57₁₆ = 87₁₀ = 'W'
- 6F₁₆ = 111₁₀ = 'o'
- 72₁₆ = 114₁₀ = 'r'
- 6C₁₆ = 108₁₀ = 'l'

So `20 57 6F 72 6C` spells " Worl".

Hex makes this readable. Imagine if it were binary:
```
00100000 01010111 01101111 01110010 01101100
```

Or decimal:
```
32 87 111 114 108
```

Hex hits the sweet spot: compact but directly convertible to binary.

## Powers of 16: Important Values

Memorize these powers of 16:

```
16⁰  = 1       = 0x1
16¹  = 16      = 0x10
16²  = 256     = 0x100
16³  = 4,096   = 0x1000
16⁴  = 65,536  = 0x10000
```

Notice the pattern in hex: each power of 16 is "1" followed by zeros, just like powers of 10 in decimal!

Also note:
- 0xFF = 255 (16² - 1)
- 0xFFF = 4,095 (16³ - 1)
- 0xFFFF = 65,535 (16⁴ - 1)

All Fs in hex means "all bits set" for that many nibbles (4-bit chunks).

## Nibbles, Bytes, and Words

Some terminology:

- **Bit**: One binary digit (0 or 1)
- **Nibble** (or Nybble): 4 bits = 1 hex digit
- **Byte**: 8 bits = 2 hex digits (0x00 to 0xFF)
- **Word**: Depends on architecture, often 16 bits (2 bytes, 4 hex digits)
- **Dword** (Double Word): 32 bits (4 bytes, 8 hex digits)
- **Qword** (Quad Word): 64 bits (8 bytes, 16 hex digits)

Example:
- Byte: 0x3F
- Word: 0x3F2A
- Dword: 0x3F2A1B4C
- Qword: 0x3F2A1B4C5E6D7A89

## Hexadecimal in MAC Addresses

Network devices have MAC addresses, displayed in hex:

Example: `00:1A:2B:3C:4D:5E`

That's six bytes (48 bits) in hex, separated by colons (or sometimes dashes).

Breaking it down:
- 00₁₆ = 0₁₀
- 1A₁₆ = 26₁₀
- 2B₁₆ = 43₁₀
- 3C₁₆ = 60₁₀
- 4D₁₆ = 77₁₀
- 5E₁₆ = 94₁₀

Why hex? Because MAC addresses are 48 bits, which is exactly 12 hex digits (or 6 bytes). Hex is the natural representation.

## Hex in Cryptography: Hashes

Cryptographic hashes are often displayed in hex.

Example SHA-256 hash:
```
a94a8fe5ccb19ba61c4c0873d391e987982fbbd3
```

That's 40 hex digits = 20 bytes = 160 bits. (Actually, that's SHA-1, which is 160 bits. SHA-256 would be 64 hex digits.)

Why hex? Because the hash output is binary data (random-looking bits), and hex is the most compact human-readable way to display it.

## Famous Hex Numbers in Programming

Programmers love embedding words in hex numbers using the digits 0-9 and A-F. Some classics:

- **0xDEADBEEF**: "Dead beef" — used as a debugging value
- **0xCAFEBABE**: "Cafe babe" — Java class file magic number
- **0xFEEDFACE**: "Feed face" — used in various file formats
- **0xBADCAFFE**: "Bad caffe" — seen in some error codes
- **0xC0FFEE**: "Coffee" — because programmers
- **0xDECAFBAD**: "Decaf bad" — because programmers really love coffee
- **0xFACE**: "Face"
- **0xBEEF**: "Beef"
- **0xFEED**: "Feed"

Available letters: A, B, C, D, E, F. You can also use 0 as O, 1 as I/L, 3 as E, 5 as S. With creativity, you can spell many words.

## Mental Conversion Tricks

**Hex to Decimal (small numbers):**
Use Horner's method (multiply by 16, add next digit):

Example: 2A3₁₆
- 2 × 16 = 32
- 32 + 10 (A) = 42
- 42 × 16 = 672
- 672 + 3 = 675₁₀

**Decimal to Hex (small numbers):**
Think in powers of 16:
- Does it have 16s? How many?
- What's left over?

Example: 100₁₀
- 100 ÷ 16 = 6 remainder 4
- So 6 sixteens and 4 ones = 64₁₆

**Binary ↔ Hex:**
Just group by fours. This should become instant with practice.

## When to Use Hexadecimal

**Use hex when:**
- Representing binary data compactly
- Working with memory addresses
- Specifying colors (#RGB)
- Reading error codes
- Debugging low-level code
- Displaying byte arrays

**Don't use hex when:**
- Doing everyday math (use decimal)
- Communicating with non-technical people
- The context doesn't relate to binary/bytes

Hexadecimal is a tool for technical contexts where you're working close to the hardware or need compact binary representation.

## Conclusion: The Universal Programmer's Language

If you work with computers at a technical level, hexadecimal is inescapable. It's the lingua franca of bits and bytes, the notation that bridges human readability and binary reality.

Mastering hex means:
- You can read memory dumps
- You understand color codes intuitively
- You can debug at a lower level
- You speak the same language as hardware

Hexadecimal might seem weird at first—using letters as numbers, counting to F before rolling over—but it's actually elegant. It maps perfectly to binary (4 bits per digit) and to bytes (2 digits per byte), making it the ideal notation for modern computing.

Plus, you can now appreciate the humor in 0xDEADBEEF. That alone is worth the learning curve.

In our next chapter, we'll explore something completely different: base-12, the duodecimal system. Unlike binary, octal, and hex, which exist to serve computers, duodecimal emerged from human needs—specifically, the need to divide things by 2, 3, 4, and 6 without getting messy fractions.

We're leaving the world of computer science and entering the world of ancient mathematics, commerce, and surprisingly practical everyday measurement.

---

**Coming Up Next:** Chapter 5 - Duodecimal (Base-12): Ancient Wisdom (where we discover why Mesopotamians were onto something)
