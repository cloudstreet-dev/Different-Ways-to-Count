# Chapter 7: Other Bases and Practical Applications — The Variety Show

## Introduction: Beyond the Greatest Hits

We've explored the major players:
- Base-10: The standard
- Base-2: Computers' native tongue
- Base-8: The nostalgic middle child
- Base-16: Programmers' favorite
- Base-12: The one that could have been
- Base-60: The eternal legacy

But the world of number systems doesn't end there. Throughout history and across cultures, humans have experimented with many different bases. Some emerged from practical needs, others from anatomical quirks, and a few from pure mathematical curiosity.

This chapter is our tour through the variety show: historical systems, modern computing applications, theoretical oddities, and practical tools you might encounter in the wild.

Buckle up—we're about to count in ways you never imagined.

## Base-20 (Vigesimal): The Mayan System

### What It Is

Base-20 uses twenty digits (0-19). After 19 comes 10₂₀ (which equals twenty in decimal).

Place values: 20⁰ = 1, 20¹ = 20, 20² = 400, 20³ = 8,000

### Where It Came From

**Anatomical origin:** Fingers and toes! If you count on all twenty digits, you naturally arrive at base-20.

The **Maya civilization** of Central America used a sophisticated base-20 system for astronomy, calendars, and mathematics. They were one of the first cultures to independently invent zero (as both a placeholder and a number).

**European remnants:** French preserves base-20 thinking:
- 80 = *quatre-vingts* ("four twenties")
- 90 = *quatre-vingt-dix* ("four twenties ten")

Danish has similar quirks. These are linguistic fossils of once-widespread vigesimal counting.

### How It Works

Counting in base-20:
```
0, 1, 2, 3, ... 18, 19, 10₂₀, 11₂₀, 12₂₀, ... 1G₂₀, 1H₂₀, 1I₂₀, 1J₂₀, 20₂₀
```

(We'd need symbols for 10-19; let's use A-J for consistency with other bases)

Convert 100₁₀ to base-20:
```
100 ÷ 20 = 5 remainder 0
  5 ÷ 20 = 0 remainder 5
```
Result: **50₂₀**

Verify: 5 × 20 + 0 = 100₁₀ ✓

Convert 400₁₀ to base-20:
```
400 ÷ 20 = 20 remainder 0
 20 ÷ 20 = 1  remainder 0
  1 ÷ 20 = 0  remainder 1
```
Result: **100₂₀** (exactly 20²)

### Mayan Numbers: A Visual System

The Maya didn't use digits 0-19. Instead, they used:
- A dot (•) = 1
- A bar (—) = 5
- A shell symbol = 0

They combined these within each place:
- •• = 2
- ••• = 3
- — = 5
- —• = 6
- —— = 10
- ——— = 15
- ———•••• = 19

Numbers were written **vertically**, with higher places above lower ones (opposite our convention).

Example: The number 32₁₀ in Mayan:
- 32 = (1 × 20) + (12 × 1)
- Bottom place: —— •• (12)
- Top place: • (1)

Beautiful and efficient!

### Why Base-20 Didn't Win

Base-10 had better marketing (and colonial spread). Base-20's main advantage—using all your digits—is offset by:
- Larger multiplication tables (20 × 20 = 400 entries)
- Less divisibility than base-12 or base-60
- No technological advantage (unlike binary for computers)

Still, for cultures that developed it independently, base-20 was perfectly functional.

## Base-3 (Ternary): The Minimalist Alternative

### What It Is

Base-3 uses three digits: **0, 1, 2**

Place values: 3⁰ = 1, 3¹ = 3, 3² = 9, 3³ = 27

### Why It's Interesting

From an information theory perspective, base-3 is theoretically optimal for certain types of computation. A "trit" (ternary digit) can be 0, 1, or 2.

Some arguments for ternary:
- **Balanced ternary** (using -1, 0, 1) can represent negatives without two's complement
- Some quantum computing proposals use ternary logic (qutrits instead of qubits)
- Hypothetically more efficient than binary for certain operations

