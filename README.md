## 📋 Pre-training survey — please take 2 minutes before we start

<a href="pre-training-survey-qr.png"><img src="pre-training-survey-qr.png" alt="Pre-training survey QR code" width="180" align="right"></a>

Scan the QR on the right (or open it from [`https://ucsantacruz.co1.qualtrics.com/jfe/form/SV_3wQP0UrsPXy3nMO?Q_CHL=qr`](https://ucsantacruz.co1.qualtrics.com/jfe/form/SV_3wQP0UrsPXy3nMO?Q_CHL=qr)) to take the **pre-training survey**. It's a quick set of questions about your prior Kubernetes / NRP / AI experience and what you hope to get out of the workshop.

Your answers let us measure how much each tutorial actually moves the needle — comparing pre-training and post-training responses, plus aggregated session telemetry, is how we study the **efficacy of our training methods** and decide what to keep, cut, or rework for future NRP workshops. The data is collected in aggregate; the more responses we get, the better the next cohort's experience will be.

<br clear="right">

Two ways to follow along during the workshop:

**Option 1 — Training JupyterHub (recommended, zero install).** The workshop hub at [training.nrp-nautilus.io](https://training.nrp-nautilus.io/) is pre-configured: every spawned JupyterLab pod already has `kubectl` installed and a kubeconfig wired up to the same identity, so you can open a terminal and run `kubectl` immediately. Click below to clone this repo straight into your JupyterLab session:

Launch 7NRP Tutorial Workspace](https://training.nrp-nautilus.io/hub/user-redirect/git-pull?repo=https%3A%2F%2Fgithub.com%2Fnrp-nautilus%2Fnautilus-kubernetes-training&urlpath=tree%2Fnautilus-kubernetes-training%2F&branch=main)

**Option 2 — kubectl on your laptop.** Install `kubectl` (Linux / macOS / Windows) and use the ready kubeconfig at [`files/nrp-training.kubeconfig`](files/nrp-training.kubeconfig). It carries the `jupyterhub-sa` service-account token, cluster CA, and `nrp-training-k8s` as the default namespace; the embedded token is valid for the duration of 7NRP, through end-of-day Thursday, May 7, 2026. Step-by-step instructions live in [Tutorial 1 → Interacting with NRP](1_nrp_kubernetes_education_research/nrp_kubernetes_education_research.md#interacting-with-nrp).

**Conventions**
- Tutorials 1 and 3 (AI/LLM) share the **`nrp-training-k8s`** namespace. It already exists for the workshop; if you need to recreate it later: `kubectl create namespace nrp-training-k8s`.
- Tutorial 4 (Custom JupyterHubs) uses pre-created per-participant namespaces (**`nrp-training-000`** … **`nrp-training-099`**).
- Replace **`<username>`** in any YAML or command with your NRP or GitHub username to avoid name collisions.
- Every workload must declare CPU and memory `requests` *and* `limits` — a cluster-wide Gatekeeper policy rejects pods without them.

