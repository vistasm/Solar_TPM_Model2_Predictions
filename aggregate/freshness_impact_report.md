# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-26 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (13.3%) is 2.1× the overall rate (6.4%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 13.3% | 0.442 | 0.2 |       29 | 100.0% |  26.7% | 1.9× | 0.0% |   0.5172 |
|       OK |   19 |   36.1 | 5.3% | 0.385 | 0.1 |       18 | 100.0% |  33.3% | 6.0× | 0.0% |   0.1667 |
| DEGRADED |   29 |  126.1 | 0.0% | 0.362 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |
|      ALL |   78 |   60.7 | 6.4% | 0.399 | 0.1 |       74 | 100.0% |  20.8% | 3.1× | 0.0% |   0.3243 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 0.0% | 0.430 | 0.0 |       29 |    - |   0.0% |    - | 0.0% |   0.1379 |
|       OK |   19 |   36.1 | 0.0% | 0.331 | 0.0 |       18 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   29 |  126.1 | 0.0% | 0.313 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |
|      ALL |   78 |   60.7 | 0.0% | 0.362 | 0.0 |       74 |    - |   0.0% |    - | 0.0% |   0.0811 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   30 |   13.0 | 6.7% | 0.590 | 0.1 |       29 | 0.0% |   0.0% |    - | 7.4% |   0.0690 |
|       OK |   19 |   36.1 | 5.3% | 0.530 | 0.1 |       18 | 0.0% |      - |    - | 5.6% |   0.0000 |
| DEGRADED |   29 |  126.1 | 0.0% | 0.469 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |
|      ALL |   78 |   60.7 | 3.9% | 0.530 | 0.0 |       74 | 0.0% |   0.0% |    - | 4.2% |   0.0405 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 25.0% | 0.516 | 0.2 |       11 | 100.0% |  60.0% | 2.2× | 0.0% |   0.4545 |
|       OK |    8 |   36.6 | 0.0% | 0.357 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   70.0 | 0.0% | 0.402 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   39.2 | 9.7% | 0.435 | 0.1 |       27 | 100.0% |  37.5% | 3.4× | 0.0% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 0.0% | 0.433 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|       OK |    8 |   36.6 | 0.0% | 0.254 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   70.0 | 0.0% | 0.292 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|      ALL |   31 |   39.2 | 0.0% | 0.337 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   12 |   12.8 | 8.3% | 0.632 | 0.1 |       11 | 0.0% |      - |    - | 9.1% |   0.0000 |
|       OK |    8 |   36.6 | 0.0% | 0.540 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |   70.0 | 0.0% | 0.556 | 0.0 |        9 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   39.2 | 3.2% | 0.581 | 0.0 |       27 | 0.0% |      - |    - | 3.7% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available