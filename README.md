# Honest vs. Misleading Visualizations

## Objective
This project demonstrates how identical data can be visually manipulated to tell contradictory stories, and establishes a rigorous, honesty-first workflow for economic data visualization.

## Methodology
- Recreated Anscombe's Quartet: four datasets sharing identical means, variances, and correlation coefficients (r ≈ 0.816) despite radically different underlying shapes and relationships
- Quantified chart distortion using Edward Tufte's Lie Factor metric, calculating a Lie Factor of **49.0** for a truncated-axis revenue chart — meaning the chart visually overstated a real 4.1% change as an apparent 200% change — then redesigned the chart as an honest, zero-based dot plot
- Constructed four distinct visualizations of the same real average hourly earnings series (FRED AHETPI, deflated to 2020 dollars), demonstrating how axis truncation, cherry-picked time windows, and log-scale transformations each produce a materially different narrative from one dataset
- Executed a systematic four-step exploratory data analysis (EDA) checklist — structure, distributions, relationships, and anomalies — on World Bank GDP data spanning **262 countries** across **64 years** (1960–2023), including diagnosis of right-skewed distributions requiring log transformation and identification of non-random (MNAR) missing-data patterns concentrated at the start and end of the panel
- Built an interactive dashboard (ipywidgets + matplotlib) allowing real-time toggling between nominal and real earnings, adjustable y-axis floors, variable time windows, and linear/log scaling, with a live-updating Lie Factor readout

## Key Findings
- Summary statistics alone are insufficient for data validation: Anscombe's Quartet proves near-identical statistical profiles can mask fundamentally different data-generating processes, underscoring that visualization must precede — not follow — statistical inference
- Axis manipulation is a powerful and easily deployed tool for misrepresentation: a Lie Factor of 49.0 shows how a modest 4% real-world change can be rendered as a 200% visual swing through simple y-axis truncation
- Real (inflation-adjusted) wage series and nominal series diverge sharply in narrative: nominal average hourly earnings rose more than twelvefold over six decades, while real earnings rose only about 20%, with a multi-decade decline through the middle of the period — a distinction that materially changes any policy or negotiation argument built on the data
- Missingness in the World Bank panel is not random (MNAR): data gaps cluster at the earliest and most recent years, reflecting real-world constraints such as newly independent states and reporting lags rather than arbitrary omission
- Every chart embeds a rhetorical choice — the appropriate framing depends on the intended audience and claim, and defensible analysis requires disclosing that choice rather than concealing it
