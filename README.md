# Ollama Models EDA

## Project Overview
This repository provides an exploratory data analysis (EDA) of the `enhanced_ollama_models.csv` dataset, which catalogs a wide range of large language models (LLMs) available in the Ollama library. The analysis aims to help users understand the diversity, capabilities, and technical requirements of these models.

## Dataset Description
- **File:** `enhanced_ollama_models.csv`
- **Columns:**
  - `name`: Model name
  - `description`: Brief summary of the model
  - `pulls`: Number of downloads/pulls
  - `tags`: Number of tags/categories
  - `updated`: Last update time
  - `capabilities`: Supported features (e.g., vision, code, math)
  - `size_variants`: Available model sizes
  - `url`: Ollama library URL
  - `parameter_sizes`: Model parameter sizes (e.g., 7B, 70B)
  - `context_window`: Supported context window sizes
  - `model_type`: Model specialization (e.g., Vision, Code, Math)
  - `license_info`: License type(s)
  - `base_model`: Base model (if any)
  - `performance_benchmarks`: Benchmark results (if available)
  - `hardware_requirements`: Required hardware for running the model
  - `specialty_domain`: Domain specialization (e.g., coding, reasoning)
  - `release_info`: Release version or notes
  - `quantization_support`: Whether quantization is supported

## Key Insights from EDA
- **Model Diversity:**
  - Models range from small (e.g., 1B parameters) to very large (e.g., 405B parameters).
  - Multiple organizations are represented (Meta, Google, Microsoft, Alibaba, etc.).
- **Capabilities:**
  - Common capabilities: Vision, Code, Math, Reasoning, Embedding, Chat, Translation.
  - Some models are highly specialized (e.g., embedding, code-specific).
- **Hardware Requirements:**
  - Requirements vary from laptop-friendly models to those needing multiple GPUs or large memory.
- **Licensing:**
  - Licenses include Apache 2.0, MIT, CC, proprietary, and commercial.
- **Context Window:**
  - Ranges from 2K tokens (small models) to 128K+ tokens (large models).
- **Quantization Support:**
  - Some models support quantization for efficient inference on limited hardware.
- **Benchmarks:**
  - Performance benchmarks are available for select models, indicating their capabilities on tasks like HellaSwag, BoolQ, PIQA, MMLU, etc.

## Example Usage (Python)
```python
import pandas as pd

# Load the dataset
df = pd.read_csv('enhanced_ollama_models.csv')

# Show basic info
print(df.info())
print(df.head())

# Distribution of model sizes
df['parameter_sizes'].value_counts().plot(kind='bar')

# Models supporting quantization
quantized_models = df[df['quantization_support'] == 'Yes']
print(quantized_models[['name', 'parameter_sizes', 'hardware_requirements']])
```

## Repository Structure
- `enhanced_ollama_models.csv`: Main dataset
- `ollama_analysis.ipynb`: Jupyter notebook for EDA and visualization

## Getting Started
1. Clone the repository.
2. Install required Python packages (e.g., pandas, matplotlib, plotly).
3. Open `ollama_analysis.ipynb` and run the cells to explore the data.

## License
See individual model license information in the CSV file.

---

Feel free to expand the analysis in the notebook or add new visualizations as needed.