### How It Works

Counting in base-3:
```
0, 1, 2, 10₃, 11₃, 12₃, 20₃, 21₃, 22₃, 100₃, 101₃...
```

Convert 10₁₀ to base-3:
```
10 ÷ 3 = 3 remainder 1
 3 ÷ 3 = 1 remainder 0
 1 ÷ 3 = 0 remainder 1
```
Result: **101₃**

Verify: (1 × 9) + (0 × 3) + (1 × 1) = 9 + 0 + 1 = 10₁₀ ✓

### Balanced Ternary: The Elegant Variant

Instead of {0, 1, 2}, use **{-1, 0, 1}** (sometimes written as {T, 0, 1} where T = "negative one"):

Example: Represent 5₁₀ in balanced ternary:
- 5 = 9 - 3 - 1 = (1 × 3²) + (-1 × 3¹) + (-1 × 3⁰)
- Written: 1TT₃

Advantages:
- No separate negative sign needed
- Rounding is symmetric
- Arithmetic has elegant properties

Some Soviet computers in the 1950s-70s actually used balanced ternary!

### Why We Don't Use It

Hardware is easier to build with two states (on/off) than three states (negative/zero/positive voltage). Binary won on engineering practicality, not theoretical elegance.

## Base-64: Encoding Binary Data

### What It Is

Base-64 uses **64 characters**:
- A-Z (26 characters)
- a-z (26 characters)
- 0-9 (10 characters)
- + and / (2 characters)
- Total: 64

### Why It Exists

Base-64 is used to encode binary data (like images or files) as text. This is crucial when you need to transmit binary data through systems that only handle text (like email).

**The problem:** You have binary data (bytes 0-255), but you can only send ASCII text.

**The solution:** Convert every 6 bits (2⁶ = 64 possibilities) into one base-64 character.

### How It Works

Each base-64 digit represents 6 bits:
- A = 000000₂ = 0₁₀
- B = 000001₂ = 1₁₀
- ...
- Z = 011001₂ = 25₁₀
- a = 011010₂ = 26₁₀
- ...
- z = 110011₂ = 51₁₀
- 0 = 110100₂ = 52₁₀
- ...
- 9 = 111101₂ = 61₁₀
- + = 111110₂ = 62₁₀
- / = 111111₂ = 63₁₀

**Example:** Encode the bytes `[M, a, n]` in base-64:

```
M = 77₁₀ = 01001101₂
a = 97₁₀ = 01100001₂
n = 110₁₀ = 01101110₂

Combined: 010011010110000101101110₂

Split into 6-bit groups:
010011 010110 000101 101110
   19     22      5      46

Convert to base-64:
19 = T
22 = W
5 = F
46 = u

Result: TWFu
```

So "Man" encoded in base-64 is "TWFu".

### Where You See It

- **Email attachments** (MIME encoding)
- **Data URIs** (embedding images in HTML/CSS)
- **JWT tokens** (web authentication)
- **Cryptographic keys**

Example data URI:
```html
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..." />
```

That long string after `base64,` is image data encoded in base-64.

### Why Base-64 Specifically?

64 = 2⁶, so each base-64 digit encodes exactly 6 bits. Three bytes (24 bits) convert to exactly four base-64 characters (24 bits). Clean math!

