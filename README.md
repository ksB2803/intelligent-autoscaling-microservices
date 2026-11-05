# Intelligent Autoscaling in Cloud-Native Microservices

**A Study and Proposed Framework for Predictive, Dependency-Aware, and Constrained Autoscaling Using Machine Learning and Reinforcement Learning.**

## 📌 Overview

Cloud-native applications are increasingly built using microservices deployed in containers and managed by orchestration platforms such as Kubernetes.

However, application workloads are dynamic. Sudden traffic spikes can cause increased latency, service failures, and violations of Service Level Objectives (SLOs). On the other hand, maintaining excessive resources leads to unnecessary infrastructure costs and energy consumption.

Kubernetes provides the Horizontal Pod Autoscaler (HPA), which adjusts the number of Pod replicas based on resource utilization. Although effective, traditional HPA is primarily reactive and does not inherently understand future workload patterns or dependencies between microservices.

This seminar explores **Intelligent Autoscaling**, investigating how Machine Learning, Deep Reinforcement Learning, workload forecasting, and service dependency analysis can improve resource allocation in cloud-native environments.

## 🎯 Objectives

- Understand the fundamentals of cloud-native computing, microservices, and Kubernetes.
- Analyse the working and limitations of Kubernetes Horizontal Pod Autoscaler (HPA).
- Study predictive workload forecasting techniques.
- Explore Reinforcement Learning and Deep Reinforcement Learning for intelligent scaling decisions.
- Investigate dependency-aware autoscaling using service graphs.
- Identify research gaps in existing autoscaling approaches.
- Propose a predictive, dependency-aware, and safety-constrained autoscaling framework.
- Define an evaluation methodology to compare the proposed framework against a tuned Kubernetes HPA baseline.

## 🏗️ Proposed Framework

The proposed framework combines multiple intelligent components to make scaling decisions before workload changes negatively affect application performance.

### Architecture and Workflow

1. **Telemetry Collection:** Collect CPU, memory, request rate, latency, errors, replica counts, and service traces.
2. **Workload Prediction:** Predict future workload using time-series forecasting and machine learning models.
3. **Dependency Analysis:** Analyse the microservice call graph to understand how workload propagates between dependent services.
4. **Capacity Estimation:** Calculate the required number of replicas for each service based on predicted demand and available capacity.
5. **Multi-Objective Scaling Policy:** Use Reinforcement Learning to balance latency, resource cost, and scaling stability.
6. **Safety and Constraint Layer:** Enforce scaling limits, cooldown periods, rate limits, and fallback mechanisms.
7. **Kubernetes Execution:** Apply safe scaling decisions through the Kubernetes API.
8. **Continuous Evaluation:** Monitor performance and compare the proposed approach against the baseline HPA.

### Framework Flow

```text
       Incoming Application Traffic
                  |
                  v
          Telemetry Collection
                  |
                  v
         Workload Prediction
          (ML / Forecasting)
                  |
                  v
        Dependency Analysis
          (Service Graph)
                  |
                  v
          Capacity Estimation
                  |
                  v
       Reinforcement Learning
        (Multi-Objective Policy)
                  |
                  v
       Safety & Constraint Layer
                  |
           +------+------+
           |             |
        Safe Action    Fallback
           |             |
           +------+------+
                  |
                  v
           Kubernetes API
                  |
                  v
          Scaling Execution
                  |
                  v
          Performance Monitoring
                  |
                  +----> Feedback Loop
```

## 🧠 Key Technologies and Concepts

| Category | Technologies / Concepts |
|---|---|
| Container Orchestration | Kubernetes |
| Containerization | Docker |
| Monitoring | Prometheus, metrics-server |
| Distributed Tracing | Jaeger, Istio |
| Workload Forecasting | ARIMA, Random Forest, LSTM |
| Reinforcement Learning | DQN, A2C, PPO |
| Dependency Analysis | Service Graphs, Graph Neural Networks |
| Scaling Mechanisms | HPA, VPA, Cluster Autoscaler |
| Load Generation | Locust |
| Benchmark Applications | Online Boutique, TeaStore |

