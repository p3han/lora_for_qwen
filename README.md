# Qwen2.5-0.5B-Instruct for Medical Symptom Polarity Classification (LoRA Fine-tuning)

This project fine-tunes the Qwen2.5-0.5B-Instruct model using LoRA (Low-Rank Adaptation) on a medical dataset derived from the PromptCBLUE benchmark. The goal is to improve the model's ability to extract and classify the **presence or absence of symptoms** based on patient dialogues.

## 🧠 Motivation

In low-resource or privacy-sensitive environments (e.g. rural clinics), deploying large-scale foundation models is impractical. This project aims to:

- Adapt a lightweight open-source model (Qwen2.5-0.5B) for **medical NLP tasks**.
- Fine-tune using **LoRA**, a parameter-efficient method.
- Target the task of **symptom polarity judgment** from clinical conversations.

## 📂 Dataset

Based on a filtered subset of [PromptCBLUE](https://github.com/CBLUEbenchmark/PromptCBLUE), focused on **symptom-level entity recognition** and **polarity classification**.

Each sample is formatted into instruction-tuning style:

```json
{
  "id": "123",
  "instruction": "请判断对话中提到的所有症状的阴阳性。",
  "input": "病人描述：最近有些流鼻涕和咳嗽……",
  "output": "清鼻涕：患有该症状\n咳嗽：患有该症状"
}
