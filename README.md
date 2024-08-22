# CS236299 Project 4: Semantic Interpretation - Question Answering

This repository contains the implementation of Project Segment 4 for the CS236299 course. The goal of this project is to build a system for converting natural language queries into SQL queries using semantic parsing techniques. This project involves both rule-based and neural network approaches to achieve the desired task.

## Table of Contents

- [Project Overview](#project-overview)
- [Goals](#goals)
- [Implementation Details](#implementation-details)
- [Setup](#setup)
- [Usage](#usage)
- [Evaluation](#evaluation)
- [Discussion](#discussion)
- [License](#license)

## Project Overview

The primary objective of this project is to develop a semantic parsing system that converts natural language (NL) queries into SQL queries. This project is divided into two main approaches:

1. **Rule-based Approach**: A rule-based semantic parser is implemented to convert text to SQL queries using a pre-defined grammar.
2. **Neural Seq2Seq Model**: An end-to-end sequence-to-sequence model with attention and self-attention mechanisms is implemented to perform the same task.

The project also includes an optional task to implement state-of-the-art pretrained transformers (e.g., BART) for text-to-SQL conversion.

## Goals

1. Build a rule-based semantic parsing system to convert text to SQL queries based on syntactic parse trees.
2. Develop an attention-based end-to-end Seq2Seq model to convert text to SQL.
3. Enhance the Seq2Seq model with self-attention to improve performance.
4. Optionally, implement a transformer-based model for text-to-SQL conversion.
5. Compare the performance and discuss the pros and cons of rule-based and neural approaches.

## Implementation Details

### Rule-based Approach

- **Grammar Development**: The project begins by developing a grammar for parsing natural language queries related to the ATIS dataset. Each syntactic rule in the grammar is augmented with a corresponding semantic rule that translates the parsed structure into an SQL query.
- **Semantic Parsing**: The project uses a bottom-up chart parser from NLTK to parse the input queries according to the developed grammar and then recursively applies the semantic rules to generate SQL queries.
- **Evaluation**: The generated SQL queries are executed against an ATIS database, and the results are compared with the expected results to evaluate the accuracy of the parser.

### Neural Seq2Seq Model

- **Attention Mechanism**: An encoder-decoder model with attention is implemented, allowing the model to focus on different parts of the input sequence when generating the output SQL query.
- **Self-Attention**: The model is further enhanced with self-attention in the decoder, enabling it to consider its previous outputs when generating the next token in the SQL query.
- **Training and Evaluation**: The model is trained on the ATIS dataset, and its performance is evaluated based on the accuracy of the generated SQL queries.

### Transformer-based Approach (Optional)

- **Pretrained Model**: The BART model is used as the base for the text-to-SQL conversion task. The data is reprocessed using the BART tokenizer, and the model is fine-tuned on the ATIS dataset.
- **Evaluation**: The performance of the BART-based model is evaluated and compared with the rule-based and Seq2Seq models.

## Setup

To set up the project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/SamiHam162/NLP236299-Project4.git
   cd NLP236299-Project4
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
3. Download the necessary datasets and scripts as outlined in the `project4_semantics-Submission.ipynb` file.

## Usage

1. **Rule-based Parsing**:
   - Run the Jupyter notebook cells related to rule-based parsing to generate SQL queries from natural language inputs.
2. **Seq2Seq Model**:
   - Train the Seq2Seq model using the provided training script in the notebook.
   - Evaluate the model on the validation and test datasets.
3. **Transformer-based Model**:
   - Fine-tune the BART model as described in the notebook.
   - Evaluate the model's performance on the test set.

## Evaluation

The evaluation of each model is based on the precision, recall, and F1-score metrics, which compare the SQL queries generated by the models to the ground truth SQL queries in the ATIS dataset. The project provides systematic evaluation scripts for both rule-based and neural approaches.

## Discussion

The final section of the project involves a discussion comparing the advantages and disadvantages of the rule-based and neural network approaches. This comparison is based on the experimental results obtained from the evaluation phase.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