If padding is needed (when data isn't a multiple of 3 bytes), the `=` character is used:
- `Man` → `TWFu` (no padding)
- `Ma` → `TWE=` (1 byte padding)
- `M` → `TQ==` (2 bytes padding)

## Base-32: Human-Friendly Encoding

### What It Is

Base-32 uses **32 characters**:
- A-Z (26 characters)
- 2-7 (6 numbers)

Note: 0, 1, 8, and 9 are excluded to avoid confusion (0/O, 1/I/l, 8/B).

### Why It Exists

Base-32 is like base-64 but easier for humans:
- Case-insensitive (only uses A-Z, not a-z)
- Avoids ambiguous characters
- Safe for URLs and filenames

Each base-32 character represents 5 bits (2⁵ = 32).

### Where You See It

- **Google Authenticator codes** (two-factor authentication)
- **Git commit hashes** (sometimes)
- **Torrent magnet links**
- **License keys**

Example: A Google Authenticator secret:
```
JBSWY3DPEHPK3PXP
```

This encodes a binary secret key used to generate time-based one-time passwords.

### Advantages Over Base-64

- Easier to type (no lowercase, no special symbols)
- Less error-prone (no confusing similar characters)
- Case-insensitive (survives UPPERCASE SHOUTING)

Disadvantage:
- Less efficient (5 bits per character vs 6 bits for base-64)

## Other Historical Bases

### Base-4 (Quaternary)

Uses: **0, 1, 2, 3**

Rare historically, but interesting because:
- DNA has 4 bases (A, C, G, T) - representable in quaternary
- Easy conversion to/from binary (2 bits = 1 quaternary digit)

### Base-5 (Quinary)

Uses: **0, 1, 2, 3, 4**

Some cultures counted in base-5 (one hand). Evidence in some South American indigenous languages.

### Base-7 (Septenary)

Uses: **0, 1, 2, 3, 4, 5, 6**

Rare. 7 has mystical significance in some cultures (7 days of week, 7 deadly sins), but not practical for a number system (7 is prime, few divisors).

## Exotic and Theoretical Bases

### Base-φ (Phi-base)

Using the golden ratio φ ≈ 1.618... as a base!

This requires non-integer bases, leading to bizarre properties:
- Multiple representations of the same number
- Non-standard arithmetic
- Mostly theoretical curiosity

### Base-e (Natural Base)

Using Euler's number e ≈ 2.718... as a base.

From an information theory perspective, base-e is theoretically optimal for representing numbers efficiently. But since we can't have 2.718 different digits, it remains theoretical.

### Base-i (Complex Base)

Using the imaginary unit i = √(-1) as a base. Numbers can be represented without explicit imaginary parts!

Example: 2₁₀ = 10₂ = (1, -1, 0, 2)ᵢ (various representations possible)

Utterly impractical but mathematically fascinating.

### Negative Bases

Base -10, base -2, etc. These work but lead to weird properties:
- Negative numbers need no minus sign
- Unusual arithmetic rules
- Mostly theoretical

## Practical Applications: Where Bases Matter

### Computer Science

**Binary (base-2):** Foundation of all digital computing

**Hexadecimal (base-16):** Memory addresses, color codes, debugging

**Base-64:** Encoding binary data as text

**Base-32:** Human-friendly encoding (2FA secrets, license keys)

### Mathematics

**Different bases for different fields:**
- Number theory: Studying properties across bases
- Cryptography: Base conversions for encoding
- Information theory: Optimal bases for storage/transmission

### Human-Computer Interaction

**QR codes:** Internally use base-2 but encode various data types

**URL shorteners:** Often use base-62 (0-9, A-Z, a-z) for compact unique IDs

**Barcodes:** Various bases depending on type (UPC, EAN, Code 39, etc.)

## Converting Between Arbitrary Bases

### General Algorithm

To convert from base-A to base-B:
1. Convert base-A to decimal (base-10)
2. Convert decimal to base-B

Example: Convert 123₄ to base-5

Step 1: Convert 123₄ to decimal:
```
123₄ = (1 × 4²) + (2 × 4¹) + (3 × 4⁰)
     = (1 × 16) + (2 × 4) + (3 × 1)
     = 16 + 8 + 3
     = 27₁₀
```

Step 2: Convert 27₁₀ to base-5:
```
27 ÷ 5 = 5 remainder 2
 5 ÷ 5 = 1 remainder 0
 1 ÷ 5 = 0 remainder 1
```
Result: **102₅**

Verify: (1 × 25) + (0 × 5) + (2 × 1) = 25 + 0 + 2 = 27₁₀ ✓

### Direct Conversion (Advanced)

For bases that are powers of each other, you can convert directly:

**Binary ↔ Octal:** Group by 3 bits
**Binary ↔ Hex:** Group by 4 bits
**Octal ↔ Hex:** Convert through binary

Example: Convert 7A₁₆ to octal:
```
7A₁₆ → binary: 0111 1010₂ → 01 111 010 → 172₈
```

## The Philosophy of Bases

After exploring so many systems, a pattern emerges:

**There is no "perfect" base.** Each has tradeoffs:

- **Small bases** (2, 3): Simple symbols, but long numbers
- **Medium bases** (8, 10, 12, 16): Balanced practicality
- **Large bases** (60, 64): Compact but complex

**Context determines choice:**
- Hardware constraints → binary
- Human anatomy → decimal or vigesimal
- Divisibility needs → base-12 or base-60
- Encoding efficiency → base-64
- Mathematical elegance → ternary or phi-base

**Historical accident matters:** We use base-10 largely because we have ten fingers and Hindu-Arabic numerals spread globally. In another timeline, we might be dozenalists or vigesimalists.

## Modern Tools: Working with Multiple Bases

### Programming Languages

Most languages support multiple bases:

**Python:**
```python
bin(42)      # '0b101010' (binary)
oct(42)      # '0o52' (octal)
hex(42)      # '0x2a' (hexadecimal)
int('2a', 16) # 42 (parse hex)
int('101', 2)  # 5 (parse binary)
```

**JavaScript:**
```javascript
(42).toString(2)   // '101010' (binary)
(42).toString(16)  // '2a' (hex)
parseInt('2a', 16) // 42
```

### Online Calculators

Numerous base conversion calculators exist:
- RapidTables Base Converter
- Calculator.net Base Calculator
- Wolfram Alpha (handles exotic bases too)

### Terminal/Command Line

**macOS/Linux bc (basic calculator):**
```bash
echo "obase=2; 42" | bc    # Convert 42 to binary
echo "ibase=16; 2A" | bc   # Convert 2A (hex) to decimal
```

## Fun Facts Across Bases

### Binary
- All even numbers end in 0
- Doubling = shift left (add a 0)
- Halving = shift right (remove rightmost digit)

### Octal
- Unix permissions (chmod 755)
- Favorite of 1960s programmers

### Decimal
- Won by anatomical accident
- Only medium divisibility (2, 5)
- Universal due to historical spread

### Duodecimal
- Most championed alternative to decimal
- Excellent divisibility (2, 3, 4, 6)
- Lives on in measurements

### Hexadecimal
- Programmer's daily driver
- Perfect for byte representation
- DEADBEEF and CAFEBABE live here

### Sexagesimal
- 4,000-year-old legacy
- Unmatched divisibility
- Time and angles forever

## Conclusion: A Universe of Counting

We started this journey thinking numbers "just are." But now you see: numbers are represented differently across bases, and each system brings its own logic, advantages, and quirks.

You've learned:
- How to convert between any bases
- Why certain bases dominate certain domains
- How hardware, culture, and mathematics shape our counting
- That "10" means different things in different bases

This knowledge isn't just academic. Understanding number systems gives you:
- Deeper insight into computing
- Appreciation for ancient mathematics
- Ability to work with hexadecimal debugging
- Understanding of why we measure time the way we do

Most importantly, you've developed **cognitive flexibility**—the ability to see the same concept (quantity) through different lenses (representations).

In our final chapter, we'll tie everything together: what you've learned, where to go next, and how these different ways of counting connect to bigger ideas in mathematics, computing, and human culture.

The journey's almost complete. One more chapter to go.

---

**Coming Up Next:** Chapter 8 - Conclusion: Counting the Ways (where we reflect on this journey through number systems)
