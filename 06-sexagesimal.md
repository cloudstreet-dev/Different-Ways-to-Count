# Chapter 6: Base-60 (Sexagesimal) — The Babylonian Legacy

## Introduction: The Most Ambitious Number System

Picture yourself as a Babylonian mathematician in 2000 BCE, working with clay tablets in the shadow of a ziggurat. You need a number system that handles astronomy, commerce, architecture, and taxation. What base do you choose?

Ten? Too few divisors.
Twelve? Better, but still limited.

How about... **sixty**?

Yes, sixty. Base-60. Sexagesimal. The most audacious, divisibility-packed number system ever used at scale by a major civilization.

The ancient Sumerians and Babylonians developed and used base-60 for over 4,000 years. And remarkably, we still use it today—every single day—without thinking about it:

- **60 seconds** in a minute
- **60 minutes** in an hour
- **360 degrees** in a circle (6 × 60)

When you check your watch, you're using Babylonian mathematics. When you measure an angle with a protractor, you're thinking in sexagesimal. When you specify a GPS coordinate (42° 21' 30" N), those seconds and minutes are base-60.

This chapter explores the most mathematically sophisticated legacy of the ancient world—a number system so well-designed that it has survived for four millennia and shows no signs of disappearing.

## Why Base-60? The Ultimate Divisibility

If base-12 is good for divisibility, base-60 is incredible.

**Factors of 60:** 1, 2, 3, 4, 5, 6, 10, 12, 15, 20, 30, 60

That's **twelve divisors**. Compare that to:
- 10 has 4 divisors: 1, 2, 5, 10
- 12 has 6 divisors: 1, 2, 3, 4, 6, 12
- 60 has 12 divisors: 1, 2, 3, 4, 5, 6, 10, 12, 15, 20, 30, 60

This means incredibly clean divisions:

```
60 ÷ 2 = 30  ✓
60 ÷ 3 = 20  ✓
60 ÷ 4 = 15  ✓
60 ÷ 5 = 12  ✓
60 ÷ 6 = 10  ✓
60 ÷ 10 = 6  ✓
60 ÷ 12 = 5  ✓
```

For ancient astronomers tracking celestial movements, merchants dividing goods, and engineers calculating angles, this flexibility was invaluable. Whatever fraction you needed—halves, thirds, quarters, fifths, sixths, tenths, twelfths—base-60 handled it cleanly.

## How Base-60 Actually Worked

Here's where it gets interesting: the Babylonians didn't use 60 different symbols. That would be insane. Instead, they used a **mixed system** combining base-10 and base-6.

They had symbols for:
- 1 through 9 (using wedge marks)
- 10, 20, 30, 40, 50 (using different wedge marks)

Within each "place," they counted from 1 to 59 using these symbols. Then they'd start a new place (similar to how we write place values in base-10).

Example in Babylonian notation (simplified):
```
| = 1
|| = 2
< = 10
<|| = 12
<<||| = 23
```

A sexagesimal number like "2, 15" meant: (2 × 60) + (15 × 1) = 135₁₀

So they weren't really thinking "fifty-nine different symbols before rolling over." They were grouping: tens within a sixty-place, then moving to the next sixty-place.

## Modern Sexagesimal: Time and Angles

We don't write general numbers in base-60 anymore, but we use it for specific applications:

### Time

**60 seconds = 1 minute**
**60 minutes = 1 hour**

When you write 1:23:45 (1 hour, 23 minutes, 45 seconds), that's sexagesimal place value:
- 1 hour = 1 × 60² seconds = 3,600 seconds
- 23 minutes = 23 × 60 seconds = 1,380 seconds
- 45 seconds = 45 × 1 = 45 seconds
- **Total: 3,600 + 1,380 + 45 = 5,025 seconds**

This is base-60 place value, just with colons instead of positional notation!

### Angles

**360 degrees = full circle** (6 × 60)

Degrees are subdivided sexagesimally:
- 1 degree = 60 minutes (')
- 1 minute = 60 seconds ('')

Example: 42° 30' 15"
- 42 degrees
- 30 minutes = 30/60 degree = 0.5°
- 15 seconds = 15/3600 degree ≈ 0.00417°
- **Total: 42.50417°**

### Geographic Coordinates

Latitude and longitude use degrees, minutes, and seconds:

```
Paris: 48° 51' 24" N, 2° 21' 03" E
```

This is sexagesimal notation! Each degree divides into 60 minutes, each minute into 60 seconds.

## Converting Decimal Time to Sexagesimal

**Example 1:** Convert 7,385 seconds to hours:minutes:seconds

```
7385 ÷ 3600 = 2 remainder 185 (2 hours)
185 ÷ 60 = 3 remainder 5 (3 minutes)
5 remains (5 seconds)
```

**Result: 2:03:05** (2 hours, 3 minutes, 5 seconds)

**Example 2:** Convert 42.5° to degrees, minutes, seconds

```
42° whole degrees
0.5° × 60 = 30' (30 minutes)
0' × 60 = 0'' (0 seconds)
```

**Result: 42° 30' 0"**

**Example 3:** Convert 123.456789° to DMS (degrees, minutes, seconds)

```
123° whole degrees
0.456789° × 60 = 27.40734'
27' whole minutes
0.40734' × 60 ≈ 24.44''
```

**Result: 123° 27' 24"** (rounding the seconds)

## Converting Sexagesimal to Decimal

**Example 1:** Convert 2:30:00 to total seconds

```
2 hours × 3600 = 7,200 seconds
30 minutes × 60 = 1,800 seconds
0 seconds = 0
Total: 9,000 seconds
```

**Example 2:** Convert 45° 30' 15" to decimal degrees

```
45 degrees = 45.0°
30 minutes = 30 ÷ 60 = 0.5°
15 seconds = 15 ÷ 3600 = 0.004167°
Total: 45.504167°
```

**Example 3:** Convert 1:00:01 (1 hour, 0 minutes, 1 second) to total seconds

```
1 × 3600 = 3600
0 × 60 = 0
1 × 1 = 1
Total: 3,601 seconds
```

## Why 360 Degrees in a Circle?

You might wonder: why 360 degrees? Why not 100, or 1000, or some other nice round number?

Several theories:

### Theory 1: Approximation of Year Length

The Babylonian year was roughly 360 days (actually ~365.25, but 360 is close and highly divisible). A circle representing the zodiac/celestial sphere naturally divided into 360 degrees—one degree per day of travel.

### Theory 2: Geometric Convenience

360 is divisible by 1, 2, 3, 4, 5, 6, 8, 9, 10, 12, 15, 18, 20, 24, 30, 36, 40, 45, 60, 72, 90, 120, 180, 360.

That's **24 divisors**! For ancient geometers, this meant angles could be divided evenly in many ways without fractions.

### Theory 3: Base-60 Influence

360 = 6 × 60, fitting neatly into the Babylonian base-60 system. A circle divided into 6 "sixties" is conceptually clean in their mathematical framework.

Whatever the reason, 360 stuck. Even today, with computers and decimal systems everywhere, we still use 360° circles. The Babylonians designed well.

## Babylonian Mathematics: Place Value Without Zero

One fascinating aspect of Babylonian sexagesimal: they didn't have a zero for most of their history.

This caused ambiguity. The notation "2, 15" could mean:
- (2 × 60) + 15 = 135
- (2 × 3600) + (15 × 60) = 8,100
- Just 2 and 15 with no place value (2.25 in our decimal thinking?)

Context determined interpretation. Later Babylonians invented a placeholder symbol (similar to zero), but it wasn't used as a number itself—just a marker for "empty place."

This shows both the sophistication and limitations of their system. They understood place value conceptually but lacked the full algebraic power that a true zero provides.

## Modern Remnants of Base-60

Beyond time and angles, base-60 thinking appears in unexpected places:

### Music

In some music theory contexts, the "perfect fifth" ratio is 3:2. The circle of fifths has 12 positions (related to 60 via 5 × 12 = 60). Ancient music theory was deeply mathematical, influenced by Babylonian astronomy.

### Navigation

Nautical navigation uses:
- Degrees, minutes, seconds for coordinates
- Knots (nautical miles per hour) for speed

A nautical mile is based on one minute of latitude (1/60 of a degree), directly from sexagesimal thinking.

### Traditional Weights and Measures

Ancient systems had remnants:
- Babylonian talent divided into 60 minas
- Various historical divisions by 12 and 60

These have mostly been replaced by metric, but base-60 was once everywhere in measurement.

## Sexagesimal Arithmetic: Addition

Adding in base-60 means carrying when you exceed 59.

**Example:** Add 2:45:30 + 1:25:45 (in time notation)

```
  2:45:30
+ 1:25:45
---------
```

Seconds: 30 + 45 = 75
- 75 ≥ 60, so: 75 - 60 = 15 seconds, carry 1 minute

Minutes: 45 + 25 + 1 (carry) = 71
- 71 ≥ 60, so: 71 - 60 = 11 minutes, carry 1 hour

Hours: 2 + 1 + 1 (carry) = 4

**Result: 4:11:15**

Verify in total seconds:
- 2:45:30 = (2 × 3600) + (45 × 60) + 30 = 7,200 + 2,700 + 30 = 9,930 seconds
- 1:25:45 = (1 × 3600) + (25 × 60) + 45 = 3,600 + 1,500 + 45 = 5,145 seconds
- Sum: 9,930 + 5,145 = 15,075 seconds
- 15,075 ÷ 3600 = 4 remainder 675
- 675 ÷ 60 = 11 remainder 15
- Result: 4:11:15 ✓

## Sexagesimal Arithmetic: Subtraction

Subtracting means borrowing 60 when needed.

**Example:** 5:15:20 - 2:30:45

```
  5:15:20
- 2:30:45
---------
```

Seconds: 20 - 45? Can't do it.
- Borrow 1 minute (60 seconds): 20 + 60 = 80
- 80 - 45 = 35 seconds
- Minutes place loses 1: 15 becomes 14

Minutes: 14 - 30? Can't do it.
- Borrow 1 hour (60 minutes): 14 + 60 = 74
- 74 - 30 = 44 minutes
- Hours place loses 1: 5 becomes 4

Hours: 4 - 2 = 2

**Result: 2:44:35**

Verify:
- 5:15:20 = 18,920 seconds
- 2:30:45 = 9,045 seconds
- Difference: 18,920 - 9,045 = 9,875 seconds
- 9,875 ÷ 3600 = 2 remainder 1,675
- 1,675 ÷ 60 = 27 remainder 55

Wait, that gives 2:27:55, not 2:44:35. Let me recalculate...

Actually, I made an error. Let me redo:

```
  5:15:20
- 2:30:45
---------
```

Seconds: 20 - 45 needs borrowing
- Borrow from minutes: 20 + 60 = 80
- 80 - 45 = 35
- Minutes: 15 - 1 = 14

Minutes: 14 - 30 needs borrowing
- Borrow from hours: 14 + 60 = 74
- 74 - 30 = 44
- Hours: 5 - 1 = 4

Hours: 4 - 2 = 2

Result: 2:44:35

Verify:
- 5:15:20 = (5 × 3600) + (15 × 60) + 20 = 18,000 + 900 + 20 = 18,920 seconds
- 2:30:45 = (2 × 3600) + (30 × 60) + 45 = 7,200 + 1,800 + 45 = 9,045 seconds
- 18,920 - 9,045 = 9,875 seconds
- Convert back: 9,875 ÷ 3600 = 2 remainder 1,675
- 1,675 ÷ 60 = 27 remainder 55

Hmm, getting 2:27:55. Let me recalculate the original...

5:15:20 seconds:
- 5 hours = 5 × 3600 = 18,000
- 15 minutes = 15 × 60 = 900
- 20 seconds = 20
- Total: 18,920

2:30:45 seconds:
- 2 hours = 2 × 3600 = 7,200
- 30 minutes = 30 × 60 = 1,800
- 45 seconds = 45
- Total: 9,045

18,920 - 9,045 = 9,875

Convert 9,875 to H:M:S:
- 9,875 ÷ 3600 = 2.743... → 2 hours
- 9,875 - 7,200 = 2,675 seconds remaining
- 2,675 ÷ 60 = 44.58... → 44 minutes
- 2,675 - 2,640 = 35 seconds

So: 2:44:35 ✓ (my arithmetic was correct)

## Dividing Time: Sexagesimal Fractions

**Example:** What is half of 1:30:00?

```
1:30:00 ÷ 2 = ?
```

Method 1: Convert to seconds, divide, convert back
- 1:30:00 = 5,400 seconds
- 5,400 ÷ 2 = 2,700 seconds
- 2,700 ÷ 3600 = 0 hours remainder 2,700
- 2,700 ÷ 60 = 45 minutes
- Result: 0:45:00

Method 2: Divide each place
- 1 hour ÷ 2 = 0 hours with 1 hour remaining = 60 minutes remaining
- 60 minutes + 30 minutes = 90 minutes
- 90 minutes ÷ 2 = 45 minutes
- Result: 0:45:00

Both methods work!

## The Sexagesimal System in Astronomy

Ancient and medieval astronomers used sexagesimal extensively:

**Ptolemy's Almagest** (2nd century CE) expressed astronomical measurements in degrees, minutes, seconds—even "thirds" and "fourths" (continuing the 60-based subdivision).

Example: A planetary position might be written:
```
45° 23' 16" 42''' 10''''
```

That's degrees, minutes, seconds, thirds (1/60 of a second), and fourths (1/60 of a third)!

Modern astronomy switched to decimal degrees for most purposes, but when specifying precise sky coordinates, DMS (degrees, minutes, seconds) notation persists.

## Why Sexagesimal Survived

Most ancient number systems disappeared. Roman numerals persist only ceremonially (Super Bowl LVIII, chapter numbers). Babylonian cuneiform is a museum curiosity.

But base-60? Still here, still essential, 4,000 years later.

Why?

**1. Network Effects**
Once everyone uses 60-minute hours, changing becomes impossible. Every clock, every schedule, every time zone, every train/plane/bus timetable would need updating.

**2. Mathematical Utility**
360 degrees with sexagesimal subdivision remains incredibly practical for navigation, surveying, astronomy, and engineering.

**3. Cultural Inertia**
We teach children to tell time using sexagesimal. It's embedded in language ("quarter past," "half past"), culture, and infrastructure.

**4. No Compelling Alternative**
Decimal time has been tried (French Revolutionary calendar had 10-day weeks, 10-hour days). It failed because the gains weren't worth the disruption.

Sexagesimal might not be "optimal" in some abstract sense, but it's "good enough" and universally established—a powerful combination.

## Decimal Time: The Failed Revolution

During the French Revolution, revolutionaries tried to decimalize everything, including time:

**Decimal Time (French Revolutionary):**
- 10-day weeks
- 10 hours per day
- 100 minutes per hour
- 100 seconds per minute

It... didn't catch on. Reasons:
- Required replacing every clock
- Broke compatibility with rest of world
- 10-hour days meant each "hour" was 2.4 standard hours (confusing)
- People liked their 7-day weeks (religious/cultural reasons)

The metric system succeeded because:
- Scientific measurements needed standardization
- No strong cultural attachment to "18 inches = 1 foot" type rules
- International cooperation supported it

But time and angles? Too embedded. The Babylonians' legacy proved too strong.

## The Beauty of 60

Let's appreciate base-60's divisors one more time:

```
60 ÷ 1 = 60
60 ÷ 2 = 30
60 ÷ 3 = 20
60 ÷ 4 = 15
60 ÷ 5 = 12
60 ÷ 6 = 10
60 ÷ 10 = 6
60 ÷ 12 = 5
60 ÷ 15 = 4
60 ÷ 20 = 3
60 ÷ 30 = 2
60 ÷ 60 = 1
```

Every common small number (2, 3, 4, 5, 6) divides evenly into 60. For a pre-calculator, pre-computer society, this is magnificent.

Want to split something six ways? 60 ÷ 6 = 10. Easy.
Want thirds? 60 ÷ 3 = 20. Done.
Want to find a quarter? 60 ÷ 4 = 15. Perfect.

The Babylonians chose wisely.

## Conclusion: Ancient Wisdom, Modern Use

Sexagesimal is a testament to the sophistication of ancient mathematics. The Sumerians and Babylonians, working with clay tablets and styluses 4,000 years ago, designed a number system so robust and practical that we still use it every single day.

Every time you:
- Check the time
- Measure an angle
- Use GPS coordinates
- Navigate by compass bearing
- Calculate astronomical positions

...you're using Babylonian mathematics.

Not as a curiosity. Not as a historical footnote. As the actual, practical, universal standard.

That's legacy.

In our next chapter, we'll explore other number systems—some historical, some modern, some whimsical. We'll look at base-20 (Mayan), base-64 (computing), base-φ (theoretical), and more. But after exploring binary's computer dominance, duodecimal's "what if," and sexagesimal's eternal persistence, we've covered the heavy hitters.

Now it's time for the variety show.

---

**Coming Up Next:** Chapter 7 - Other Bases and Applications (where we explore the wild world of alternative number systems)
