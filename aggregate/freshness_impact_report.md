# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-04 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.5 | 16.7% | 0.463 | 0.2 |       22 | 100.0% |  30.8% | 1.7× | 0.0% |   0.5909 |
|       OK |   12 |   36.1 | 8.3% | 0.413 | 0.1 |       12 | 100.0% |  33.3% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   20 |  152.0 | 0.0% | 0.351 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   56 |   67.4 | 8.9% | 0.412 | 0.1 |       52 | 100.0% |  26.3% | 2.7× | 0.0% |   0.3654 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.5 | 0.0% | 0.472 | 0.0 |       22 |    - |   0.0% |    - | 0.0% |   0.1818 |
|       OK |   12 |   36.1 | 0.0% | 0.384 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   20 |  152.0 | 0.0% | 0.320 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   56 |   67.4 | 0.0% | 0.399 | 0.0 |       52 |    - |   0.0% |    - | 0.0% |   0.0962 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   24 |   12.5 | 8.3% | 0.604 | 0.1 |       22 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |   12 |   36.1 | 8.3% | 0.522 | 0.1 |       12 | 0.0% |      - |    - | 8.3% |   0.0000 |
| DEGRADED |   20 |  152.0 | 0.0% | 0.429 | 0.0 |       18 |    - |   0.0% |    - | 0.0% |   0.0556 |
|      ALL |   56 |   67.4 | 5.4% | 0.524 | 0.1 |       52 | 0.0% |   0.0% |    - | 6.1% |   0.0577 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.3 | 36.4% | 0.639 | 0.5 |        9 | 100.0% |  66.7% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   36.4 | 25.0% | 0.515 | 0.2 |        4 | 100.0% | 100.0% | 4.0× | 0.0% |   0.2500 |
| DEGRADED |   16 |  168.5 | 0.0% | 0.358 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   95.3 | 16.1% | 0.478 | 0.2 |       27 | 100.0% |  55.6% | 3.0× | 0.0% |   0.3333 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.3 | 0.0% | 0.595 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   36.4 | 0.0% | 0.392 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.5 | 0.0% | 0.315 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.3 | 0.0% | 0.424 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   10.3 | 18.2% | 0.676 | 0.2 |        9 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|       OK |    4 |   36.4 | 0.0% | 0.463 | 0.0 |        4 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   16 |  168.5 | 0.0% | 0.422 | 0.0 |       14 |    - |   0.0% |    - | 0.0% |   0.0714 |
|      ALL |   31 |   95.3 | 6.5% | 0.518 | 0.1 |       27 | 0.0% |   0.0% |    - | 8.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available