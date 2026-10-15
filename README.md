<a href="https://github.com/gulaag/FinSage">
  <img src="./assets/hero.svg" alt="Digvijay Singh, AI Engineer: agentic systems, production RAG and LLM evaluation" width="100%">
</a>

<p align="center">
  <a href="https://github.com/gulaag/FinSage">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=19&duration=3200&pause=900&color=22D3EE&center=true&vCenter=true&width=760&lines=Agents+that+cite+every+number+they+return;Tool+calling+%C2%B7+RAG+%C2%B7+LLM-as-a-judge+evals+%C2%B7+guardrails;33%25+%E2%86%92+87%25+accuracy+on+a+100-question+SEC+benchmark;FastAPI+backends+serving+3K%2B+monthly+users+in+production" alt="Typing summary of focus areas">
  </a>
</p>

<p align="center">
  <a href="https://linkedin.com/in/digvijayarsaga"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:digvijay21251@iiitd.ac.in"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://github.com/gulaag/FinSage"><img src="https://img.shields.io/badge/Flagship-FinSage-7C3AED?style=for-the-badge&logo=databricks&logoColor=white" alt="FinSage"></a>
  <a href="https://github.com/gulaag/mieru-case-study"><img src="https://img.shields.io/badge/Live_SaaS-MIERU-10B981?style=for-the-badge&logo=fastapi&logoColor=white" alt="MIERU case study"></a>
</p>

<br>

## 🧠 About me

```python
class DigvijaySingh(AIEngineer):
    now        = "AI & Software Engineer @ Arsaga Partners (Japan)"
    builds     = ["tool-calling agents", "production RAG", "LLM eval harnesses", "backends at scale"]
    certified  = ["Databricks Generative AI Engineer Associate", "Databricks Data Engineer Professional"]
    education  = "B.Tech, Computer Science & Applied Mathematics, IIIT Delhi"

    def principle(self):
        return "A number without a source is worthless. Ground it, cite it, or refuse."
```

I take LLM agents from notebook to production: the **orchestration loop**, the **retrieval layer**, the **guardrails**, and the **evaluation harness** that proves a new version is better before it ships. I also build the backend and data platforms they run on.

<table>
<tr>
<td width="33%" valign="top">

### 🤖 Agentic AI
Function-calling agents with an **owned harness** (no LangChain): bounded ReAct loops, JSON-schema tools, argument validation, refusal policies, citation enforcement.

</td>
<td width="33%" valign="top">

### 🔎 Retrieval & Evals
ANN **semantic search** with metadata filters and similarity gates, section-aware chunking, **LLM-as-a-judge** plus programmatic scorers, run-over-run regression diffs.

</td>
<td width="33%" valign="top">

### 🏗️ Scalable systems
FastAPI services, PostgreSQL, multi-tenant RBAC, Spark / Delta Lake **Medallion** pipelines, Docker on Cloud Run, Databricks Asset Bundles, CI/CD.

</td>
</tr>
</table>

<br>

## ⭐ Flagship: [FinSage](https://github.com/gulaag/FinSage), an agentic financial analyst over SEC filings

<a href="https://github.com/gulaag/FinSage">
  <img src="./assets/finsage-impact.svg" alt="FinSage lifts answer accuracy from 33% to 87% on a 100-question SEC-verified benchmark, with 100% citation coverage" width="100%">
</a>

A tool-calling agent that answers questions about 30 large-cap companies from **728 SEC 10-K / 10-Q filings**, and backs every figure with the filing, fiscal year and section it came from. Piloted with **1,000 retail investors in Japan**; Arsaga then formed a dedicated team to productize it.

<a href="https://github.com/gulaag/FinSage">
  <img src="./assets/finsage-architecture.svg" alt="FinSage architecture: agent harness routes numbers to Gold Delta metric tools and narrative to Vector Search, with a citation enforcer and an evaluation gate on every version" width="100%">
</a>

- **Numbers never come from RAG.** Figures are served only by metric tools over audited Gold tables; vector search handles narrative. That split is why hallucinated numbers are close to zero.
- **Owned agent harness.** A ReAct-style loop in `mlflow.pyfunc` (≤ 5 iterations, 150 s budget, temperature 0) where the harness, not the model, validates arguments, runs tools and enforces the output contract.
- **Retrieval with a quality gate.** Metadata-filtered ANN search over 45,136 BGE-large chunks with a 0.4 similarity gate and a single permissive retry.
- **Evals as a release gate.** 100 stratified, SEC-verified questions; 8 scorers (±1% numeric tolerance, tool routing, refusal reason, citation format, retrieval groundedness, two LLM judges); results persisted to Delta with dataset hash and git commit for regression diffs across agent versions.
- **Production plumbing.** MLflow Tracing on every tool call, Unity Catalog model registry, scale-to-zero Model Serving, Databricks Asset Bundles, GitHub Actions with OAuth M2M (no PATs), Terraform cost guardrails.

