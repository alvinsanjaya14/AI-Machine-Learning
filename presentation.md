---
marp: true
theme: uncover
class: invert
paginate: true
backgroundColor: #0d1117
color: #e6edf3
style: |
  section {
    background: linear-gradient(160deg, #0d1117 0%, #161b22 100%);
    color: #e6edf3;
    font-size: 30px;
    text-align: left;
    justify-content: flex-start;
    padding: 60px 70px;
  }
  h1 {
    color: #58a6ff;
    font-size: 54px;
  }
  h2 {
    color: #58a6ff;
    border-bottom: 2px solid #30363d;
    padding-bottom: 12px;
  }
  h3 { color: #79c0ff; }
  strong { color: #ffa657; }
  em { color: #7ee787; }
  a { color: #58a6ff; }
  blockquote {
    border-left: 4px solid #58a6ff;
    background: #161b22;
    padding: 10px 20px;
    color: #adbac7;
    font-style: italic;
  }
  ul, ol { line-height: 1.5; }
  code {
    background: #161b22;
    color: #ffa657;
    padding: 2px 6px;
    border-radius: 4px;
  }
  section.lead { text-align: center; justify-content: center; }
  section.lead h1 { font-size: 60px; }
  footer { color: #6e7681; }
  section::after {
    color: #6e7681;
    font-size: 18px;
  }
---

<!--
Format note: Each "---" separates a slide. Text inside HTML comments (like this one)
is a presenter note — visible in Marp presenter view but NOT on the slide.
To export: run `marp presentation.md --pdf` (or --pptx / --html), or use the Marp for VS Code extension.
-->

<!-- _class: lead invert -->

# A Brief Story of AI Implementation in Industry

**Setia Budi**
Machine Learning Engineer at tiket.com

<!--
Keep it warm and personal for the first 30 seconds — you want the room relaxed.
Set expectations: "By the end, you'll know what an ML engineer really does day-to-day,
and 3–4 concrete things you can start doing this semester."
-->

---

## Introduction

- Hi everyone, my name is **Setia Budi**.
- I'm a **Machine Learning Engineer at tiket.com** — one of the most loved Online Travel Agents in Indonesia.
- Today's goal: a real, practical look at how **AI/ML actually works in industry** — and how to prepare for it before you graduate.
- Please **interrupt and ask questions at any point.** This is a conversation, not a lecture.

<!--
Ask a quick show of hands: "Who here has trained a model in a course project?"
— this tells you how technical to go.
-->

---

## Agenda

1. Why data (and AI) matters in business
2. What AI in industry actually looks like
3. The role of an ML/AI Engineer
4. How AI services are deployed
5. The common industry tech stack
6. Technical demo: from model to live API
7. Fundamental skills that matter
8. **How to prepare before graduation**
9. Q&A

<!--
Signpost the flow so students know the "career prep" payoff is coming
— it keeps them engaged through the technical middle.
-->

---

## Data is the New Oil

- Ever heard the slogan **"Data is the new oil"**?
- What does it actually mean?
  - Like oil, **raw data is not valuable by itself** — it must be *refined*.
  - Refining = collecting, cleaning, storing, turning data into **decisions and products**.
  - The companies that refine data best **win their markets**.

<!--
Ask the room what they think it means before revealing.
Example: "Every search you type, every hotel you click, every booking you cancel
— that's crude oil. Our job is to refine it into recommendations, pricing, and fraud detection."
Modern nuance: today it's less about HAVING data and more about USING it responsibly and fast.
-->

---

## AI in the Industry

- Is AI in industry **for real**, or just hype?
- Short answer: **very real** — but often invisible.
- Most production AI isn't a flashy robot; it's a quiet service making **millions of small decisions per day**.
- Where is AI already working behind the scenes in an app you used *today*?

<!--
Let students shout out examples (feeds, maps, spam filters, recommendations).
Key reframe: "The best AI in production is the AI you never notice."
Distinguish hype (demos) from value (reliable systems that move a business metric).
-->

---

## Objectives of AI in Industry

At the end of the day, business AI serves **two goals**:

- **Reduce operational cost** — automate repetitive human work (support, moderation, data entry).
- **Improve revenue** — better search, recommendations, pricing, and conversion.

A third, underrated one: **improve customer experience** (which feeds back into both).

<!--
Most important mindset slide for students: a model that doesn't move a business metric doesn't ship.
Accuracy is not the goal — IMPACT is. A 99% accurate model nobody uses is worth less
than a 90% model that saves the company money. Tie every later example back to "cost" or "revenue."
-->

---

## A Glimpse of AI in Industry

Real examples from an online travel / e-commerce context:

- **Search keyword autocomplete** — predict what the user wants to type
- **Product / hotel search ranking** — order results to maximize relevance & conversion
- **Cross-sell recommender** — "customers who booked this also booked…"
- **Review categorization** — auto-tag and summarize reviews
- **Image curation** — detect low-quality or wrong images at scale
- **Smart chatbot** — handle common support 24/7
- **Email / WhatsApp automation** — personalized/standardized, well-timed messaging

<!--
For each, quickly name the business goal: ranking → revenue, chatbot → cost, image curation → experience.
Pick ONE you've personally worked on and tell a 30-second story — real experience is what students remember.
-->

---

## The Role of an ML / AI Engineer

- **Develop production-ready AI services** — not notebooks, but reliable software.
- **Handle deployment** of those services into live systems.
- **Monitor** them after launch (performance, drift, cost, failures).

> The model is maybe **10–20%** of the job. The other 80% is **engineering**: data, pipelines, serving, testing, and monitoring.

<!--
Biggest surprise for students: industry ML ≠ Kaggle.
"In coursework, the model is the finish line. In industry, a trained model is the STARTING line."
An ML engineer owns the whole lifecycle, not just model.fit().
-->

---

## How AI Services Are Deployed

- **Synchronous (user-facing)** — real time, e.g. search ranking, autocomplete. Low latency is critical.
- **Asynchronous (batch)** — process large volumes offline, e.g. scoring millions of items overnight.
- **Scheduled** — runs daily / weekly / monthly, e.g. recomputing recommendations or retraining.

<!--
Mental model: "Do we need the answer NOW (sync), SOON in bulk (batch), or ON A CLOCK (scheduled)?"
Trade-offs: sync = strict latency & scaling; batch = throughput & cost efficiency.
-->

---

## Common AI Tech Stacks

The moving parts behind a production AI system:

- **Infrastructure** — where things run
- **Data Pipeline** — how data moves
- **MLOps** — how models are managed
- **LLMOps** — how LLM apps are managed
- **Development Tools** — how we build day-to-day

<!--
Reassure them: "You don't need to master all of these before graduating — but you should
RECOGNIZE them so you're not lost on day one." Next slides zoom into each.
-->

---

## Infrastructure

- **Cloud:** AWS, GCP, Azure, Alibaba Cloud
- **Databases:** PostgreSQL, MongoDB, Redis, Milvus, FalkorDB *(vector & graph stores for AI/RAG)*
- **Container orchestration:** Kubernetes
- **Deployment / delivery:** Jenkins, ArgoCD, Consul, Vault
- **Monitoring:** Grafana, Kibana

<!--
Don't read the whole list — call out the CATEGORIES: compute, storage, orchestration, delivery, observability.
Highlight that vector databases (Milvus) are newly essential because of LLMs and semantic search.
Advice: "Pick ONE cloud and get comfortable — the concepts transfer."
-->

---

## Data Pipeline

- **Batch pipelines:** Kubeflow, Apache Airflow, dbt
- **Streaming pipelines:** Apache Beam, Google Dataflow

<!--
Unglamorous truth: most ML work is data plumbing.
Batch = "process a big chunk on a schedule." Streaming = "process events as they arrive."
If a student learns just one thing here: SQL + Airflow — universally useful.
-->

---

## MLOps

- **Experiment tracking** — record every run, parameter, and metric for reproducibility.
- **Model registry** — version, stage, and promote models (dev → staging → prod).
- **Platform example:** MLflow

<!--
Define MLOps simply: "DevOps, but for machine learning."
Without tracking, you can't answer "which model is in production and how was it trained?"
— a real, scary question.
-->

---

## LLMOps

- **AI Gateway** — a single controlled entry point to LLM providers (routing, rate limits, cost, security).
- **Prompt registry** — version and manage prompts like code.
- **Platform example:** MLflow (with growing LLM support)

<!--
This category barely existed a few years ago — a great example of how fast this field moves.
"If you build with GPT/Claude APIs, you're already doing early LLMOps."
-->

---

## Development Tools

- **Editor / IDE:** Jupyter, VS Code, Vim
- **Version control:** Git *(non-negotiable)*
- **Containerization:** Docker
- **AI coding assistants:** Cursor, Claude Code, Copilot

<!--
Two must-haves TODAY: Git and Docker. Learn them now, not on the job.
On AI assistants: "Use them to go faster, but understand what they produce — you own the code, not the tool."
-->

---

## Python Toolbox

- **Env / package manager:** uv *(fast, modern replacement for pip + venv)*
- **API framework:** FastAPI *(how models become services)*
- **Data validation:** Pydantic
- **Testing:** PyTest
- **DataFrames:** Pandas, Polars
- **AI / ML:** scikit-learn, PyTorch, TensorFlow, etc
- **AI agents:** Google ADK, Microsoft Agent Framework, Pydantic AI, CrewAI

<!--
Python is the lingua franca of ML — get genuinely comfortable here.
Priorities for students: Pandas + scikit-learn first, then FastAPI + Pydantic to ship a model as an API.
Polars and uv show the ecosystem constantly evolving toward speed.
The AI-agent tools are the newest frontier — worth exploring, but master the fundamentals first.
-->

<!--
Next up: a short technical demo that uses these tools in action: uv for the environment, scikit-learn for the model, FastAPI + Pydantic for the service, PyTest for tests, and Docker for packaging.
-->

---

## Demo Overview: From Model to Live API

A mini version of a real **review-sentiment service**:

1. **Train** a small text classifier (scikit-learn)
2. **Serve** it as an API (FastAPI + Pydantic)
3. **Test** it (curl + PyTest)
4. **Package** it (Docker)
5. **Watch** it in production (health, latency, drift)

> Flow: `Client` → `FastAPI` → `Pydantic validation` → `model.predict()` → `JSON`

<!--
Technical demo section. Explain that this is a deliberately tiny version of the review-categorization service mentioned earlier: same shape as production, toy data.
Say it out loud: "Five steps — train, serve, test, package, watch. Only step 1 is 'data science'. Steps 2 to 5 are the engineering that makes up most of an ML engineer's job."
Walk the flow in the quote: a request comes in, Pydantic checks the input, the model predicts, a JSON response goes back. This is the SYNCHRONOUS deployment pattern from the earlier slide, so latency matters.
-->

---

<style scoped>
pre { font-size: 16px; line-height: 1.3; margin: 0 0 10px 0; }
</style>

## Demo Step 1: Set Up & Train

```bash
uv init review-api && cd review-api
uv add scikit-learn fastapi "uvicorn[standard]" joblib
uv add --dev pytest httpx
```

```python
# train.py   ->   run: uv run python train.py
import joblib
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.linear_model import LogisticRegression
from sklearn.pipeline import make_pipeline

texts = ["great hotel, very clean", "rude staff, dirty room",
         "lovely view, will come back", "terrible, never again"]
labels = ["positive", "negative", "positive", "negative"]

model = make_pipeline(TfidfVectorizer(), LogisticRegression())
model.fit(texts, labels)
joblib.dump(model, "model.joblib")   # the artifact we will serve
```

**Key idea:** save preprocessing + model as **one pipeline**.

<!--
uv init creates the project plus pyproject.toml; uv add installs packages and records exact versions in uv.lock. That lockfile is what makes the environment reproducible later in Docker.
In train.py, TfidfVectorizer turns text into numbers and LogisticRegression classifies. make_pipeline chains them, so ONE object is saved with joblib. At serving time the exact same preprocessing is applied automatically; mismatched preprocessing between training and serving is one of the most common production bugs.
The dataset is 4 sentences, only to keep the demo fast. Be honest about it: real work is collecting more data and evaluating the model properly (train/test split, precision/recall) before shipping.
Training is done once, offline. The API only loads the saved model.joblib.
-->

---

<style scoped>
pre { font-size: 14px; line-height: 1.3; margin: 0 0 10px 0; }
</style>

## Demo Step 2: Serve It with FastAPI

```python
# main.py
import joblib
from fastapi import FastAPI
from pydantic import BaseModel, Field

model = joblib.load("model.joblib")      # load ONCE, not per request
app = FastAPI(title="Review Sentiment API")

class ReviewIn(BaseModel):
    text: str = Field(min_length=1, max_length=2000)

class ReviewOut(BaseModel):
    label: str
    confidence: float

@app.get("/health")
def health():
    return {"status": "ok"}

@app.post("/predict", response_model=ReviewOut)
def predict(review: ReviewIn):
    proba = model.predict_proba([review.text])[0]
    best = int(proba.argmax())
    return ReviewOut(label=str(model.classes_[best]),
                     confidence=float(proba[best]))
```

<!--
Walk through the file top to bottom:
1) The model is loaded ONCE at startup, at module level. Loading it inside the endpoint would reload the file on every request and destroy latency.
2) ReviewIn and ReviewOut are Pydantic models. They define the API contract: input text must be 1 to 2000 characters, output is a label plus a confidence. Bad input is rejected automatically with HTTP 422, so the model never sees garbage.
3) /health is a trivial endpoint that Kubernetes (or a load balancer) calls to know whether the service is alive.
4) /predict is a plain def, not async def. scikit-learn is CPU-bound and blocking, so FastAPI runs it in a worker thread pool instead of blocking the event loop.
5) predict_proba gives probabilities; we return the best class and its probability. The model.classes_ order matches the columns of predict_proba.
Bonus: FastAPI generates interactive docs at /docs for free. Show them live if the room has a screen.
-->

---

<style scoped>
pre { font-size: 16px; line-height: 1.3; margin: 0 0 10px 0; }
</style>

## Demo Step 3: Run, Call, and Test

```bash
uv run uvicorn main:app --reload      # API + auto docs at /docs
curl -X POST localhost:8000/predict \
  -H "Content-Type: application/json" \
  -d '{"text": "great hotel, very clean"}'
# -> {"label":"positive","confidence":0.xx}
```

```python
# test_api.py   ->   run: uv run pytest
from fastapi.testclient import TestClient
from main import app

client = TestClient(app)

def test_predict_ok():
    r = client.post("/predict", json={"text": "great hotel"})
    assert r.status_code == 200
    assert 0.0 <= r.json()["confidence"] <= 1.0

def test_empty_text_is_rejected():
    assert client.post("/predict", json={"text": ""}).status_code == 422
```

**422** = Pydantic rejects bad input *before* it reaches the model.

<!--
Live part: start the server with uvicorn (--reload restarts it on code changes, for development only), open http://localhost:8000/docs, and call /predict with a positive review, then a negative one, then an empty string. The empty string returns 422 with a clear error message, without any code written for it.
The curl output will show a label and a confidence value; with only 4 training sentences the confidence will be modest, which is expected and a good moment to talk about why real data matters.
Then show PyTest: TestClient calls the app in-process, with no running server needed. Two tests are enough to show the idea: the happy path (status 200, confidence between 0 and 1) and a validation failure (422).
Message: tests are what let you change a model or dependency next month and know nothing broke. In CI (Jenkins, from the infrastructure slide) these run on every commit.
-->

---

<style scoped>
pre { font-size: 16px; line-height: 1.3; margin: 0 0 10px 0; }
</style>

## Demo Step 4: Package with Docker

```dockerfile
FROM python:3.12-slim
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin/uv
WORKDIR /app
COPY pyproject.toml uv.lock ./
RUN uv sync --frozen --no-dev
COPY main.py model.joblib ./
EXPOSE 8000
CMD [".venv/bin/uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

```bash
docker build -t review-api .
docker run -p 8000:8000 review-api
```

**Why:** one image runs on a laptop, in CI, and on Kubernetes.

<!--
Explain the Dockerfile in layers. Copy the dependency files first and run uv sync BEFORE copying the code, so Docker caches the slow install layer and rebuilds stay fast when only main.py changes.
--frozen installs exactly what is in uv.lock, and --no-dev leaves out pytest and httpx. This keeps the image smaller and, importantly, pins the same scikit-learn version used for training: a model saved with one scikit-learn version may fail or behave differently when loaded with another.
--host 0.0.0.0 is required so the server is reachable from outside the container; -p 8000:8000 maps the container port to the machine.
Practical tip: keep the Python version in the base image compatible with the requires-python value in pyproject.toml, otherwise uv sync will complain. Also add a .dockerignore (.venv, __pycache__) in real projects.
This image is what Kubernetes would run, and ArgoCD or Jenkins would deploy; connect it back to the Infrastructure slide.
-->

---

## After Launch: What We Watch in Production

- **Latency (p95)** — a synchronous API must answer in milliseconds.
- **Health checks** — `/health` lets Kubernetes restart unhealthy pods.
- **Errors & traffic** — dashboards in Grafana, logs in Kibana.
- **Model version** — track runs and register models in MLflow.
- **Data drift** — real user text changes over time, so schedule retraining.

> Shipping is the **starting line**, not the finish line.

<!--
Close the demo by connecting it to the earlier slides. p95 latency means 95% of requests are faster than this number; averages hide slow outliers, so engineers watch percentiles.
Health checks, Grafana and Kibana come from the Infrastructure slide. MLflow answers "which model version is in production and how was it trained?" (MLOps slide).
Drift: people start writing different words (new destinations, slang, new campaigns), so a model trained last year slowly gets worse. That is why the scheduled deployment pattern includes periodic retraining.
Transition: "So the model took 10 lines; everything else in this demo is the 80% engineering. Which brings us to the skills you need."
-->

---

## Fundamental Skills for an ML / AI Engineer

- **Software Engineering** — prolem solving, clean code, testing, Git, APIs, Docker.
- **Learning New Things (Growth Mindset)** — the stack changes; the ability to *keep learning* is the real skill.
- **Communication** — explain trade-offs to non-technical people; a model nobody understands won't be trusted or used.

<!--
Rank them honestly: "If I had to hire one trait, it's the growth mindset — everything else can be learned."
ML engineers are software engineers FIRST. Strong SWE fundamentals beat fancy model knowledge.
-->

---

## How to Prepare Before You Graduate

Do-it-this-semester advice:

- **Master the fundamentals** — data structures, algorithms, *especially* SQL.
- **Get fluent in Git, Docker, and the Linux command line.**
- **Build 2–3 end-to-end projects** — data → model → *deployed API*. Deployment impresses employers.
- **Put it on GitHub** with a clean README. Your public work is your resume.
- **Do an internship** — nothing beats *real industry experience* before you graduate.
- **Learn to read docs and debug independently.**
- **Write and speak clearly** — practice explaining your projects in 2 minutes.

<!--
This is the slide they'll photograph — slow down and let it land.
Reframe grades: "Employers care more about what you can BUILD than your GPA."
One deployed project > ten half-finished tutorials.
On internships: emphasize this strongly — a real internship exposes you to production systems,
teamwork, code review, and how decisions are really made. It's the single biggest added value
a fresh graduate can walk in with, and often the fastest path to a full-time offer.
-->

---

## A Few Honest Pieces of Advice

- **You don't need to know everything** — nobody does. Be comfortable saying "I don't know yet, but I can find out."
- **Depth beats breadth early on** — go deep on one project rather than dabbling in ten.
- **Fundamentals > frameworks** — tools change every year; principles don't.
- **Curiosity and consistency** win over raw talent.

<!--
Speak from experience — a personal "learned it the hard way" anecdote is very effective.
Reassure them: imposter syndrome is normal; everyone in industry googles things daily.
-->

---

## Key Takeaways

- Industry AI is **real, valuable, and mostly invisible** — it cuts cost and grows revenue.
- The ML engineer's job is **~80% engineering**, not modeling.
- **Software fundamentals + growth mindset + communication** matter more than any single tool.
- **Technical demo recap:** train → serve → test → package → monitor. The model is only one step of five.
- Start now: **build, deploy, and share** end-to-end projects.

<!--
Keep this tight — this is the message they carry out the door.
-->

---

<!-- _class: lead invert -->

## Q & A

What questions do you have?

*Day-to-day work · how to break in · specific tech · anything about the industry*

<!--
If it's quiet, prompt them: "A common question is HOW DID YOU GET YOUR FIRST ML ROLE?
— want me to answer that?" Offer LinkedIn / email for follow-ups.
-->

---

<!-- _class: lead invert -->

# Thank You

**Setia Budi**
Machine Learning Engineer, tiket.com

*Now go build something.*

<!--
End on the call to action: encourage them to start a project THIS WEEK.
-->
