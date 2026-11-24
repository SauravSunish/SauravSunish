<p align="center">
  <img src="./assets/systems-banner.png" alt="Abstract systems map connecting neural attention and transit routes" width="100%" />
</p>

<h1 align="center">SAURAV / BUILD NOTES</h1>

<p align="center">
  <code>web systems</code> · <code>applied ML</code> · <code>ideas I can explain end to end</code>
</p>

---

I build academic and personal projects to understand how an idea moves from **logic → interface → working prototype**.

The two projects below are the best examples of how I currently think and build.

### 01 — ROUTE / LIGHT / CHOICE

**[SmartBus →](https://github.com/SauravSunish/mini-project-sonajafy)**  
A PHP/MySQL bus-booking prototype with seat inventory, booking flow, QR e-tickets, a route-progress view, and a sunlight-based seat recommendation experiment.

#### How the sunlight recommendation works

1. The source and destination are mapped to stored latitude/longitude coordinates.
2. The client calculates an approximate route bearing between those points.
3. SunCalc returns solar azimuth and altitude for the selected departure time.
4. The relative angle between the route and sun is used to recommend the left or right side.
5. At night all seats remain available; near high noon, aisle seats are preferred.

The tracking screen polls a PHP endpoint every eight seconds and renders progress between route stops. It is a prototype of near-real-time UI updates—not a production GPS platform.

`PHP` `MySQL` `JavaScript` `Bootstrap` `SunCalc`

**What I can discuss:** prepared statements, server-to-client JSON, booked-seat state, responsive seat layouts, QR generation, polling, and the trade-offs in the sunlight heuristic.

**Known limitation:** the recommendation uses a straight source-to-destination bearing and the journey start time. A production version should follow the actual route geometry and recompute sun exposure throughout the trip.

---

### 02 — TOKENS / ATTENTION / EVIDENCE

**[BERT × SST-2 →](https://github.com/SauravSunish/AIpro)**  
An academic sentiment-classification experiment that fine-tunes `bert-base-uncased` on SST-2 and provides a separate inference path for inspecting multi-head self-attention.

#### What the pipeline actually does

1. Loads pinned revisions of the model and GLUE/SST-2 dataset.
2. Tokenizes with truncation and dynamic batch padding.
3. Fine-tunes with Hugging Face `Trainer`.
4. Evaluates accuracy, precision, recall, and F1.
5. Saves the model, tokenizer, metrics, state, and run metadata.
6. Reloads the trained model for inference and exports attention heatmaps.

`Python` `PyTorch` `Transformers` `Datasets` `scikit-learn`

**What I can discuss:** transfer learning, tokenization, padding, train/validation separation, deterministic seeds, evaluation metrics, fast smoke tests, and why attention is useful to inspect.

**Known limitation:** attention weights show internal routing patterns; they are not proof that a token caused the prediction. The corrected pipeline should be rerun before presenting historical checkpoint metrics as final experimental results.

---

### CURRENT COORDINATES

```text
comfortable with → PHP, MySQL, JavaScript, Python project workflows
learning deeply  → NLP, model evaluation, explainability limitations
working toward   → smaller claims, stronger evidence, better-tested software
```

### HOW I APPROACH A PROJECT

- I start with one concrete problem and make the mechanism visible.
- I document both the implementation and its limits.
- I prefer a working prototype I understand over a larger system I cannot defend.
- If I do not know something, I treat that as the next question—not something to hide.

<p align="center">
  <sub>Everything highlighted here links to code I can walk through.</sub>
</p>