*These technologies represent the techniques and tools studied or proposed in the framework; they should not be interpreted as a claim that a complete implementation has been deployed.*

## 📚 Literature Survey

The report reviews **29 research studies published between 2019 and 2026**, covering different approaches to intelligent autoscaling.

Major research areas include:

- Predictive autoscaling using machine learning.
- Deep Reinforcement Learning-based scaling policies.
- Dependency-aware autoscaling using Graph Neural Networks.
- Hybrid proactive and reactive autoscaling.
- Multi-layer and energy-aware resource management.
- Safety mechanisms and production-ready autoscaling.

Some notable research systems discussed include:

- Google Autopilot
- MagicScaler
- DScaler
- GRAF
- DeepScaler
- Gwydion
- AWARE
- NimbusGuard

## ⚙️ Research Gaps Identified

The literature survey identifies several important challenges:

1. **RL Exploration Cost:** Training reinforcement learning agents directly in production can cause performance degradation.
2. **Dependency Blindness:** Traditional autoscalers often treat microservices independently, ignoring downstream bottlenecks.
3. **Multi-Objective Optimization:** Balancing latency, infrastructure cost, energy consumption, and scaling stability is difficult.
4. **Prediction Uncertainty:** Incorrect workload predictions can result in over-provisioning or insufficient capacity.
5. **Workload Drift:** Previously trained models may become inaccurate as application traffic patterns change.
6. **Evaluation Standards:** Different benchmarks, workloads, and baselines make research comparisons difficult.

## 📊 Proposed Evaluation Methodology

The proposed framework defines an evaluation plan against a tuned Kubernetes HPA baseline.

### Evaluation Metrics

- **MAE / RMSE:** Workload forecasting accuracy.
- **p95 Latency:** 95th-percentile application response time.
- **SLO Violations:** Frequency of application performance target violations.
- **Resource Consumption:** CPU and memory utilization.
- **Infrastructure Cost:** Cost associated with allocated resources.
- **Scaling Churn:** Frequency of scaling operations.

### Planned Experiments

1. Compare reactive HPA with predictive autoscaling.
2. Evaluate the effect of dependency-aware capacity estimation.
3. Compare different reinforcement learning policies.
4. Evaluate the safety layer and fallback mechanism.
5. Analyse the complete framework under bursty and changing workloads.

## 🔬 Current Project Status

**Status: Research Study and Proposed Framework**

This work is primarily a literature survey and conceptual framework proposal. It includes:

- A comparative review of 29 research studies.
- Analysis of Kubernetes autoscaling mechanisms.
- A proposed intelligent autoscaling architecture.
- Workload prediction and dependency analysis methodology.
- A multi-objective reinforcement learning formulation.
- Safety constraints and fallback mechanisms.
- An evaluation plan with defined metrics and experiments.

**Note:** The proposed framework has not yet been implemented or experimentally validated as a complete system. Quantitative results discussed in the report belong to the original research papers.

## 🚀 Future Work

Potential extensions include:

- Implementing the proposed framework on a Kubernetes cluster.
- Using Online Boutique as the benchmark microservice application.
- Integrating Prometheus and Jaeger for telemetry collection.
- Implementing workload forecasting models.
- Training reinforcement learning agents in a simulated environment.
- Integrating safe scaling decisions with the Kubernetes API.
- Extending the framework to vertical and node-level autoscaling.
- Exploring energy-aware scaling and workload drift detection.

## 📖 Documentation

The complete seminar report is available in this repository:

`Intelligent_Autoscaling_Seminar_Report.pdf`

It covers the introduction, literature survey, research gaps, proposed methodology, algorithms, evaluation plan, discussion, and references.

## 👨‍💻 Author

**Kripal Singh Bisht**

- Information Technology Engineering
- Army Institute of Technology, Pune
- Academic Year: 2026–2027

**Seminar Guide:** Dr. Ashwini Sapkal

## ⭐ Acknowledgement

This seminar was carried out under the guidance of Dr. Ashwini Sapkal, Department of Information Technology, Army Institute of Technology, Pune.

---

*This repository documents an academic study of intelligent autoscaling techniques and a proposed framework for improving resource efficiency, application performance, and reliability in cloud-native microservices.*
