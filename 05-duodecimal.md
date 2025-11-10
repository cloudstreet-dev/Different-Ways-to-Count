# Chapter 5: Base-12 (Duodecimal) — Ancient Wisdom

## Introduction: The System That Should Have Won

Imagine a world where dividing by 3 doesn't give you 0.333333... Imagine fractions that actually make sense. Imagine a number system so practical, so divisible, so elegant that ancient civilizations independently discovered it across the globe.

Welcome to base-12, also called duodecimal or dozenal.

Base-12 uses twelve digits, and before you ask: yes, we need two new symbols beyond 0-9, just like hexadecimal. But unlike hexadecimal, which exists to serve computers, base-12 emerged from very human needs: commerce, time, measurement, and the universal desire to divide things evenly without getting fractions with infinite decimal places.

The ancient Sumerians and Babylonians used base-12 (and base-60, which we'll cover next chapter). Traces of duodecimal thinking persist in modern life:
- 12 inches in a foot
- 12 hours on a clock face
- 12 months in a year
- Dozens (12) and gross (144 = 12²)
- 12 zodiac signs
- 12 notes in a musical octave (chromatic scale)

Some passionate advocates argue we should have adopted base-12 instead of base-10. They call themselves "dozenalists" and they make surprisingly compelling arguments. This chapter will show you why.

## Why Base-12 Is Special: The Magic of Divisibility

The fundamental advantage of base-12 over base-10 is **divisibility**.

10 is divisible by: 1, 2, 5, 10
12 is divisible by: 1, 2, 3, 4, 6, 12

Having more factors means more fractions come out "clean" (without repeating decimals).

Watch what happens when we divide by common numbers:

**In Base-10:**
```
10 ÷ 2 = 5.0 ✓
10 ÷ 3 = 3.333... ✗
10 ÷ 4 = 2.5 ~
10 ÷ 5 = 2.0 ✓
10 ÷ 6 = 1.666... ✗
```

**In Base-12:**
```
12 ÷ 2 = 6.0 ✓
12 ÷ 3 = 4.0 ✓
12 ÷ 4 = 3.0 ✓
12 ÷ 5 = 2.4 ~ (but even this is "cleaner")
12 ÷ 6 = 2.0 ✓
```

See the difference? In base-12, dividing by 2, 3, 4, or 6 gives you a whole number. This is huge for:
- **Commerce**: Splitting prices (1/2, 1/3, 1/4 of a dozen)
- **Measurement**: Dividing lengths evenly
- **Time**: Dividing hours into quarters and thirds
- **Music**: Dividing octaves into semitones

This practical advantage explains why base-12 thinking persists despite base-10's dominance.

## The Duodecimal Digits

Base-12 needs twelve symbols. We have 0-9, so we need two more.

Several notations have been proposed:

**Traditional Dozenal Society symbols:**
- ↊ (turned 2) = ten
- ↋ (turned 3) = eleven

**Alternative symbols:**
- X (or χ) = ten
- E (or ε) = eleven

**Most common in practice:**
- A or T = ten
- B or E = eleven

For this chapter, we'll use **A** for ten and **B** for eleven, following the hexadecimal convention most readers know.

So the duodecimal digits are: **0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B**

After B comes 10₁₂ (which equals twelve in base-10).

## Counting in Duodecimal

Let's count from 0 to 24 in base-12:

```
Decimal    Duodecimal
  0            0
  1            1
  2            2
  3            3
  4            4
  5            5
  6            6
  7            7
  8            8
  9            9
 10            A
 11            B
 12           10    ← rollover!
 13           11
 14           12
 15           13
 16           14
 17           15
 18           16
 19           17
 20           18
 21           19
 22           1A
 23           1B
 24           20
```

The pattern: count 0-9, A, B, then roll over to 10₁₂.

## Place Value in Duodecimal

Place values are powers of 12:

```
... 12⁴   12³   12²  12¹  12⁰
    20736 1728  144  12   1
```

Let's decode 2A5₁₂:

```
  2     A     5
  ↓     ↓     ↓
12²   12¹   12⁰
144    12     1
```

- 2 × 144 = 288
- A (10) × 12 = 120
- 5 × 1 = 5
- **Total: 288 + 120 + 5 = 413₁₀**

So 2A5₁₂ = 413₁₀

Let's try 100₁₂:

```
  1     0     0
  ↓     ↓     ↓
12²   12¹   12⁰
144    12     1
```

- 1 × 144 = 144
- 0 × 12 = 0
- 0 × 1 = 0
- **Total: 144₁₀**

So 100₁₂ = 144₁₀ (a "gross" in English)

## Historical Use: Why Twelve?

Several theories explain why humans gravitated toward twelve:

### Theory 1: Finger Counting by Segments

Look at your fingers (not your thumb). Each finger has three segments (bones). If you use your thumb to point at each segment, you can count to 12 on one hand:

```
Index finger: 3 segments
Middle finger: 3 segments
Ring finger: 3 segments
Pinky finger: 3 segments
Total: 12
```

Ancient Sumerians and Babylonians likely counted this way. Your other hand could track dozens (multiples of 12), giving you a range up to 60—which brings us to base-60, coming next chapter!

### Theory 2: Astronomical Observations

The Moon completes roughly 12 lunar cycles per year. Ancient calendars often had 12 months. The zodiac has 12 signs, corresponding to 12 lunar months.

### Theory 3: Practical Divisibility

Merchants needed to divide goods. Twelve items can be split evenly among 2, 3, 4, or 6 customers. Ten items can only be split among 2 or 5 customers.

If you're selling grain, bread, or cloth, divisibility matters.

## Converting Decimal to Duodecimal

Use successive division by 12:

**Example 1:** Convert 100₁₀ to duodecimal

```
100 ÷ 12 = 8 remainder 4
  8 ÷ 12 = 0 remainder 8
```

Result: **84₁₂**

Verify: (8 × 12) + 4 = 96 + 4 = 100₁₀ ✓

**Example 2:** Convert 144₁₀ to duodecimal

```
144 ÷ 12 = 12 remainder 0
 12 ÷ 12 = 1  remainder 0
  1 ÷ 12 = 0  remainder 1
```

Result: **100₁₂**

This makes sense: 144 is 12², so it's 100 in base-12, just like 100₁₀ is 10² in base-10.

**Example 3:** Convert 500₁₀ to duodecimal

```
500 ÷ 12 = 41 remainder 8
 41 ÷ 12 = 3  remainder 5
  3 ÷ 12 = 0  remainder 3
```

Result: **358₁₂**

Verify: (3 × 144) + (5 × 12) + 8 = 432 + 60 + 8 = 500₁₀ ✓

## Duodecimal Fractions: Where It Shines

This is where base-12 shows its true power. Let's look at common fractions:

**In Base-10 (Decimal):**
```
1/2 = 0.5
1/3 = 0.333...  (repeating)
1/4 = 0.25
1/5 = 0.2
1/6 = 0.166...  (repeating)
1/8 = 0.125
1/10 = 0.1
```

**In Base-12 (Duodecimal):**
```
1/2 = 0.6₁₂
1/3 = 0.4₁₂
1/4 = 0.3₁₂
1/5 = 0.2497...₁₂  (repeating, but rarer fraction)
1/6 = 0.2₁₂
1/8 = 0.16₁₂
1/10₁₂ = 0.1₁₂  (1/12 in decimal)
```

Look at that beauty! In base-12:
- 1/2 = 0.6₁₂ (exactly)
- 1/3 = 0.4₁₂ (exactly!)
- 1/4 = 0.3₁₂ (exactly)
- 1/6 = 0.2₁₂ (exactly!)

No repeating decimals for halves, thirds, quarters, or sixths. These are the most common fractions in everyday life, and base-12 handles them cleanly.

### How Duodecimal Fractions Work

Let's derive 1/2 in base-12:

We want to find x such that: x + x = 1₁₂ (which is 12 in base-10... wait, no. Let me reconsider.)

Actually, in base-12, "1" still means "one whole." So 1/2 means half of one.

Half of 1 in any base is represented by the place value: 1 / 2.

In base-10: 1 / 2 = 5/10 = 0.5
In base-12: 1 / 2 = 6/12 = 0.6₁₂

Why 6? Because 6₁₂ × 2 = 10₁₂ (which is 12₁₀), so 6₁₂ is half of 10₁₂ (the base).

Wait, let me clarify more carefully:

In base-12:
- 0.1₁₂ = 1/12
- 0.2₁₂ = 2/12 = 1/6
- 0.3₁₂ = 3/12 = 1/4
- 0.4₁₂ = 4/12 = 1/3
- 0.6₁₂ = 6/12 = 1/2

So the first decimal place represents twelfths, not tenths!

**1/3 in base-12:**
1/3 = 4/12 = 0.4₁₂

To verify: 0.4₁₂ × 3 = ?
In base-12: 4 × 3 = 10₁₂ (which is 12₁₀)
So 0.4₁₂ × 3 = 0.10₁₂ = 1.0₁₂ ✓

**1/4 in base-12:**
1/4 = 3/12 = 0.3₁₂

To verify: 0.3₁₂ × 4 = ?
In base-12: 3 × 4 = 10₁₂
So 0.3₁₂ × 4 = 1.0₁₂ ✓

This is why dozenalists love base-12: common fractions have simple, terminating representations.

## Duodecimal Multiplication Table

To truly think in base-12, you'd need to learn a new multiplication table:

```
×  | 1  2  3  4  5  6  7  8  9  A  B  10
---+------------------------------------
1  | 1  2  3  4  5  6  7  8  9  A  B  10
2  | 2  4  6  8  A  10 12 14 16 18 1A 20
3  | 3  6  9  10 13 16 19 20 23 26 29 30
4  | 4  8  10 14 18 20 24 28 30 34 38 40
5  | 5  A  13 18 21 26 2B 34 39 42 47 50
6  | 6  10 16 20 26 30 36 40 46 50 56 60
```

Some interesting patterns:

**Multiples of 2:**
2, 4, 6, 8, A, 10₁₂, 12₁₂, 14₁₂...
(After A comes 10₁₂, which is 12₁₀)

**Multiples of 3:**
3, 6, 9, 10₁₂, 13₁₂, 16₁₂, 19₁₂...
(After 9 comes 10₁₂)

**Multiples of 6:**
6, 10₁₂, 16₁₂, 20₁₂, 26₁₂, 30₁₂...

Notice: 6 × 2 = 10₁₂ (the base itself!)

## Duodecimal Arithmetic: Addition

```
  5A₁₂
+ 3B₁₂
------
```

Rightmost: A (10) + B (11) = 21₁₀ = 19₁₂
- 21 ÷ 12 = 1 remainder 9
- Write 9, carry 1

Leftmost: 5 + 3 + 1 = 9

```
   ₁     (carry)
  5A₁₂
+ 3B₁₂
------
  99₁₂
```

Verify in decimal:
- 5A₁₂ = (5 × 12) + 10 = 70₁₀
- 3B₁₂ = (3 × 12) + 11 = 47₁₀
- 70 + 47 = 117₁₀
- 99₁₂ = (9 × 12) + 9 = 108 + 9 = 117₁₀ ✓

## Duodecimal in Modern Life

Though we officially use base-10, base-12 thinking persists:

### Time

**12 hours per clock face**
Why 12? It's divisible by 2, 3, 4, and 6. Easy to say:
- "Quarter past" (1/4 of 12 = 3 minutes)
- "Half past" (1/2 of 12 = 6 minutes)
- "Twenty past" (divides evenly)

**60 minutes per hour**
60 = 12 × 5 (we'll explore this in the sexagesimal chapter)

### Measurement

**12 inches = 1 foot**
Why not 10? Because 12 is more divisible:
- 1/2 foot = 6 inches (whole number)
- 1/3 foot = 4 inches (whole number)
- 1/4 foot = 3 inches (whole number)
- 1/6 foot = 2 inches (whole number)

Try that in metric:
- 1/2 meter = 50 cm ✓
- 1/3 meter = 33.333... cm ✗
- 1/4 meter = 25 cm ✓
- 1/6 meter = 16.666... cm ✗

**12 troy ounces = 1 troy pound** (precious metals)

### Commerce

**Dozen (12) and Gross (144 = 12²)**
Eggs are sold by the dozen because:
- 1/2 dozen = 6
- 1/3 dozen = 4
- 1/4 dozen = 3

**12-packs** of beverages (easier to split than 10-packs)

### Culture

**12 months** (roughly 12 lunar cycles per year)
**12 zodiac signs**
**12 hours** (AM/PM)
**12 notes** in chromatic musical scale
**12 days of Christmas** (a dozen days of presents!)

## The Dozenal Movement

There's a small but passionate community advocating for switching from base-10 to base-12. The Dozenal Society of America (DSA) argues:

**Advantages of base-12:**
1. More divisors (2, 3, 4, 6 vs just 2, 5)
2. Cleaner fractions (1/3, 1/4, 1/6 all terminate)
3. Historical precedent (Sumerians, measurements)
4. Practical for commerce and everyday splitting

**Their counterarguments to objections:**
- "But we have 10 fingers!" → Count by finger segments (12 per hand)
- "Too hard to switch!" → We switched currencies, measurements before
- "No one uses it!" → Because of chicken-and-egg problem

They've invented new symbols (↊ and ↋), new terminology (dozen, gross), and even duodecimal metric systems.

Realistically? We're not switching. Base-10 is too entrenched, and computers speak binary (which relates to powers of 2, making hexadecimal more relevant than duodecimal for computing).

But intellectually? The dozenalists have a point.

## Duodecimal Patterns

**Pattern 1: Powers of 12**
```
12⁰ = 1   = 1₁₂
12¹ = 12  = 10₁₂
12² = 144 = 100₁₂
12³ = 1728 = 1000₁₂
```

Just like decimal, multiplying by the base adds a zero.

**Pattern 2: All Bs (highest digit)**
```
B₁₂ = 11₁₀
BB₁₂ = 143₁₀ (12² - 1)
BBB₁₂ = 1727₁₀ (12³ - 1)
```

**Pattern 3: Half of the base**
In base-10, half of 10 is 5.
In base-12, half of 10₁₂ (12₁₀) is 6.

So 6₁₂ is like our 5—it's the "middle digit."

## Alternative Symbols for Ten and Eleven

Different duodecimal enthusiasts use different symbols:

**Turned digits (DSA):**
- ↊ = ten (turned 2)
- ↋ = eleven (turned 3)

**Greek letters:**
- α (alpha) = ten
- β (beta) = eleven

**Letters:**
- A and B (like hex)
- T and E (Ten and Eleven)
- X and Y

**Playing card inspiration:**
- T (ten, like in cards)
- J (jack = eleven, like in cards)

No universal standard exists outside of math papers (which often use A and B for consistency with hexadecimal).

## Could We Actually Use Base-12?

Hypothetically, if we used base-12:

**Counting words would change:**
We'd need a word for "twelve" that's as simple as "ten."
Maybe: "doh" (from "dozen")

```
1, 2, 3, 4, 5, 6, 7, 8, 9, dek, el, doh
doh-one, doh-two, ... two-doh, three-doh...
```

**Written numbers:**
We'd use 0-9, A, B (or some other symbols).

**Arithmetic:**
We'd memorize multiplication tables up to 12 × 12.

**Fractions:**
Life would be easier! 1/3 = 0.4, 1/6 = 0.2.

**Computers:**
Would still use binary. Hex wouldn't change. But maybe we'd use base-12 for human-facing interfaces?

**Measurements:**
Already partially there (feet/inches, dozens).

## Conclusion: The Path Not Taken

Base-12 is the "what if" of number systems. What if we'd prioritized divisibility over anatomy? What if ancient Sumerian finger-segment counting had won out over Egyptian finger counting?

We'd have a system that:
- Makes fractions easier
- Splits things more evenly
- Aligns with historical measurements
- Makes mental math cleaner for common divisions

But we didn't take that path. Base-10 won, probably because:
1. Most cultures counted on fingers/toes (base-10 or base-20)
2. Hindu-Arabic numerals (base-10) spread globally
3. The metric system (base-10) became the scientific standard
4. Network effects: once everyone uses base-10, switching is nearly impossible

Still, traces of base-12 linger. Every time you check a clock, buy eggs by the dozen, or measure something in feet and inches, you're using duodecimal thinking.

And maybe, in some alternate universe, children learn their "twelves tables" up to doh-times-doh, and they think base-10 is weird because "who wants 3.333... when dividing by three?"

In that universe, the dozenalists won.

In our next chapter, we'll explore an even more impressive ancient number system: base-60, the sexagesimal system of the Babylonians. If base-12 is impressively divisible, base-60 is mind-blowingly divisible. And we still use it every single day to tell time and measure angles.

---

**Coming Up Next:** Chapter 6 - Sexagesimal (Base-60): The Babylonian Legacy (where we discover why there are 60 seconds in a minute)