<details>
<summary><b>Watch the Databricks pipeline run end to end</b> (Bronze → Silver → Gold → Vector index)</summary>
<br>
<img src="https://raw.githubusercontent.com/gulaag/FinSage/main/assets/screenshots/pipeline.gif" alt="FinSage Databricks job DAG running schema setup, bronze autoloader, silver decoder, gold metrics and vector chunker" width="100%">
</details>

<p>
  <img src="https://img.shields.io/badge/Claude_Sonnet_4.6-191919?style=flat-square&logo=anthropic&logoColor=white" alt="Claude Sonnet 4.6">
  <img src="https://img.shields.io/badge/Databricks_Vector_Search-FF3621?style=flat-square&logo=databricks&logoColor=white" alt="Databricks Vector Search">
  <img src="https://img.shields.io/badge/MLflow_GenAI_Evaluate-0194E2?style=flat-square&logo=mlflow&logoColor=white" alt="MLflow">
  <img src="https://img.shields.io/badge/Unity_Catalog-FF3621?style=flat-square&logo=databricks&logoColor=white" alt="Unity Catalog">
  <img src="https://img.shields.io/badge/Apache_Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white" alt="Apache Spark">
  <img src="https://img.shields.io/badge/Delta_Lake-00ADD4?style=flat-square" alt="Delta Lake">
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI">
  <img src="https://img.shields.io/badge/Terraform-844FBA?style=flat-square&logo=terraform&logoColor=white" alt="Terraform">
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions">
</p>

<br>

## 🏗️ Production at scale: [MIERU](https://github.com/gulaag/mieru-case-study), a multi-tenant KPI SaaS

<a href="https://github.com/gulaag/mieru-case-study">
  <img src="./assets/mieru-architecture.svg" alt="MIERU architecture: React SPA, FastAPI backend with 99 endpoints, PostgreSQL, Stripe, Firebase, AI Growth Coach and Cloud Run delivery" width="100%">
</a>

