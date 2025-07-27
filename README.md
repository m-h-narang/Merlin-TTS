# Merlin TTS on Hábrók — Speech Synthesis

This project customizes the Merlin TTS implementation for training and inference on the Hábrók cluster as part of the Voice Technology MSc. 2024–2025 Speech Synthesis 2 course.

---

## Original Repository

The full codebase can be obtained by cloning the official Merlin repository:

https://github.com/CSTR-Edinburgh/merlin

---

## Project Description

This project focuses on training and fine-tuning the Merlin TTS system for statistical parametric speech synthesis using the CMU Arctic bdl dataset. It includes tasks such as:

- Training a “full voice” using the standard Merlin recipe on the CMU Arctic bdl dataset
- Running inference to synthesize test sentences from the trained model
- Experimenting with different feedforward network architectures for the acoustic model to observe the impact of the number of hidden layers and hidden units
- Comparing model performance using metrics such as MCD, BAP, V/UV error rates, and RMSE of log-f0

---

## What This Repository Contains

This folder only includes modified or newly created files relevant to the project.
To access the complete codebase, clone the repository from the link above.

Key changes in this project include:

- Adjustments for running Merlin in a containerized environment on Hábrók
- Scripts for training the full voice model on the CMU Arctic bdl dataset
- Configurations for training multiple acoustic model architectures for comparison
- Generated synthesis outputs for each experimental setup

---

## How to Run

1. Clone the Original Repository

```bash
git clone https://github.com/CSTR-Edinburgh/merlin.git
cd merlin
```

2. Compile Tools

```bash
bash tools/compile_tools.sh
```

3. Start Container on Hábrók (bind Merlin directory and enable GPU)

```bash
apptainer shell --nv --bind <PATH_TO_YOUR_MERLIN>:/merlin merlin-tts_Habrok_tutorial.sif
```

4. Train the Full Voice

```bash
bash egs/cmu_arctic/s1/run_full_voice.sh
```

5. Perform Inference

Synthesized waveforms will be generated in the experiment’s test_synthesis/wav folder after training.

6. Experiment with Acoustic Model Architectures

Modify the number of hidden layers and units in the configuration files and retrain using the same dataset and recipe to compare model performance.

---

## Language

The project was developed using the CMU Arctic bdl dataset for English speech synthesis.

