# Licenses, compliances, pirated datasets

## Table of Contents

- [Licenses, compliances, pirated datasets](#licenses-compliances-pirated-datasets)
  - [Table of Contents](#table-of-contents)
  - [AI training data](#ai-training-data)
    - [**The Licensing Landscape: Open Weights vs. "Strings Attached"**](#the-licensing-landscape-open-weights-vs-strings-attached)
    - [**The Use of Unlicensed and Pirated Datasets**](#the-use-of-unlicensed-and-pirated-datasets)
    - [**Compliance and Legal Secrecy**](#compliance-and-legal-secrecy)
    - [**The Ethical Perspective**](#the-ethical-perspective)

## AI training data

The sources provide a detailed look at the legal and ethical complexities surrounding AI training data, specifically focusing on the distinctions between various licenses, the use of unlicensed or pirated content, and the resulting legal consequences for major AI labs.

### **The Licensing Landscape: Open Weights vs. "Strings Attached"**

A major distinction exists between the licensing of Western open-weight models and their Chinese counterparts.

- **Restricted Licenses:** Models like Meta’s **Llama** or Google’s **Gemma** are not truly "unrestricted." They come with "strings attached," such as requirements for companies to report their financial situation to the developer if they exceed a specific user threshold (e.g., 700 million users).
- **Unrestricted Chinese Licenses:** In contrast, Chinese companies often release models under **"unrestricted open source licenses"** to gain international influence. Because many US companies avoid paying for Chinese API subscriptions due to security concerns, these unrestricted licenses allow Chinese labs to capture a share of the growing AI expenditure market.
- **Truly Open Source:** A "fully open" model, such as **OLMo**, distinguishes itself by releasing not just the weights, but the **training code and the underlying data** so researchers can understand and replicate the process.

### **The Use of Unlicensed and Pirated Datasets**

The sources highlight a growing tension between massive web-scrapes and the rights of content creators:

- **Unlicensed Web Scrapes:** Most models are trained on **Common Crawl**, a scrape of the entire internet. This data is considered **"largely unlicensed,"** meaning explicit consent from the website owners or creators has not been provided.
- **The "Gray Zone" of Purchased Content:** There is significant legal debate over whether buying a book (e.g., via Kindle or Manning) and then using it for AI training is permitted. This is currently viewed as a **"gray zone"** because while the content was paid for, the license to read may not include a license to train a model.
- **Pirated and Torrented Data:** The most severe legal risks arise from using **pirated books**. The sources mention that **Anthropic** was found culpable in a "mind-boggling" lawsuit where they were ordered to pay **$1.5 billion to authors**. While they were legally cleared for books they had bought and scanned, they were penalized for using **torrented (pirated) books** to train their models.

### **Compliance and Legal Secrecy**

Due to these copyright and licensing risks, AI labs have become increasingly secretive about their datasets:

- **Guarded Secrets:** A model's training data is now one of its **closest guarded secrets** for legal reasons. Developers even train models specifically **not to reveal their sources** to avoid providing evidence for potential lawsuits.
- **Compliance Efforts:** Some research consortiums, such as Apertus in Switzerland, are building models designed specifically for **EU compliance**. These projects focus on ensuring the model fits specific regulatory checks regarding data governance and licensing.
- **The Move Toward Explicit Licensing:** There is a growing movement to train models only on **explicitly licensed data**, where a governing contract is provided for every piece of information used, ensuring total legal safety.

### **The Ethical Perspective**

For authors and creators, the current state of AI training often feels like **"theft"**. The sources suggest that the industry may eventually need a **compensation scheme** similar to what Spotify created for music streaming, ensuring that authors receive credit and financial reward when their work is used to power AI intelligence.