[mieru.info](https://mieru.info) is a live KGI / CSF / KPI management platform used by Japanese companies (**3K+ MAU**). I built across the whole stack and shipped its generative-AI feature.

- **Backend:** 99 REST endpoints across 18 FastAPI modules, PostgreSQL schema of 13 tables and 41 Alembic migrations, org-level RBAC, JWT + CSRF, Stripe subscription billing.
- **Frontend:** a 181-component React + TypeScript app with React Query, Storybook and MSW-mocked tests.
- **AI Growth Coach:** personalized coaching on Llama 3.3 70B, self-hosted on Ollama at **4× lower latency than Groq**. Input passes through prompt-injection filters that block **98%** of attack payloads, and every number in the response is checked against the user's own data. **3× engagement lift** (daily opens 2 → 6+).
- **Delivery:** Docker images built by Cloud Build and deployed to Cloud Run (staging and production).

> The source is proprietary, so the repo is a [case study](https://github.com/gulaag/mieru-case-study) of the architecture and engineering decisions. Happy to walk through the code in an interview.

<br>

## 🧪 More work

| Project | What it is | Stack |
|---|---|---|
| 🤖 [**databricks-AIagent**](https://github.com/gulaag/databricks-AIagent) | Enterprise **action agent**: retrieves context from past sessions via Vector Search, drafts a Japanese announcement, posts it to Slack / Teams, and audit-logs every action to Unity Catalog. | MLflow PyFunc · Vector Search · Llama 3.3 70B · MLflow Tracing |
| 🏭 **Enterprise data platform** *(client work)* | OIDC-federated CI/CD for Databricks Asset Bundles on GCP: CI 20 → 5 min, deploys 45 → 8 min, compute cost −40%. Spark ETL on Delta Live Tables at 50K records/day. | Databricks · DLT · PySpark · Terraform · GitLab CI |
| 🎬 [**movie_recommender**](https://github.com/gulaag/movie_recommender) | Content-based recommender over 4,800 films using vectorized tags and cosine similarity, served with Streamlit. | scikit-learn · NLP · Streamlit |
| 📈 [**regression_DataCleaning**](https://github.com/gulaag/regression_DataCleaning) | End-to-end ML: preprocessing pipelines, stacked ensembles with GridSearchCV, Flask serving. | scikit-learn · XGBoost · CatBoost · Flask |

<br>

## 🛠️ Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,ts,java,cpp,fastapi,react,tailwind,postgres,docker,kubernetes,gcp,aws,terraform,githubactions,linux,git&perline=16" alt="Python, TypeScript, Java, C++, FastAPI, React, Tailwind, PostgreSQL, Docker, Kubernetes, GCP, AWS, Terraform, GitHub Actions, Linux, Git">
</p>

<table>
<tr><td><b>LLMs & agents</b></td><td><img src="https://img.shields.io/badge/Claude-191919?style=flat-square&logo=anthropic&logoColor=white" alt="Anthropic"> <img src="https://img.shields.io/badge/Llama_3.3_70B-0467DF?style=flat-square&logo=meta&logoColor=white" alt="Meta"> <img src="https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white" alt="Ollama"> <img src="https://img.shields.io/badge/Function_calling-7C3AED?style=flat-square" alt="Function calling"> <img src="https://img.shields.io/badge/ReAct_loops-7C3AED?style=flat-square" alt="ReAct"> <img src="https://img.shields.io/badge/Guardrails-7C3AED?style=flat-square" alt="Guardrails"></td></tr>
<tr><td><b>Retrieval & evals</b></td><td><img src="https://img.shields.io/badge/Databricks_Vector_Search-FF3621?style=flat-square&logo=databricks&logoColor=white" alt="Vector Search"> <img src="https://img.shields.io/badge/BGE--large_embeddings-0EA5E9?style=flat-square" alt="BGE"> <img src="https://img.shields.io/badge/MLflow_Evaluate_%26_Tracing-0194E2?style=flat-square&logo=mlflow&logoColor=white" alt="MLflow"> <img src="https://img.shields.io/badge/LLM--as--a--judge-0EA5E9?style=flat-square" alt="LLM judge"></td></tr>
<tr><td><b>Data platform</b></td><td><img src="https://img.shields.io/badge/Databricks-FF3621?style=flat-square&logo=databricks&logoColor=white" alt="Databricks"> <img src="https://img.shields.io/badge/PySpark-E25A1C?style=flat-square&logo=apachespark&logoColor=white" alt="Spark"> <img src="https://img.shields.io/badge/Delta_Lake-00ADD4?style=flat-square" alt="Delta"> <img src="https://img.shields.io/badge/Unity_Catalog-FF3621?style=flat-square&logo=databricks&logoColor=white" alt="Unity Catalog"> <img src="https://img.shields.io/badge/Delta_Live_Tables-FF3621?style=flat-square&logo=databricks&logoColor=white" alt="DLT"></td></tr>
<tr><td><b>Backend</b></td><td><img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"> <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"> <img src="https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat-square&logo=sqlalchemy&logoColor=white" alt="SQLAlchemy"> <img src="https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white" alt="Pydantic"> <img src="https://img.shields.io/badge/Stripe-635BFF?style=flat-square&logo=stripe&logoColor=white" alt="Stripe"></td></tr>
<tr><td><b>Frontend</b></td><td><img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB" alt="React"> <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"> <img src="https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind"></td></tr>
<tr><td><b>Cloud & DevOps</b></td><td><img src="https://img.shields.io/badge/GCP_Cloud_Run-4285F4?style=flat-square&logo=googlecloud&logoColor=white" alt="GCP"> <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square" alt="AWS"> <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"> <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" alt="Kubernetes"> <img src="https://img.shields.io/badge/Terraform-844FBA?style=flat-square&logo=terraform&logoColor=white" alt="Terraform"> <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions"> <img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white" alt="pytest"></td></tr>
</table>

<br>

## 🏆 Credentials

- 🎓 **Databricks Certified Generative AI Engineer Associate**
- 🎓 **Databricks Certified Data Engineer Professional**
- 🥇 **Winner**, Build with Claude hackathon (Arsaga)
- ⚔️ **Codeforces Expert** (max rating 1632)
- 📐 **JEE Main 98.9 percentile** (top 1% of 1.3M)

<br>

<p align="center">
  <b>Hiring for agentic AI, LLM platform or backend roles?</b> I'd love to talk.<br><br>
  <a href="https://linkedin.com/in/digvijayarsaga"><img src="https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
  <a href="mailto:digvijay21251@iiitd.ac.in"><img src="https://img.shields.io/badge/Say_hello-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
</p>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:7C3AED,50:3B82F6,100:22D3EE&height=110&section=footer" width="100%" alt="">
