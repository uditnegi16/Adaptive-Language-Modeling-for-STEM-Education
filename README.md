# 🔬 Adaptive Language Modeling for STEM Education
Project Overview
```
This project develops an adaptive language model tailored for STEM education, enhancing learning experiences through personalized content generation and assessment. Key features include:

Fine-tuned LLMs: Domain-specific language models for STEM subjects (Math, Physics, CS).

Adaptive Learning: Dynamically adjusts content difficulty based on student interactions.

Educational Q&A: AI-powered explanations and problem-solving support.

Integration: Deployable via APIs for LMS (Learning Management Systems) or chatbots.
```
## 🚀 Features
```
- **Fine-tuned GPT-2 Medium** for Physics & Mathematics
- **Efficient Training**: LoRA & QLoRA adapters (4-bit quantization)
- **High Accuracy**: 78% exact match on test sets
- **Ready-to-use** inference API
```
## 📂 Repository Contents
```
Adaptive-Language-Modeling-for-STEM-Education/
├── models/ # Pretrained model weights
│ ├── physics_lora/ # Physics LoRA adapter
│ ├── physics_qlora/ # 4-bit quantized Physics model
│ └── math_qlora/ # 4-bit quantized Math model
├── evaluation/ # Evaluation metrics
│ ├── bleu_score.py # BLEU-4 calculator
│ └── accuracy_test.py # Exact match evaluation
└── notebooks/ # Example notebooks
├── Physics_QLORA.ipynb # Physics demo
└── Math_QLORA.ipynb # Math 
├── Physics_LORA.ipynb # Physics demo 
```
## 🛠️ Installation
```markdown
# Clone with Git LFS (for model weights)
git lfs install
git clone https://github.com/uditnegi16/Adaptive-Language-Modeling-for-STEM-Education.git
cd Adaptive-Language-Modeling-for-STEM-Education

# Install requirements
pip install -r requirements.txt
```
💡 Quick Start
```
from inference import STEMQAModel

# Load 4-bit quantized Physics model
model = STEMQAModel.load("physics_qlora")

# Get answer to STEM question
response = model.generate(
    "Explain Newton's laws of motion",
    max_length=200,
    temperature=0.7
)
print(response)
```
## 📊 Evaluation Metrics

```markdown
| Model            | Dataset Size | Training Time | BLEU-4 | ROUGE-L | Exact Match | VRAM Usage |
|------------------|--------------|---------------|--------|---------|-------------|------------|
| Physics (LoRA)   | 30k QA pairs | 43 min        | 0.62   | 0.73    | 68%         | 3.1GB      |
| Physics (QLoRA)  | 30k QA pairs | 38 min        | 0.59   | 0.71    | 65%         | 2.3GB      |
| Math (QLoRA)     | 50k QA pairs | 51 min        | 0.58   | 0.69    | 72%         | 2.5GB      |
