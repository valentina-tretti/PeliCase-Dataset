# PeliCase Dataset

**PeliCase** is a linguistic corpus consisting of Spanish-language YouTube comments concerning the Pelicot court case. The dataset was collected in November 2024 (prior to the court ruling) strictly for academic, scientific, and computational linguistics research purposes.

---

## Corpus Overview

* **Extraction Period:** November 2024 (prior to the court verdict).
* **Comment Date Range:** September 2, 2024 – November 11, 2024.
* **Coverage:** 46 videos across 38 YouTube channels.
* **Channel Typology:** News, podcasts, and radio broadcasts.
* **Available Formats:** JSON (`.json`) and CSV (`.csv`).
* **Extraction Software:** MAXQDA2020 (VERBI Software, 2021).

---

## Video Selection Criteria

Videos included in the corpus were selected based on two strict criteria:
1. **Narrative Focus:** The video explicitly covers the Pelicot case as its main narrative focus.
2. **Language and Accessibility:** The video is narrated in Spanish and features Spanish subtitles whenever French-speaking participants appear.

*Note:* Video duration ranges from 1 to 57 minutes. For detailed metadata regarding channel categorization, please refer to the supplementary file `Supplemental_Material_Dataset.csv`.

---

## Anonymization and Ethics Statement

Due to the sensitive nature of the topic:
* **Privacy Protection:** All usernames have been anonymized and replaced with the generic tag `@user`.
* **Exclusive Use:** The corpus is shared solely for scientific research, discourse analysis, and social/linguistic studies.
* **Data Minimization:** No Personally Identifiable Information (PII) beyond the public, anonymized comment text has been collected or distributed.

---

## Data Structure

The `.json` and `.csv` files contain the following attributes:

| Column Name | Description |
| :--- | :--- |
| `corpus_id` | Unique comment identifier within the corpus. |
| `extraction_id` | Comment identifier assigned during extraction in MAXQDA. |
| `comment_anonimized` | Anonymized comment text (usernames replaced with `@user`). |
| `base_comment` | `yes` if it is a top-level video comment; `no` if it is a reply to another comment. |
| `publication_date_comment` | Publication timestamp of the comment. |
| `title_video` | Original title of the YouTube video. |
| `type_of_video` | Content classification (`news`, `radio`, `podcast`). |
| `publication_date` | Publication date of the video. |
| `channel_id` | Unique channel identifier assigned within the corpus. |
| `video_url` | Direct URL to the original video. |
| `fully_processed_comment` | Preprocessed text (lowercased, punctuation removed, emojis stripped). |

---

## Usage Example (Python)

```python
import pandas as pd

# Load corpus from CSV file
df_csv = pd.read_csv("pelicase_dataset.csv")

# Load corpus from JSON file
df_json = pd.read_json("pelicase_dataset.json")

print(f"Total comments loaded: {len(df_csv)}")
print(df_csv[["corpus_id", "comment_anonimized", "type_of_video"]].head())

## License and Terms of Use

The dataset and metadata collected in this repository are distributed under the **[Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/)** license.

**Note on Third-Party Rights:**
- The original comments remain the intellectual property of their respective authors on YouTube and are distributed under the *Fair Use* doctrine exclusively for non-profit academic, scientific, and linguistic research purposes.
- The use of this dataset is subject to ongoing compliance with the [YouTube Terms of Service](https://www.youtube.com/t/terms).

