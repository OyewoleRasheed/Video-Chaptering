## 📼 Video Chaptering Using Python

Automatically segment a video transcript into meaningful chapters using **topic modeling** and **semantic shifts**.

---

### 📌 Features

* Extracts text transcript from a video.
* Applies topic modeling (LDA/NMF) to detect dominant topics.
* Finds logical breakpoints based on topic transitions.
* Groups segments into coherent **chapters**.
---

### 🧰 Requirements

Install required packages:

```bash
pip install numpy pandas sklearn matplotlib nltk google-api-python-client
```


### 📁 Project Structure

```plaintext
video_chaptering/
│
├── video_chaptering.py         # Main script
├── 71op1DQ2gyo_transcript.csv              # Input transcript (timestamped)
├── chapters_output.json        # Output: list of chapters and topics
├── README.md                   # This file
```

---

### 🧠 How It Works

1. **Transcript Input**
   A CSV file with columns like:

   * `start`: Start time of the segment
   * `text`: Text spoken during the segment

2. **Text Exploration**

   * Checking the distribution of text lengths and geting the most common words

3. **Topic Modeling**

   * Apply LDA or NMF to extract `n` topics
   * Assign each segment its **dominant topic**

4. **Logical Break Detection**

   * Find points where the topic changes
   * Merge consecutive segments with the same topic

5. **Chapter Creation**

   * Create final chapters based on these breaks
   * Optionally generate summaries

---

### 🚀 Usage

```bash
python video_chaptering.py
```

Or use the functions in your own script:

```python
from video_chaptering import generate_chapters

chapters = generate_chapters("transcript.csv", model="lda", num_topics=5)
```

---

### 📝 Example Output

```json
[
  {
    "start_time": 0.0,
    "topic": 2,
    "text": "Introduction to AI and its impact on daily life..."
  },
  {
    "start_time": 120.0,
    "topic": 0,
    "text": "Now let's explore neural networks and deep learning..."
  }
]
```

---



### 🙏 Credits

Inspired by [AmanXAI - Video Chaptering using Python](https://amanxai.com/2024/06/24/video-chaptering-using-python/).

---

### 📄 License

MIT License – free to use, modify, and distribute.

