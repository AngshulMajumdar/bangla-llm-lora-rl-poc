# Bangla LLM Fine-Tuning with LoRA and Reinforcement Learning (PoC)

This repository presents a **proof-of-concept (PoC)** for adapting a large language model to **Bangla (Bengali)** using:

1. **Supervised fine-tuning (SFT)** with **LoRA**
2. **Reinforcement learning (policy-gradient / REINFORCE)** with a **rule-based reward**
3. **Low-resource execution** on a single GPU (Colab T4)

The goal is to **demonstrate feasibility**, not to achieve state-of-the-art performance.

---

## Model
- **Base model:** Qwen/Qwen2.5-0.5B  
- **Tokenization:** Byte Pair Encoding (BPE)  
- **Adaptation:** LoRA (parameter-efficient fine-tuning)

---

## Dataset
- **AI4Bharat IndicCorpV2**
- Language split: **Bangla (`ben_Beng`)**
- Data accessed in streaming mode; a subset is used for the PoC

---

## Training Overview

### 1. Supervised Fine-Tuning (SFT)
- LoRA adapters trained on Bangla text
- Checkpointed training with resume support

### 2. Reinforcement Learning (RL)
- **Policy-gradient (REINFORCE)** optimization
- **Rule-based reward** encouraging Bangla language purity
- No human feedback
- No PPO / TRL dependency

---

## Reinforcement Learning Formulation

- **Policy:** LoRA-adapted language model  
- **Action:** Token generation  
- **Reward:** Scalar score based on Bangla Unicode dominance and English suppression  
- **Optimization:** Gradient ascent on expected reward  

This constitutes **valid reinforcement learning** under the standard policy-gradient framework.

---

## Example Claim (Honest & Defensible)

> We refine a Bangla-adapted language model using reinforcement learning with a rule-based reward, implemented via policy-gradient optimization on top of LoRA fine-tuning.

---

## Scope & Disclaimer

This repository is intended as a **research and demonstration PoC**:
- Not production-ready
- Not optimized for benchmark performance
- Focused on methodology and feasibility

---

## License
MIT
