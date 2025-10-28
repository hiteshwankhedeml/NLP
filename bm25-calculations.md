---
hidden: true
---

# ✈️ BM25 - Calculations

## BM25 Example with Step-by-Step Calculations in Tabular Format

### BM25 Formula

```
BM25(q,d) = Σ IDF(qi) × (tf(qi,d) × (k1 + 1)) / (tf(qi,d) + k1 × (1 - b + b × |d|/avgdl))
```

Where:

* `tf(qi,d)` = term frequency of query term qi in document d
* `IDF(qi)` = inverse document frequency of term qi
* `|d|` = length of document d in words
* `avgdl` = average document length in the corpus
* `k1` = term frequency saturation parameter (typically 1.2-2.0)
* `b` = length normalization parameter (typically 0.75)

### Example Setup

**Document Collection:**

* D1: "the cat sat on the mat"
* D2: "the dog ran in the park"
* D3: "cats and dogs are pets"

**Query:** "cat dog" **Parameters:** k1 = 1.2, b = 0.75

### Step 1: Document Statistics

| Document    | Content                   | Length   |
| ----------- | ------------------------- | -------- |
| D1          | "the cat sat on the mat"  | 6        |
| D2          | "the dog ran in the park" | 6        |
| D3          | "cats and dogs are pets"  | 5        |
| **Average** |                           | **5.67** |

### Step 2: Term Frequency Matrix

| Document          | tf("cat") | tf("dog") |
| ----------------- | --------- | --------- |
| D1                | 1         | 0         |
| D2                | 0         | 1         |
| D3                | 0         | 0         |
| **df (doc freq)** | **1**     | **1**     |

### Step 3: IDF Calculations

| Term  | df | N - df + 0.5 | df + 0.5 | (N-df+0.5)/(df+0.5) | IDF = log(...) |
| ----- | -- | ------------ | -------- | ------------------- | -------------- |
| "cat" | 1  | 2.5          | 1.5      | 1.667               | 0.511          |
| "dog" | 1  | 2.5          | 1.5      | 1.667               | 0.511          |

### Step 4: Length Normalization Factor Calculations

| Document | Length | Length/avgdl | b × (Length/avgdl) | 1-b+b×(Length/avgdl) | k1×(1-b+b×(Length/avgdl)) |
| -------- | ------ | ------------ | ------------------ | -------------------- | ------------------------- |
| D1       | 6      | 1.059        | 0.794              | 1.044                | 1.253                     |
| D2       | 6      | 1.059        | 0.794              | 1.044                | 1.253                     |
| D3       | 5      | 0.882        | 0.661              | 0.911                | 1.093                     |

**Calculation details:**

* avgdl = 5.67
* b = 0.75
* k1 = 1.2
* For D1: 6/5.67 = 1.059, then 0.75×1.059 = 0.794, then 1-0.75+0.794 = 1.044, then 1.2×1.044 = 1.253

### Step 5: BM25 Component Calculations

#### For Document D1 and term "cat":

| Component       | Value     | Formula              |
| --------------- | --------- | -------------------- |
| tf              | 1         | count of "cat" in D1 |
| k1 + 1          | 2.2       | 1.2 + 1              |
| tf × (k1 + 1)   | 2.2       | 1 × 2.2              |
| Denominator     | 2.253     | tf + k1×(1-b+b×      |
| TF component    | 0.977     | 2.2 / 2.253          |
| IDF             | 0.511     | from table above     |
| **Final score** | **0.499** | 0.511 × 0.977        |

#### Complete BM25 Score Matrix

| Document | Term "cat" |         |       | Term "dog" |         |       | **Total** |
| -------- | ---------- | ------- | ----- | ---------- | ------- | ----- | --------- |
|          | tf         | TF comp | Score | tf         | TF comp | Score |           |
| D1       | 1          | 0.977   | 0.499 | 0          | 0.000   | 0.000 | **0.499** |
| D2       | 0          | 0.000   | 0.000 | 1          | 0.977   | 0.499 | **0.499** |
| D3       | 0          | 0.000   | 0.000 | 0          | 0.000   | 0.000 | **0.000** |

Where TF comp = (tf × (k1 + 1)) / (tf + k1 × (1 - b + b × |d|/avgdl))

### Step 6: Final Rankings

| Rank    | Document | BM25 Score | Content                   |
| ------- | -------- | ---------- | ------------------------- |
| 1 (tie) | D1       | 0.499      | "the cat sat on the mat"  |
| 1 (tie) | D2       | 0.499      | "the dog ran in the park" |
| 3       | D3       | 0.000      | "cats and dogs are pets"  |

### Key Observations

1. **Length normalization**: Documents D1 and D2 are slightly longer than average, so their scores are penalized by the length normalization factor.
2. **Term frequency saturation**: With k1=1.2, the contribution of term frequency saturates quickly. A term appearing twice would have diminishing returns.
3. **Exact matching**: Without stemming, "cats" and "dogs" don't match "cat" and "dog", resulting in zero scores for D3.
4. **IDF impact**: Since both "cat" and "dog" appear in only one document each, they have the same IDF value and contribute equally to the final scores.

### Practical Considerations

In real implementations:

* Stemming/lemmatization would match "cats"→"cat" and "dogs"→"dog"
* Stop words like "the", "and", "are" are often removed
* Larger corpora produce more meaningful IDF differences
* Parameters k1 and b are often tuned for specific domains
