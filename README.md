📝 Text Summarization Using Python & HuggingFace Transformers
This project demonstrates Text Summarization using Python, NLTK, and HuggingFace Transformers in Google Colab. It supports both extractive and abstractive summarization techniques, converting long articles, reports, or text documents into concise summaries. The project provides a practical example of NLP applications in AI-driven content processing.

🚀 Features
Extracts important information from long texts.
Supports extractive summarization (selecting key sentences).
Supports abstractive summarization (generates human-like summaries).
Works directly in Google Colab — no local setup required.
Can be extended for multiple articles, news, or reports.

🧩 Technologies Used
Python 🐍
NLTK (for tokenization & preprocessing)
HuggingFace Transformers (for abstractive summarization)
Google Colab (cloud environment)

⚙️ Installation
Run this in Google Colab:
!pip install transformers
!pip install datasets
!pip install nltk

🧾 Usage
1. Import Libraries
import nltk
from nltk.tokenize import sent_tokenize
from transformers import pipeline

2. Sample Text
text = "Your long text or article goes here..."

3. Extractive Summarization (Basic)
sentences = sent_tokenize(text)
extractive_summary = " ".join(sentences[:2])
print("Extractive Summary:\n", extractive_summary)

4. Abstractive Summarization (Using Transformers)
summarizer = pipeline("summarization")
abstractive_summary = summarizer(text, max_length=80, min_length=30, do_sample=False)
print("Abstractive Summary:\n", abstractive_summary[0]['summary_text'])

5. Summarize Your Dataset
from google.colab import files
import pandas as pd

uploaded = files.upload()
df = pd.read_csv("your_dataset.csv")
article = df['text_column'][0]

summary = summarizer(article, max_length=80, min_length=30, do_sample=False)
print(summary[0]['summary_text'])

🎯 Example Output

Original Text:
"The advent of the transistor in the mid-20th century, specifically the invention at Bell Labs in 1947 by John Bardeen, Walter Brattain, and William Shockley, marked a fundamental turning point in electronics and computing. Before this revolutionary component, electronic circuits relied heavily on bulky, power-hungry, and unreliable vacuum tubes. Vacuum tubes, essentially glass envelopes enclosing electrodes, functioned by controlling the flow of electrons in a vacuum. They generated substantial heat and had an average operational lifespan that necessitated frequent replacement, making large-scale computing machines, such as the ENIAC (Electronic Numerical Integrator and Computer), immense and incredibly costly to maintain. ENIAC, for instance, contained nearly 18,000 vacuum tubes, consumed 150 kilowatts of power, and occupied 1,800 square feet of floor space.
The transistor, a semiconductor device, offered a radically superior alternative. Utilizing the properties of materials like silicon and germanium, it could perform the same functions—amplification and switching—as a vacuum tube, but in a solid state. This meant it was significantly smaller, more durable, consumed vastly less power, and generated minimal heat. Early transistors were point-contact transistors, but the later development of the junction transistor and, critically, the invention of the integrated circuit (IC) by Jack Kilby and Robert Noyce, truly catalyzed the digital revolution. The integrated circuit allowed thousands, and eventually billions, of transistors to be fabricated onto a single, small silicon chip, leading directly to the microprocessors that power all modern computing devices, from smartphones to supercomputers. The exponential improvement in chip density, famously predicted by Moore's Law, has continued this trend for decades, driving down costs and increasing processing power at an astonishing rate.
The global economic and social impact of this shift is incalculable. The miniature, robust nature of semiconductor technology facilitated the space race—enabling the creation of compact, reliable guidance systems—and subsequently the proliferation of personal computers in the 1980s. Without the transistor and the IC, the development of the internet and the mobile communication infrastructure we rely on today would have been impossible. The story of the transistor, therefore, is not just a technological narrative; it is a foundational chapter in the history of the information age itself."

Extractive Summary:
"The advent of the transistor in the mid-20th century, specifically the invention at Bell Labs in 1947 by John Bardeen, Walter Brattain, and William Shockley, marked a fundamental turning point in electronics and computing. Before this revolutionary component, electronic circuits relied heavily on bulky, power-hungry, and unreliable vacuum tubes"

Abstractive Summary:

"The advent of the transistor in the mid-20th century marked a fundamental turning point in electronics and computing . Before this revolutionary component, electronic circuits relied heavily on bulky, power-hungry, and unreliable vacuum tubes . The transistor, a semiconductor device, offered a radically superior alternative ."

🛠️ Future Improvements
Batch summarization for multiple articles at once.
Integrate custom datasets or news APIs.
Combine summarization with translation for multilingual summaries.
Build a simple web interface using Streamlit or Flask.
