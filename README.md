The codebase focuses on evaluating and comparing multiple techniques to improve the human-likeness of AI-generated text and reduce detectability.

## Modules Description

### Text Generation

* Generates task-specific outputs using Gemini API
* Supports multi-candidate generation for diversity
* Controlled using prompt engineering

### RAG (Retrieval-Augmented Generation)

* Uses FAISS for similarity search
* Retrieves human-written text from CC-News dataset
* Injects retrieved context into prompts
* Improves realism and reduces artificial patterns

### Adversarial Search

* Generates multiple candidate outputs
* Uses dual detectors (RoBERTa + BERT-based discriminator)
* Iteratively refines outputs based on detection score
* Selects lowest-detectability text

### GAN-based Refinement

* Generator produces text candidates
* Discriminator evaluates human-likeness
* Iterative refinement loop improves outputs
* Acts as a proxy GAN setup

### Back-Translation

* Translates text → pivot language → back to English
* Introduces variation in sentence structure and phrasing
* Helps break common AI-generated patterns

### Evaluation Module

* Computes detectability scores
* Uses RoBERTa detector and BERT-based classifier
* Ensures fair comparison across all approaches

## Output

* Generated texts (per topic)
* Detector scores (before vs after refinement)
* Logs of iterative improvements
* Final selected outputs

## Key Observations

* Adversarial search achieves the lowest detectability scores
* RAG improves naturalness via grounding
* GAN improves stylistic quality through refinement
* Back-translation adds variability and reduces repetition

## Technologies Used

* Python
* HuggingFace Transformers
* PyTorch
* SentenceTransformers
* FAISS
* Google Generative AI (Gemini API)

---

## Notes

* This folder contains only implementation code
* Refer to the main report for methodology and analysis
* Ensure API keys (Gemini, etc.) are configured before running

---

## Authors

J Ashwin Balagi, Gopika Ganesan, I S Rajesh, Siddharth M, Tarun Suresh
