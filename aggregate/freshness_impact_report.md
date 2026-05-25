# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-25 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (13.3%) is 2.1× the overall rate (6.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 13.3% | 0.442 | 0.2 |       29 | 100.0% |  26.7% | 1.9× | 0.0% |   0.5172 |
|       OK |   19 |   36.1 | 5.3% | 0.385 | 0.1 |       18 | 100.0% |  33.3% | 6.0× | 0.0% |   0.1667 |
| DEGRADED |   28 |  127.4 | 0.0% | 0.361 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.1923 |
|      ALL |   77 |   60.3 | 6.5% | 0.399 | 0.1 |       73 | 100.0% |  21.7% | 3.2× | 0.0% |   0.3151 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 0.0% | 0.430 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1379 |
|       OK |   19 |   36.1 | 0.0% | 0.331 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   28 |  127.4 | 0.0% | 0.312 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0769 |
|      ALL |   77 |   60.3 | 0.0% | 0.363 | 0.0 |       73 |    - |   0.0% |    - | 0.0% |   0.0822 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 6.7% | 0.590 | 0.1 |       29 | 0.0% |   0.0% |    - | 7.4% |   0.0690 |
|       OK |   19 |   36.1 | 5.3% | 0.530 | 0.1 |       18 | 0.0% |      - |    - | 5.6% |   0.0000 |
| DEGRADED |   28 |  127.4 | 0.0% | 0.466 | 0.0 |       26 |    - |   0.0% |    - | 0.0% |   0.0385 |
|      ALL |   77 |   60.3 | 3.9% | 0.530 | 0.0 |       73 | 0.0% |   0.0% |    - | 4.3% |   0.0411 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.7 | 30.8% | 0.544 | 0.4 |       12 | 100.0% |  66.7% | 2.0× | 0.0% |   0.5000 |
|       OK |    8 |   36.6 | 0.0% | 0.357 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   67.8 | 0.0% | 0.403 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   36.7 | 12.9% | 0.451 | 0.2 |       27 | 100.0% |  50.0% | 3.4× | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.7 | 0.0% | 0.467 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|       OK |    8 |   36.6 | 0.0% | 0.254 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   67.8 | 0.0% | 0.289 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   36.7 | 0.0% | 0.355 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   13 |   12.7 | 15.4% | 0.654 | 0.1 |       12 | 0.0% |      - |    - | 16.7% |   0.0000 |
|       OK |    8 |   36.6 | 0.0% | 0.540 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   10 |   67.8 | 0.0% | 0.556 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   36.7 | 6.5% | 0.593 | 0.1 |       27 | 0.0% |      - |    - | 7.4% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available