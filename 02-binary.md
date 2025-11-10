# Chapter 2: Base-2 (Binary) — The Language of Computers

## Introduction: There Are 10 Types of People

There are 10 types of people in the world: those who understand binary, and those who don't.

Got it? If you're scratching your head, don't worry—you will by the end of this chapter. (Hint: "10" in binary means two, not ten.)

Binary is the most alien-feeling number system you'll encounter in this book. It only uses two digits: 0 and 1. That's it. No 2, no 3, certainly no 9. Just on and off. Yes and no. True and false. One and zero.

And yet, this absurdly simple system powers every computer, smartphone, tablet, smart watch, and digital device you've ever used. Your phone doesn't understand "5." It doesn't comprehend "cat" or "blue" or "LOL." Everything—EVERYTHING—gets translated into binary before your device can process it.

Welcome to the foundation of the digital world.

## Why Binary? (Or: How Electronic Switches Determine Number Systems)

Let's start with the practical question: Why would anyone use a number system with only two digits? It seems needlessly inefficient. Writing "100" in binary when you could write "4" in decimal feels like spelling out every word instead of using shortcuts.

The answer is hardware.

Computers are made of electronic switches—billions of them, actually. Early computers used vacuum tubes; modern computers use transistors. But the principle is the same: these switches have two states:

1. **On** (electricity flowing) = 1
2. **Off** (no electricity) = 0

You could theoretically build a computer that recognizes ten different voltage levels (0V, 1V, 2V... 9V) and thus works in base-10. But here's the problem: electrical signals are noisy. Distinguishing between 2V and 3V reliably, billions of times per second, across varying temperatures and conditions? Good luck.

But distinguishing between "on" and "off"? Between "voltage" and "no voltage"? That's easy. Reliable. Fast. And most importantly, cheap to manufacture.

So computers use binary not because it's theoretically elegant (though it is), but because it maps perfectly to the physics of electronic switches. Binary is what hardware naturally speaks.

## Understanding Binary: Only Two Symbols

In base-10, we have ten digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9.

In binary (base-2), we have two digits: 0, 1.

That's the entire alphabet. When counting in binary, we only use these two symbols. Let's see how counting works:

```
Base-10    Base-2 (Binary)
   0            0
   1            1
   2           10      ← ran out of digits, roll over!
   3           11
   4          100      ← rolled over twice
   5          101
   6          110
   7          111
   8         1000
   9         1001
  10         1010
```

See the pattern? In base-10, we count 0-9 then roll over to 10. In binary, we count 0-1 then roll over to 10₂ (which equals 2₁₀).

Let's break this down carefully, because this is where binary starts to mess with your head.

## Place Value in Binary

Remember from Chapter 1: in any base-b system, place values are powers of b.

In base-10:
- Rightmost place: 10⁰ = 1
- Next place left: 10¹ = 10
- Next place left: 10² = 100

In base-2:
- Rightmost place: 2⁰ = 1
- Next place left: 2¹ = 2
- Next place left: 2² = 4
- Next place left: 2³ = 8
- Next place left: 2⁴ = 16

