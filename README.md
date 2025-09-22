Resume Parser Benchmarking with Free-Tier LLMs
This project benchmarks multiple free-tier large language models (LLMs) to identify the best performer for automated resume parsing. It evaluates models based on accuracy, latency, and reliability, then uses the top-ranked model to extract structured information(name, email, skills) from resumes.

Project Overview
1. Goal: Find the most effective free-tier LLM for extracting name, email, and skills from resumes. Both PDF and word files are compatible formats. 

2. Approach:
Test multiple LLMs (e.g., Gemini Flash, Gemini Pro, Gemini 2.5 variants)

Evaluate each model on:

(1) Success rate (valid JSON returned)

(2) Response time

(3) Accuracy (name/email match)

(4) Skills precision, recall, and F1 score

Select the best-performing model. Use it to parse a batch of resumes (PDF and/or DOCX).

3. Benchmarking Metrics
Each model is evaluated across 18 resumes using the following metrics:

Metric	Description
Success Rate: % of resumes parsed without error
Response Time: Average time per resume
Name Match Accuracy:Exact match with ground truth
Email Match Accuracy:Exact match with ground truth
Skills Precision:% of predicted skills that are correct
Skills Recall:% of actual skills that were successfully parsed
Skills F1 Score:Harmonic mean of precision and recall

4. Models Tested
gemini-2.5-pro, 
gemini-1.5-flash-latest,
gemini-1.5-pro-latest,
gemini-1.5-pro,
gemini-1.5-flash-8b-latest,
gemini-2.5-flash,
gemini-2.0-flash


🥇 Best Performing Model
Based on the evaluation, the best model was: gemini-1.5-flash-8b-latest
It achieved the highest balance of accuracy, speed, and reliability across all metrics.

5. Resume Parsing Pipeline
Once the best model is selected, it is used to parse resumes from a local folder. The pipeline supports:

✅ PDF and DOCX formats
✅ Robust error handling
✅ Case-insensitive evaluation
✅ Ground truth comparison for accuracy scoring

6. API Key Safety
To keep your API key secure:
Store it in a .env file (not in the notebook)
Load it using python-dotenv
Add .env to .gitignore to prevent accidental exposure

How to Run
Clone the repo:

bash
git clone https://github.com/yourusername/resume-parser-benchmark.git
cd resume-parser-benchmark
Install dependencies:

bash
pip install -r requirements.txt
Set your API key in .env:

Code
GEMINI_API_KEY=your-api-key-here
Launch the notebook and run all cells.

📈 Output
Parsed results saved as JSON

Benchmark metrics logged and visualized

Bar charts comparing model performance

👩‍💻 Author
Built by Jiejie — neuroscientist turned data scientist, passionate about AI, education, and inclusive tech.