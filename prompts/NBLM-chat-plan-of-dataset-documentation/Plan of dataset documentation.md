### **Phase 1: Structural Discovery**

**Goal:** Determine the physical shape and health of the file (encoding, delimiter, and row/column count).

**The Output:** A technical summary of the file’s metadata, including any corrupted lines or unexpected formatting.

**Quality Check:** I will provide the raw "head" (first 5–10 lines) of the file. You should visually verify that the columns align correctly and that characters aren't replaced by "" (which indicates an encoding error).

### **Phase 2: Schema Decoding**

**Goal:** Identify the data types (dates, integers, strings) and hypothesize what each column represents.

**The Output:** A table mapping column names to their inferred meaning and data format.

**Quality Check:** I will provide a list of "Unique Value Samples" for each column. If a column is labeled "Year" but contains values like 3.14 or Washington, we know the inference was a hallucination.

### **Phase 3: Statistical Validation**

**Goal:** Uncover the "story" of the data through distributions, ranges, and missing values.

**The Output:** A descriptive statistics report (mean, median, min/max for numbers; frequency counts for categories) and a "Missingness Map" highlighting where data is gapped.

**Quality Check:** Cross-reference the "Min/Max" values against the column's logic. If a "Birth Year" column shows a maximum value of $2029$ (and it's currently 2026), we’ve caught an entry error or a projection.

### **Phase 4: The Final Codebook**

**Goal:** Synthesize all previous findings into a single, authoritative Dataset Documentation (Codebook).

**The Output:** A Markdown or PDF document containing:

* **Dataset Name & Source** (if identified).  
* **Column Index:** Name, Type, and Description.  
* **Value Key:** Definition of any codes or abbreviations (e.g., Status 1 \= Active).  
* **Known Limitations:** Notes on missing data or outliers.  
  **Quality Check:** I will generate a small "Synthetic Sample" based strictly on the rules of the codebook. If that sample looks fundamentally different from the original data, the documentation needs a rewrite.