Each place is worth **double** the place to its right (because we're multiplying by 2 instead of 10).

Let's look at the binary number 1011₂:

```
  1     0     1     1
  ↓     ↓     ↓     ↓
 2³    2²    2¹    2⁰
  8     4     2     1
```

To convert to base-10, multiply each digit by its place value:
- 1 × 8 = 8
- 0 × 4 = 0
- 1 × 2 = 2
- 1 × 1 = 1
- **Total: 8 + 0 + 2 + 1 = 11₁₀**

So 1011₂ = 11₁₀.

Let's try another: 11111₂

```
  1     1     1     1     1
  ↓     ↓     ↓     ↓     ↓
 2⁴    2³    2²    2¹    2⁰
 16     8     4     2     1
```

- 1 × 16 = 16
- 1 × 8 = 8
- 1 × 4 = 4
- 1 × 2 = 2
- 1 × 1 = 1
- **Total: 16 + 8 + 4 + 2 + 1 = 31₁₀**

All those 1s light up every place value. This gives us a useful rule: **n ones in binary equals 2ⁿ - 1 in decimal**.

## The Memorization Shortcut: Powers of 2

To work fluently with binary, memorize these powers of 2:

```
2⁰  = 1
2¹  = 2
2²  = 4
2³  = 8
2⁴  = 16
2⁵  = 32
2⁶  = 64
2⁷  = 128
2⁸  = 256
2⁹  = 512
2¹⁰ = 1,024
2¹¹ = 2,048
2¹² = 4,096
2¹³ = 8,192
2¹⁴ = 16,384
2¹⁵ = 32,768
2¹⁶ = 65,536
```

I'm serious about memorizing these. You don't need to get them all immediately, but at minimum, memorize up to 2¹⁰ = 1,024. These numbers appear CONSTANTLY in computing:

- 2⁸ = 256: Maximum value in a byte (0-255)
- 2¹⁰ = 1,024: The "kilo" in kilobyte (approximately)
- 2¹⁶ = 65,536: Maximum value in two bytes

Once you know these, converting binary to decimal becomes much faster. You just recognize the place values and add them up.

## Converting Binary to Decimal (The Easy Direction)

Converting binary to decimal is straightforward—just add up the place values where there's a 1.

**Example 1:** Convert 10110₂ to decimal

```
  1     0     1     1     0
  ↓     ↓     ↓     ↓     ↓
 2⁴    2³    2²    2¹    2⁰
 16     8     4     2     1
```

We have 1s in positions: 2⁴, 2², and 2¹
- 16 + 4 + 2 = **22₁₀**

**Example 2:** Convert 11010101₂ to decimal

```
  1     1     0     1     0     1     0     1
  ↓     ↓     ↓     ↓     ↓     ↓     ↓     ↓
 2⁷    2⁶    2⁵    2⁴    2³    2²    2¹    2⁰
128    64    32    16     8     4     2     1
```

We have 1s in positions: 2⁷, 2⁶, 2⁴, 2², and 2⁰
- 128 + 64 + 16 + 4 + 1 = **213₁₀**

See? Once you know the powers of 2, it's just addition.

## Converting Decimal to Binary (The Harder Direction)

Converting the other way—decimal to binary—is trickier. There are two main methods:

### Method 1: Successive Division by 2

Divide the decimal number by 2 repeatedly. The remainders, read backwards, give you the binary representation.

Let's convert 22₁₀ to binary:

```
22 ÷ 2 = 11 remainder 0
11 ÷ 2 = 5  remainder 1
 5 ÷ 2 = 2  remainder 1
 2 ÷ 2 = 1  remainder 0
 1 ÷ 2 = 0  remainder 1
```

Read the remainders from bottom to top: **10110₂**

Why does this work? Because we're literally asking "is this number odd or even?" at each step. If it's odd, we need a 1 in that binary place; if it's even, we need a 0. By dividing by 2 repeatedly, we're separating out each binary digit.

Let's try 213₁₀:

```
213 ÷ 2 = 106 remainder 1
106 ÷ 2 = 53  remainder 0
 53 ÷ 2 = 26  remainder 1
 26 ÷ 2 = 13  remainder 0
 13 ÷ 2 = 6   remainder 1
  6 ÷ 2 = 3   remainder 0
  3 ÷ 2 = 1   remainder 1
  1 ÷ 2 = 0   remainder 1
```

Reading backwards: **11010101₂** ✓

### Method 2: Subtraction (Faster Once You Know Powers of 2)

Find the largest power of 2 that fits into your number, mark a 1, subtract it, and repeat.

Let's convert 22₁₀ to binary:

- Largest power of 2 ≤ 22 is 16 (2⁴)
  - Put a 1 in the 2⁴ place
  - 22 - 16 = 6 remaining

- Largest power of 2 ≤ 6 is 4 (2²)
  - Put a 1 in the 2² place
  - 6 - 4 = 2 remaining

- Largest power of 2 ≤ 2 is 2 (2¹)
  - Put a 1 in the 2¹ place
  - 2 - 2 = 0 remaining

- We used: 2⁴, 2², 2¹
- We didn't use: 2³, 2⁰
- Binary: **10110₂** ✓

This method is faster if you know your powers of 2 well. It's also more intuitive—you're literally building the number by adding powers of 2.

## Counting in Binary

Let's count from 0 to 31 in binary and see the patterns:

```
 0₁₀ =      0₂     16₁₀ = 10000₂
 1₁₀ =      1₂     17₁₀ = 10001₂
 2₁₀ =     10₂     18₁₀ = 10010₂
 3₁₀ =     11₂     19₁₀ = 10011₂
 4₁₀ =    100₂     20₁₀ = 10100₂
 5₁₀ =    101₂     21₁₀ = 10101₂
 6₁₀ =    110₂     22₁₀ = 10110₂
 7₁₀ =    111₂     23₁₀ = 10111₂
 8₁₀ =   1000₂     24₁₀ = 11000₂
 9₁₀ =   1001₂     25₁₀ = 11001₂
10₁₀ =   1010₂     26₁₀ = 11010₂
11₁₀ =   1011₂     27₁₀ = 11011₂
12₁₀ =   1100₂     28₁₀ = 11100₂
13₁₀ =   1101₂     29₁₀ = 11101₂
14₁₀ =   1110₂     30₁₀ = 11110₂
15₁₀ =   1111₂     31₁₀ = 11111₂
```

Notice the patterns:
- The rightmost bit alternates: 0, 1, 0, 1, 0, 1...
- The next bit over alternates every 2: 00, 11, 00, 11...
- The next bit over alternates every 4: 0000, 1111, 0000, 1111...
- Each position alternates at twice the frequency of the position to its left

This makes sense! Each position represents "do we have this power of 2?" The 2⁰ place asks "do we have 1?" which alternates with every count. The 2¹ place asks "do we have 2?" which flips every 2 counts.

## Binary Arithmetic: Addition

Addition in binary follows the same rules as base-10, just with different rollover points.

In base-10, we carry when a column sums to 10 or more.
In base-2, we carry when a column sums to 2 or more.

The basic rules:
```
0 + 0 = 0
0 + 1 = 1
1 + 0 = 1
1 + 1 = 10₂  (that's "0, carry 1")
```

Let's add 1011₂ + 1101₂:

```
    1011
  + 1101
  ------
```

Starting from the right:
- 1 + 1 = 10₂ (write 0, carry 1)
- 1 + 0 = 1, plus carried 1 = 10₂ (write 0, carry 1)
- 0 + 1 = 1, plus carried 1 = 10₂ (write 0, carry 1)
- 1 + 1 = 10₂, plus carried 1 = 11₂ (write 11)

```
    ₁₁₁   (carries)
    1011
  + 1101
  ------
   11000
```

**Result: 11000₂**

Let's verify in decimal:
- 1011₂ = 11₁₀
- 1101₂ = 13₁₀
- 11 + 13 = 24₁₀
- 11000₂ = 16 + 8 = 24₁₀ ✓

## Binary Arithmetic: Multiplication

Binary multiplication is actually easier than decimal multiplication because you only multiply by 0 or 1.

- Multiply by 0: Result is 0
- Multiply by 1: Result is the original number

Let's multiply 101₂ × 11₂:

```
    101
  ×  11
  -----
    101  (101 × 1)
   1010  (101 × 1, shifted left because it's the "tens" place)
  -----
   1111
```

**Result: 1111₂**

Verify in decimal:
- 101₂ = 5₁₀
- 11₂ = 3₁₀
- 5 × 3 = 15₁₀
- 1111₂ = 8 + 4 + 2 + 1 = 15₁₀ ✓

The shifting (adding zeros) happens for the same reason as in decimal: each position to the left represents the next power of the base. In binary, moving left one place doubles the value.

## Why Binary Numbers Get So Long

One of the frustrating things about binary is how quickly numbers get long. Look:

- 255₁₀ = 11111111₂ (8 digits!)
- 1000₁₀ = 1111101000₂ (10 digits!)
- 65535₁₀ = 1111111111111111₂ (16 digits!)

In base-10, we can represent 0-99 with two digits. In binary, two digits only get us 0-3. We need more digits to express the same quantities because we have fewer symbols to work with.

This is why computers group binary digits:
- 8 bits = 1 byte (can represent 0-255)
- 16 bits = 2 bytes (can represent 0-65,535)
- 32 bits = 4 bytes (can represent 0-4,294,967,295)
- 64 bits = 8 bytes (can represent 0-18,446,744,073,709,551,615)

A "bit" is a binary digit—a single 0 or 1. A "byte" is 8 bits, the fundamental unit of computer storage.

## Binary in the Real World: Where You See It

### Computer Memory and File Sizes

Computer storage is measured in powers of 2:
- 1 byte = 8 bits
- 1 kilobyte = 1,024 bytes (2¹⁰)
- 1 megabyte = 1,024 kilobytes (2²⁰)
- 1 gigabyte = 1,024 megabytes (2³⁰)
- 1 terabyte = 1,024 gigabytes (2⁴⁰)

Notice it's 1,024, not 1,000. That's because computers think in binary. 2¹⁰ = 1,024, which is close enough to 1,000 that we call it "kilo" (thousand), but it's not exact.

Actually, there's been a movement to use "kibibyte" (KiB) for 1,024 bytes and reserve "kilobyte" (KB) for 1,000 bytes, but in practice, people still use KB to mean 1,024 bytes. Welcome to the chaos of real-world standards!

### IP Addresses (IPv4)

An IPv4 address looks like: 192.168.1.1

Each number (0-255) is actually one byte (8 bits). So an IP address is 32 bits total:

```
192      .168      .1        .1
11000000 .10101000 .00000001 .00000001
```

Routers and computers work with these 32-bit binary addresses, but humans prefer the decimal representation because 192.168.1.1 is easier to remember than 11000000101010000000000100000001.

### Boolean Logic

Binary maps perfectly to Boolean logic (true/false):
- 1 = true
- 0 = false

Logical operations:
- AND: Both must be 1 → result is 1
  - 1 AND 1 = 1
  - 1 AND 0 = 0
  - 0 AND 0 = 0

- OR: At least one must be 1 → result is 1
  - 1 OR 1 = 1
  - 1 OR 0 = 1
  - 0 OR 0 = 0

- NOT: Flip the bit
  - NOT 1 = 0
  - NOT 0 = 1

These operations are how computers make decisions. Every if-statement, every comparison, ultimately becomes binary logic operations.

### Permissions (Unix/Linux)

File permissions in Unix are expressed in binary. You might see:
```
chmod 755 file.txt
```

That 755 is actually three octal (base-8) digits, but each octal digit represents 3 binary digits:
```
7 = 111₂ = read + write + execute
5 = 101₂ = read + execute (no write)
5 = 101₂ = read + execute (no write)
```

We'll cover octal more in the next chapter, but this is binary hiding under the surface.

### Binary in Culture

Binary has become a cultural symbol for "computer-ness." You see it in:
- The Matrix's falling green code
- Hacker aesthetics
- T-shirts with binary jokes
- The "10 types of people" joke (now you get it!)

## Thinking in Binary: Pattern Recognition

To truly understand binary, try to see patterns without translating to decimal:

**Pattern 1: Powers of 2 are single 1s**
- 1₂ = 1₁₀
- 10₂ = 2₁₀
- 100₂ = 4₁₀
- 1000₂ = 8₁₀
- 10000₂ = 16₁₀

**Pattern 2: All 1s equals 2ⁿ - 1**
- 1₂ = 1₁₀ = 2¹ - 1
- 11₂ = 3₁₀ = 2² - 1
- 111₂ = 7₁₀ = 2³ - 1
- 1111₂ = 15₁₀ = 2⁴ - 1

**Pattern 3: Multiplying by 2 = shift left**
- 101₂ (5) × 2 = 1010₂ (10)
- 110₂ (6) × 2 = 1100₂ (12)

Adding a 0 to the right doubles the number, just like adding a 0 in decimal multiplies by 10.

**Pattern 4: Dividing by 2 = shift right**
- 1010₂ (10) ÷ 2 = 101₂ (5)
- 1100₂ (12) ÷ 2 = 110₂ (6)

Removing the rightmost digit divides by 2 (rounding down).

## Advanced Topic: Negative Numbers and Two's Complement

How do computers represent negative numbers in binary? They can't just add a minus sign—remember, computers only understand 1 and 0.

The solution: **two's complement**. It's clever and initially confusing.

In an 8-bit system:
- Positive numbers: 0-127 (00000000 to 01111111)
- Negative numbers: -1 to -128 (11111111 to 10000000)

The highest bit indicates the sign: 0 for positive, 1 for negative.

To convert a positive number to its negative (two's complement):
1. Flip all the bits (1→0, 0→1)
2. Add 1

Example: Convert 5 to -5 in 8-bit two's complement:
```
5 = 00000101
Flip: 11111010
Add 1: 11111011
-5 = 11111011
```

Why this weird system? Because it makes addition work correctly:
```
  00000101  (5)
+ 11111011  (-5)
----------
 100000000
```

The leading 1 overflows (gets discarded in 8-bit), leaving 00000000 = 0. Perfect!

This means computers can use the same circuitry for addition whether the numbers are positive or negative. Engineering elegance.

## Binary Jokes and Puns

Now that you understand binary, here are some jokes that actually make sense:

1. "There are 10 types of people: those who understand binary, and those who don't."
   - 10₂ = 2₁₀, so "10 types" = "2 types"

2. "I'd tell you a joke about UDP, but you might not get it. Unlike my binary jokes—they always land with 100% accuracy."
   - 100₂ = 4₁₀, but the joke is that binary is exact

3. Why do programmers confuse Halloween and Christmas?
   - Because Oct 31 = Dec 25
   - Octal 31 = 25 decimal (we'll explore this more in the octal chapter!)

4. "My relationship status is 1100110, which is complicated in binary."
   - Actually, 1100110₂ = 102₁₀, which has nothing to do with "complicated," but it sounds technical

## Counting on Your Fingers in Binary

Here's a party trick: you can count to 1,023 on your fingers using binary!

Each finger represents a power of 2:
- Right pinky: 2⁰ = 1
- Right ring: 2¹ = 2
- Right middle: 2² = 4
- Right index: 2³ = 8
- Right thumb: 2⁴ = 16
- Left thumb: 2⁵ = 32
- Left index: 2⁶ = 64
- Left middle: 2⁷ = 128
- Left ring: 2⁸ = 256
- Left pinky: 2⁹ = 512

Finger up = 1, finger down = 0.

To show 42₁₀:
- 42 = 32 + 8 + 2
- 42 = 101010₂
- Put up: left thumb (32), right index (8), right ring (2)

Fair warning: be careful with this system. The number 4 (100₂) requires only your right middle finger extended. Use discretion in public settings.

## Why Binary Matters Beyond Computers

Understanding binary gives you insight into:

1. **Information Theory**: How much information can we store? A bit is the fundamental unit—the answer to a single yes/no question.

2. **Digital vs. Analog**: Binary is discrete (on/off), while analog is continuous (any value). Digital music is sampled thousands of times per second and each sample is stored as binary numbers.

3. **Error Detection**: Binary makes error detection easier. If you receive something that's not 0 or 1, you know there's an error.

4. **Compression**: Understanding binary helps you grasp how compression works—finding patterns in 1s and 0s and encoding them more efficiently.

5. **Cryptography**: Modern encryption relies on binary operations—XOR, AND, bit shifting. It's math, but math performed on binary numbers.

## Conclusion: The Simplest System with Infinite Complexity

Binary is absurdly simple—just 1s and 0s. Yet from this simplicity emerges all of modern computing. Every photo, song, video, game, app, website, and AI model is ultimately just very, very long strings of 1s and 0s, interpreted by hardware that adds, subtracts, compares, and moves these bits around billions of times per second.

When you understand binary, you understand the language computers speak natively. Everything else—the pretty graphics, the friendly interfaces, the app icons—is translation for human benefit. Underneath, it's all binary.

As we move forward to octal and hexadecimal, you'll see they're really just shorthand for binary. Programmers got tired of writing 11101011 when they could write EB, so they invented hexadecimal (base-16). Octal (base-8) emerged for similar reasons.

But binary is fundamental. Binary is truth. Binary is the foundation upon which the digital world is built.

Now when you see "10 types of people," you'll smile, maybe roll your eyes, but you'll get it. And that's a satisfying feeling.

---

**Coming Up Next:** Chapter 3 - Octal: The Forgotten Middle Child (where we learn why programmers in the 1960s loved base-8)
