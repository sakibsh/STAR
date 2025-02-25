# STAR: Self-Knowledge and Targeted Augmented Retrieval

## Overview

**Recent advances in Retrieval-Augmented Generation (RAG)** have enabled large language models (LLMs) to consult external knowledge bases, mitigating the limitations of purely parameterized knowledge. However, many existing RAG-based systems employ _iterative_ methods—like multi-step question decomposition—which can be overly time-consuming for straightforward queries.

### What is STAR?

**STAR (Self-Knowledge and Targeted Augmented Retrieval)** addresses these inefficiencies by using a **two-branch** architecture:

1. **Self-Knowledge Branch** – Determines whether the query can be answered by the LLM’s existing knowledge alone.
2. **Passage Retrieval Branch** – If the model is “not sure,” it fetches relevant passages from an external corpus, segments them into smaller chunks, and then ranks these chunks by relevance to the query.

This streamlined design reduces unnecessary question decomposition steps, **lowers computational overhead**, and delivers answers more directly—without sacrificing accuracy.

![final](https://github.com/user-attachments/assets/fa6c0c4a-fbba-4a82-8b97-c00b07106032)


## Key Features

- **Two-Branch Flow**  
  Eliminates multi-step decomposition when it provides minimal benefit, focusing instead on immediate retrieval if needed.

- **Efficient Passage Ranking**  
  Splits retrieved documents into smaller segments and ranks them by relevance, allowing the model to focus on only the most pertinent content.

- **Reduced Complexity**  
  Matches or exceeds performance of iterative, multi-module frameworks but operates at a fraction of the overhead.

## Performance

Our evaluations on multiple QA benchmarks—such as **Natural Questions** and **TriviaQA**—indicate that STAR:

- **Matches or surpasses** more complex RAG-based baselines in terms of exact-match accuracy.
- Operates with **fewer retrieval calls and lower token usage**, making it well-suited for real-time or resource-constrained settings.

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/YourUsername/STAR.git
cd STAR
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```
Make sure you have a recent version of Python (>=3.8).

### 3. Run Experiments
Use `main.py` or `main_g.py` to initiate the QA pipeline.
Adjust paths and hyperparameters in `config.py` and `contriever_config.py` as needed.

### 4. Customize Retrieval
- Modify the **Passage Retrieval Branch** to point to your preferred corpus.
- For question-evaluation logic, edit the **Self-Knowledge Branch** or fine-tune it with additional data.


## Citation
If you use or build upon STAR in your work, please cite:

```bibtex
@misc{HayawiShahriar2025STAR,
  title={STAR: Self-Knowledge and Targeted Augmented Retrieval},
  author={Kadhim Hayawi and Sakib Shahriar},
  year={2025},
  howpublished={\url{https://github.com/sakibsh/STAR}},
}
```

## License
**MIT License**

For questions, suggestions, or contributions, feel free to open an issue or submit a pull request. Thank you for using STAR!
