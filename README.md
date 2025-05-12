# 🧾 HSN Code Validation Agent

This project implements an **intelligent agent** for validating **HSN (Harmonized System Nomenclature)** codes using the Google ADK (Agent Developer Kit) conceptual framework. The agent validates user-provided HSN codes against a master dataset (Excel file) and returns validation results with descriptions.

---

## 📌 Features

- ✅ Accepts single or multiple HSN codes
- 🧠 Validates codes for:
  - Format correctness (length, digits)
  - Existence in master dataset
  - (Optional) Hierarchical structure presence
- 📄 Excel-based master dataset (`HSN_Master_Data.xlsx`)
- 🔍 Designed using ADK-style components (Intent, Entity, Fulfillment)

---

## 🚀 How to Run (Colab)

1. Open the [Colab Notebook](link-to-colab-if-public)
2. Upload the `HSN_Master_Data.xlsx` file from [Google Drive](https://docs.google.com/spreadsheets/d/1UD4JAAQ6Fgeyc5a1OwBiLV2cPTAK_D2q/edit)
3. Enter HSN codes in the input box (comma-separated)
4. Run the notebook cells to get validation results

---

## 🧠 Agent Design (Based on ADK)

| ADK Concept   | Component Description                                   |
|---------------|---------------------------------------------------------|
| **Intent**    | `ValidateHSNCode`: Triggered when the user asks to validate codes |
| **Entity**    | `HSNCode`: Extracted 2–8 digit numeric values           |
| **Fulfillment** | Python function that loads the dataset and validates codes |
| **Response**  | Returns confirmation or error with description or reason |

---

## ⚙️ Validation Logic

### ✅ Format Validation
- HSN code must be numeric and 2, 4, 6, or 8 digits long

### ✅ Existence Validation
- HSN code must be present in the `HSNCode` column of the Excel dataset

### 🧱 Optional: Hierarchical Validation
- For codes like `01011010`, checks for parent codes (`01`, `0101`, etc.)

---

## 📂 Project Structure

```

HSN-Validation-Agent/
│
├── HSNcodeValidationagent.ipynb     # Main Colab notebook
├── HSN_Master_Data.xlsx           # Master dataset (uploaded manually)
├── README.md                      # This documentation

````

---

## 📈 Sample Output

```text
✅ HSN Code 0101 is valid.
   → Description: LIVE HORSES, ASSES, MULES AND HINNIES.

❌ HSN Code 999999 is invalid.
   → Reason: Not found in master dataset.
````

---

## 📖 References

* [Google ADK Framework](https://google.github.io/adk-docs/)
* [HSN Code Master Data (Google Sheets)](https://docs.google.com/spreadsheets/d/1UD4JAAQ6Fgeyc5a1OwBiLV2cPTAK_D2q)

---

## 👨‍💻 Author

**Yash Pal Singh Negi**
*2023 Engineering Graduate | ML Enthusiast | Agent Design Project*

---

## 📜 License

This project is for academic demonstration and interview discussion purposes.

