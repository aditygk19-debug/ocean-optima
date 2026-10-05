# Ocean Optima

**Quantum-Inspired Fuel Consumption Prediction and Green Fleet Optimization**

Ocean Optima is an India-focused, explainable, and reproducible decision-support platform for green fleet management. It is designed to address **SIH26138** (Organization: Egreen Quanta, Theme: Clean & Green Technology).

> **Note on Repository Status:** This repository currently contains only the project blueprint and README. The full implementation (prediction models, optimizer, API, and dashboard) is under active development and will be pushed in subsequent commits.

## 🎯 Problem Statement
The maritime industry needs to reduce greenhouse gas emissions while maintaining cost-effectiveness. Traditional methods struggle with the high-dimensional, non-linear, and multi-objective nature of green fleet management. Ocean Optima solves this by integrating:
- **Fuel Consumption Prediction** under varying operational conditions.
- **Fleet Deployment Optimization** for vessel types, capacities, and cruising speeds.
- **Alternative Fuel Integration** (LNG, Methanol, Hydrogen, Ammonia) and **Shore Power**.
- **Lifecycle Emissions (Well-to-Wake)** and **Regulatory Compliance** (IMO CII, FuelEU).

## 🚀 Proposed Solution
Ocean Optima is a modular decision-support system that connects prediction, lifecycle accounting, constrained optimization, benchmarking, and explanation in one workflow. It does not claim to be the first solution; it is an **open, transparent, and reproducible demonstrator** that differentiates itself through explainability and fair benchmarking.

### Core Deliverables
1. **Prediction Model:** Hybrid physics (Admiralty formula) + ML (XGBoost/CatBoost) with uncertainty estimation.
2. **Optimization Engine:** Quantum-inspired metaheuristics (QGA/QPSO/QUBO) benchmarked against classical methods (GA, PSO, SA, NSGA-II).
3. **Emissions & Compliance:** Well-to-Wake (WTW) lifecycle accounting, shore power decisions based on India's grid mix, and CII/FuelEU scenario modeling.
4. **Decision Support Dashboard:** Pareto front exploration, what-if scenarios, and plain-language explanations for every recommendation.

## 🏗️ System Architecture
The architecture is modular, ensuring the same domain logic is used by the dashboard, API, benchmark runner, and report generator.

| Layer | Responsibilities | Main Components |
| :--- | :--- | :--- |
| **Presentation** | Scenario builder, maps, charts, Pareto exploration, reports. | React/TypeScript, Plotly, Leaflet |
| **API/Application** | Validation, orchestration, jobs, authentication, audit. | FastAPI, Pydantic, SQLAlchemy |
| **Data** | Vessel, route, port, fuel, weather, cargo, and experiment data. | SQLite/PostgreSQL, CSV/JSON |
| **Prediction** | Physics baseline, ML model, residual correction, uncertainty. | NumPy, Pandas, scikit-learn, XGBoost |
| **Emissions/Compliance** | WTW, shore power, CII, FuelEU scenario calculations. | Configurable rules and factor tables |
| **Optimization** | Problem encoding, QI solver, classical solvers, repair, Pareto. | NumPy/SciPy, custom QGA/QPSO, DEAP |
| **Benchmarking** | Repeated runs, metrics, scaling, exact small cases. | Seed manager, benchmark runner |
| **Reporting** | Plain-language explanation, charts, assumptions, export. | Jinja/Markdown/PDF/DOCX |

## 🇮🇳 India-Specific Focus
- **Shore Power Decision Engine:** Evaluates shore power based on India's current fossil-heavy grid mix (~710 gCO₂/kWh) rather than assuming it is automatically green.
- **Indian Port Scenarios:** Curated routes, port waits, congestion, and fuel availability for Indian coastal shipping.
- **Regulatory Alignment:** Designed for IMO CII, EEXI, FuelEU, and EU ETS scenarios.

## 📊 Benchmarking & Validation
We are committed to fair and honest benchmarking:
- **Same Instances:** All algorithms run on identical scenarios.
- **Same Budget:** Equal evaluation budgets and stopping conditions.
- **Repeated Seeds:** Stochastic methods are run across multiple seeds.
- **Metrics:** Mean, median, standard deviation, best result, feasibility percentage, runtime, hypervolume, and optimality gap.
- **Baselines:** GA, PSO, SA, NSGA-II, Greedy, and Exact MILP for small instances.

## 🛠️ Technology Stack
- **Frontend:** React + TypeScript + Tailwind
- **Backend:** Python + FastAPI + Pydantic
- **Database:** SQLite (MVP) → PostgreSQL (Production)
- **ML:** Pandas, NumPy, scikit-learn, XGBoost/CatBoost
- **Optimization:** NumPy/SciPy, custom QI algorithms, DEAP/PyGAD, OR-Tools/PuLP
- **Deployment:** Docker Compose

## 🗺️ Roadmap
- [ ] **Phase 0:** Contracts, Schemas, Repo Structure
- [ ] **Phase 1:** Physics & Data Layer
- [ ] **Phase 2:** ML Prediction & Uncertainty
- [ ] **Phase 3:** Optimization Encoding & QI Solver
- [ ] **Phase 4:** Benchmarking & Baselines
- [ ] **Phase 5:** API & UI Integration
- [ ] **Phase 6:** India Scenarios & Case Study
- [ ] **Phase 7:** Hardening, Testing, & Documentation

## 👥 Target Users
- Fleet Managers
- Sustainability / Compliance Managers
- Operations / Port Planners
- Researchers / Evaluators

## 📄 License
This project is developed for the Smart India Hackathon (SIH) 2026. Please refer to the official SIH guidelines for usage and distribution.

---
*Prepared for SIH 2026 — Problem SIH26138 | Version 0.1 | October 2026*
