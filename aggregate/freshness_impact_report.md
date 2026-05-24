# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-24 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (13.3%) is 2.0× the overall rate (6.6%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 13.3% | 0.442 | 0.2 |       29 | 100.0% |  26.7% | 1.9× | 0.0% |   0.5172 |
|       OK |   19 |   36.1 | 5.3% | 0.385 | 0.1 |       17 | 100.0% |  33.3% | 5.7× | 0.0% |   0.1765 |
| DEGRADED |   27 |  129.6 | 0.0% | 0.354 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1923 |
|      ALL |   76 |   60.2 | 6.6% | 0.396 | 0.1 |       72 | 100.0% |  21.7% | 3.1× | 0.0% |   0.3194 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 0.0% | 0.430 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1379 |
|       OK |   19 |   36.1 | 0.0% | 0.331 | 0.0 |       17 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   27 |  129.6 | 0.0% | 0.305 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   76 |   60.2 | 0.0% | 0.361 | 0.0 |       72 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 6.7% | 0.590 | 0.1 |       29 | 0.0% |   0.0% |    - | 7.4% |   0.0690 |
|       OK |   19 |   36.1 | 5.3% | 0.530 | 0.1 |       17 | 0.0% |      - |    - | 5.9% |   0.0000 |
| DEGRADED |   27 |  129.6 | 0.0% | 0.460 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |
|      ALL |   76 |   60.2 | 4.0% | 0.529 | 0.0 |       72 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.2 | 28.6% | 0.557 | 0.4 |       13 | 100.0% |  57.1% | 1.9× | 0.0% |   0.5385 |
|       OK |    8 |   36.6 | 0.0% | 0.357 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   67.9 | 0.0% | 0.386 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   34.6 | 12.9% | 0.456 | 0.2 |       27 | 100.0% |  44.4% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.2 | 0.0% | 0.493 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    8 |   36.6 | 0.0% | 0.254 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   67.9 | 0.0% | 0.264 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   34.6 | 0.0% | 0.365 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   14 |   12.2 | 14.3% | 0.658 | 0.1 |       13 | 0.0% |   0.0% |    - | 16.7% |   0.0769 |
|       OK |    8 |   36.6 | 0.0% | 0.540 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    9 |   67.9 | 0.0% | 0.549 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   34.6 | 6.5% | 0.596 | 0.1 |       27 | 0.0% |   0.0% |    - | 7.7% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available