<p align="center">
  <img src="https://raw.githubusercontent.com/SauravSunish/SauravSunish/main/assets/systems-banner.png" alt="Saurav Sunish portfolio banner" width="100%" />
</p>

<h1 align="center">Saurav Sunish</h1>

<p align="center">
  <strong>Project Portfolio</strong><br/>
  Web systems · Applied machine learning · Explainable prototypes
</p>

---

I build academic and personal projects to understand how an idea moves from **logic → interface → working prototype**. I document what works, how it works, and where the limitations are.

## Featured Projects

### 01. SmartBus — Bus Booking Prototype

**[View repository →](https://github.com/SauravSunish/mini-project-sonajafy)**

A PHP/MySQL application with seat inventory, booking flow, QR e-tickets, a route-progress screen, and an experimental sunlight-based seat recommendation.

`PHP` · `MySQL` · `JavaScript` · `Bootstrap` · `SunCalc`

**Key idea:** recommend the side of a bus with lower sun exposure using the journey time, approximate route bearing, and solar position.

<details>
<summary><strong>How it works and what I can explain</strong></summary>

<br/>

1. Source and destination names map to stored latitude/longitude coordinates.
2. JavaScript calculates an approximate bearing between those coordinates.
3. SunCalc returns solar azimuth and altitude for the selected departure time.
4. The relative angle determines whether the left or right side is recommended.
5. At night all seats remain available; near high noon, aisle seats are preferred.

The route-progress screen polls a PHP endpoint every eight seconds. It demonstrates periodic UI updates; it is not a production GPS implementation.

I can walk through prepared statements, PHP-to-JavaScript JSON, booked-seat state, responsive seat layouts, QR generation, polling, and the recommendation logic.

**Limitation:** the current heuristic uses a straight source-to-destination bearing and the journey start time. A production version would use actual route geometry and recalculate exposure during the trip.

</details>

---

### 02. BERT Fine-Tuning on SST-2

**[View repository →](https://github.com/SauravSunish/AIpro)**

An academic sentiment-classification experiment that fine-tunes `bert-base-uncased` on SST-2 and provides a separate inference path for inspecting multi-head self-attention.

`Python` · `PyTorch` · `Transformers` · `Datasets` · `scikit-learn`

**Key idea:** build a reproducible training workflow while treating attention plots as observations—not causal explanations.

<details>
<summary><strong>How it works and what I can explain</strong></summary>

<br/>

The pipeline loads pinned model and dataset revisions, tokenizes with dynamic batch padding, fine-tunes with Hugging Face `Trainer`, evaluates accuracy/precision/recall/F1, and saves the model plus run metadata. A separate inference path reloads the model and exports attention heatmaps.

I can discuss transfer learning, tokenization, padding, train/validation separation, deterministic seeds, evaluation metrics, smoke tests, and the limitations of attention visualization.

**Limitation:** attention weights show internal routing patterns; they do not prove that a token caused a prediction. The corrected pipeline should be rerun before historical checkpoint metrics are presented as final results.

</details>

---

## Current Focus

```text
Comfortable with → PHP, MySQL, JavaScript, Python project workflows
Learning deeply  → NLP, model evaluation, explainability limitations
Working toward   → smaller claims, stronger evidence, better-tested software
```

> I prefer a working prototype I understand over a larger system I cannot defend.

<p align="center">
  <sub>Every highlighted project links to code I can walk through.</sub>
</p>
