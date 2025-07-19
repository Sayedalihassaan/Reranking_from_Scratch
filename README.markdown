# Document Reranking Project

## Overview
This project implements a document reranking system using both **Sentence Transformers** for initial semantic similarity ranking and a **Cross-Encoder** for refined reranking. The goal is to retrieve and rank documents based on their relevance to a given query, leveraging natural language processing (NLP) techniques. The system uses a dataset of sample documents, encodes them into embeddings, and ranks them based on cosine similarity and cross-encoder scores.

The project is implemented in Python using a Jupyter Notebook (`Reranking_from_Scratch.ipynb`) and relies on libraries such as `sentence-transformers`, `scikit-learn`, and `rank_bm25`.

## Features
- **Document Encoding**: Uses a pre-trained Sentence Transformer model (`paraphrase-xlm-r-multilingual-v1`) to convert documents and queries into dense embeddings.
- **Initial Ranking**: Computes cosine similarity between query and document embeddings to rank documents.
- **BM25 Integration**: Applies the BM25 algorithm to the top-ranked documents for additional ranking based on term frequency.
- **Cross-Encoder Reranking**: Refines the ranking using a cross-encoder model (`ms-marco-MiniLM-L-6-v2`) for improved relevance scoring.
- **Sample Dataset**: Includes a small set of documents related to keyword extraction and search techniques for demonstration.

## Prerequisites
To run this project, ensure you have the following installed:
- Python 3.10 or higher
- Jupyter Notebook or JupyterLab
- Required Python libraries (listed in `requirements.txt`)

## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/document-reranking.git
   cd document-reranking
   ```

2. **Set Up a Virtual Environment** (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**:
   Install the required Python packages using the provided `requirements.txt`:
   ```bash
   pip install -r requirements.txt
   ```

   If `requirements.txt` is not provided, install the following packages manually:
   ```bash
   pip install sentence-transformers numpy scikit-learn rank-bm25
   ```

4. **Download Models**:
   The project uses pre-trained models from the `sentence-transformers` library. These will be automatically downloaded when the code is run for the first time.

## Usage
1. **Open the Jupyter Notebook**:
   Start Jupyter Notebook or JupyterLab:
   ```bash
   jupyter notebook
   ```
   Open the `Reranking_from_Scratch.ipynb` file in your browser.

2. **Run the Notebook**:
   Execute the cells in the notebook sequentially to:
   - Load the sample documents and query.
   - Encode documents and query using Sentence Transformers.
   - Compute initial rankings using cosine similarity.
   - Apply BM25 for additional ranking (optional).
   - Rerank the top documents using a Cross-Encoder.
   - Display the ranked documents with their similarity scores.

3. **Customize the Dataset**:
   Modify the `documents` list in the first cell of the notebook to include your own documents. Update the `query` variable to test different queries.

4. **View Results**:
   The notebook outputs:
   - Initial document embeddings.
   - Cosine similarity scores for each document.
   - BM25 scores for the top-ranked documents.
   - Final reranked documents with cross-encoder scores.

## Project Structure
```
document-reranking/
│
├── Reranking_from_Scratch.ipynb  # Main Jupyter Notebook with the implementation
├── README.md                    # This file
├── requirements.txt             # Python dependencies
└── LICENSE                      # License file (e.g., MIT License)
```

## Example
The notebook includes a sample query:
```
"Natural language processing techniques enhance keyword extraction efficiency."
```
It ranks a set of documents, such as:
- "Efficient keyword extraction enhances search accuracy."
- "Machine learning algorithms can optimize keyword extraction methods."
- ...

The output will display the ranked documents with their similarity scores, followed by the reranked results using the cross-encoder.

## Limitations
- **BM25 Issue**: The current implementation shows zero BM25 scores due to a potential issue with tokenization or input format. This needs further debugging (e.g., ensuring proper tokenization of documents for BM25).
- **Scalability**: The project uses a small dataset for demonstration. For large datasets, consider optimizing the embedding and ranking processes.
- **Model Selection**: The chosen Sentence Transformer and Cross-Encoder models are lightweight but may not be optimal for all use cases. Experiment with other models for better performance.

## Future Improvements
- Fix the BM25 scoring issue by ensuring proper tokenization and input handling.
- Add support for larger datasets and batch processing.
- Integrate additional ranking algorithms or hybrid approaches.
- Provide a command-line interface or web app for easier interaction.
- Experiment with other transformer models for improved accuracy.

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit (`git commit -m "Add feature"`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

Please ensure your code follows the project's coding style and includes appropriate tests.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
For questions or suggestions, feel free to open an issue or contact the repository owner at [your-email@example.com](mailto:your-email@example.com).