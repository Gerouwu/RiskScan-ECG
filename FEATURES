RiskScan ECG — Feature Set v1

This document defines the official feature architecture for the RiskScan ECG MVP. It serves as the foundational blueprint for transforming raw ECG signals into structured, clinically meaningful features that support automated risk classification for ischemia, myocardial infarction, and arrhythmic conditions.

The goal is not only to list features but also to explain the clinical reasoning, signal-processing logic, and design choices behind each block. This ensures transparency, reproducibility, and long-term scalability.

All features are extracted from 10-second, 12-lead ECG recordings, processed at a standardized sampling rate of 500 Hz, consistent with modern electrocardiographs and major research datasets.

 1. Signal-Level Features

Direct measurements taken from the ECG waveform after filtering, baseline stabilization, and noise reduction.

1.1 Intervals

Heart rate (HR)

Mean RR interval

PR interval

QRS duration

QT and QTc

Simple RR variability

1.2 Amplitudes

R-wave amplitude

S-wave amplitude

T-wave amplitude

1.3 Axis and Voltage

QRS electrical axis (approximate)

Total QRS voltage

R/S ratio per lead

1.4 Signal Quality

Noise index

Baseline wander index

Percentage of clipping or saturation

Muscle artifact detection

Lead-level quality scoring

 2. Morphology Features

Anatomical characteristics of the P-QRS-T complex.

2.1 Rhythm

Rhythm regularity

Atrial fibrillation suspicion

Ectopic beat detection

2.2 P-QRS-T Morphology

QRS width and morphology

P-wave shape

T-wave polarity (positive/negative/biphasic)

T-wave symmetry

2.3 Pathological Q Waves

Q waves > 40 ms

QS complexes

Territory-specific pathological Q patterns

 3. Ischemia & Infarction Features

Core features used for detecting ischemia and myocardial infarction.

3.1 ST Level per Lead

ST elevation (mV)

ST depression (mV)

ST level relative to baseline

3.2 ST Morphology

Convex

Straight

Upsloping

Downsloping

Horizontal

3.3 Contiguous Territories

Inferior: II, III, aVF

Anterior: V1–V4

Lateral: I, aVL, V5, V6

3.4 Reciprocal Changes

Reciprocal ST depression

Opposing-territory confirmation

3.5 Additional Ischemic Markers

T-wave inversion

Hyperacute T-waves

 4. Clinical Context Features

Minimal but essential clinical information that modifies risk classification.

4.1 Demographics

Age

Sex

4.2 Symptoms

Chest pain (yes/no)

Syncope/presyncope (yes/no)

4.3 Medical History

Prior myocardial infarction

Diabetes

Hypertension

 5. Derived Risk Features

Internally computed features created by combining multiple signal-level and clinical variables.

5.1 Internal Scores

Ischemia score (0–10)

Infarction score (0–10)

Arrhythmia score (0–10)

5.2 Clinical Flags

STEMI likely

Ischemia likely

Poor-quality ECG detected

5.3 Final Risk Classification

Low risk

Intermediate risk

High risk

Critical risk

 Recording Specifications (MVP Standard)

All features in this MVP are extracted under the following recording conditions:

Window Duration

10-second ECG window (standard clinical acquisition)

Sampling Frequency

500 Hz sampling rate (standard across many modern ECG devices and public datasets)

If datasets provide 250 Hz, they will be resampled to 500 Hz unless otherwise required

CSV Format

One row per ECG recording

Each column represents a feature

Include an ecg_id and the output label (risk_label or diagnosis)
