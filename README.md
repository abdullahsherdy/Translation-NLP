# Translation NLP

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

A comprehensive machine translation system for Arabic-English language pairs, implementing state-of-the-art transformer models with evaluation metrics and a user-friendly GUI interface.

## Features

- Bilingual translation between Arabic and English
- State-of-the-art MarianMT transformer model
- Comprehensive evaluation using BLEU and ROUGE scores
- Interactive translation interface
- User-friendly GUI application
- Detailed visualization and reporting
- GPU acceleration support
- Caching for improved performance

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/translation-nlp.git
cd translation-nlp
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Dependencies

The project requires the following Python packages:

```python
datasets>=2.0.0
scikit-learn>=1.0.0
pandas>=1.3.0
numpy>=1.20.0
matplotlib>=3.4.0
seaborn>=0.11.0
transformers>=4.0.0
nltk>=3.6.0
emoji>=1.6.0
torch>=1.9.0
wordcloud>=1.8.0
arabic-reshaper>=2.1.0
python-bidi>=0.4.0
rouge-score>=0.0.4
tkinter  # Usually comes with Python installation
```

## Project Structure

```
translation-nlp/
├── NLP.py                 # Main implementation file
├── translation_gui.py     # GUI implementation
├── requirements.txt       # Project dependencies
├── README.md             # Project documentation
├── visualizations/       # Generated visualizations
├── fine_tuned_models/    # Saved model checkpoints
└── logs/                 # Training and evaluation logs
```

## Usage

### Command Line Interface

```python
from NLP import BilingualTranslationPipeline

# Initialize pipeline for Arabic to English translation
pipeline = BilingualTranslationPipeline('ar-en')

# Run the complete pipeline
pipeline.run_pipeline()

# Use interactive translation mode
pipeline.interactive_translation_test()
```

### Graphical User Interface

The project includes a user-friendly GUI application built with tkinter. To launch the GUI:

```bash
python translation_gui.py
```

#### GUI Features

1. **Translation Direction Selection**
   - Radio buttons to switch between Arabic→English and English→Arabic translation
   - Real-time direction updates

2. **Text Input/Output**
   - Large text areas for input and output
   - Scrollable text areas for long translations
   - Clear button to reset both text areas

3. **Translation Controls**
   - Translate button to perform translation
   - Status bar showing current state and translation time
   - Asynchronous translation (non-blocking UI)

4. **Error Handling**
   - Clear error messages in status bar
   - Input validation
   - Graceful error recovery

#### GUI Usage

1. Launch the application:
   ```bash
   python translation_gui.py
   ```

2. Select translation direction:
   - Click "Arabic → English" for Arabic to English translation
   - Click "English → Arabic" for English to Arabic translation

3. Enter text:
   - Type or paste text in the "Input Text" area
   - Text can be in either Arabic or English depending on the selected direction

4. Translate:
   - Click the "Translate" button
   - Wait for the translation to complete
   - View the result in the "Translation" area

5. Clear text:
   - Click "Clear" to reset both input and output areas

### Evaluation

```python
# Run evaluation on a specific number of samples
pipeline.evaluate_translations(num_samples=100)
```

## Implementation Details

### Model Configuration

The system supports two translation directions:
- Arabic to English (ar-en)
- English to Arabic (en-ar)

Each direction has its own configuration including:
- Pre-trained model selection
- Language-specific stopwords
- Preserved words

### Evaluation Metrics

#### BLEU Score
- Range: 0 to 1 (higher is better)
- Measures translation precision
- Considers n-gram matches

#### ROUGE Scores
- Range: 0 to 1 (higher is better)
- Measures translation recall
- Three variants:
  - ROUGE-1: Single word matches
  - ROUGE-2: Two-word phrase matches
  - ROUGE-L: Longest common subsequence

### Visualization

The system generates several visualizations:

1. **Word Clouds**
   - Shows most frequent words in both languages
   - Helps in understanding vocabulary distribution

2. **Length Distributions**
   - Displays sentence length patterns
   - Helps in identifying optimal sequence lengths

3. **Training Metrics**
   - Shows training loss over time
   - Helps in monitoring model convergence

4. **Evaluation Scores**
   - BLEU score distribution
   - ROUGE scores comparison
   - Helps in understanding translation quality

## Output Files

The pipeline generates several output files:

- `translation_log_{direction}.txt`: Detailed training logs
- `evaluation_results_{direction}.txt`: Evaluation metrics
- `final_report_{direction}.txt`: Comprehensive pipeline report
- Visualizations in the `visualizations/` directory

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Helsinki-NLP](https://huggingface.co/Helsinki-NLP) for the pre-trained models
- [Hugging Face](https://huggingface.co/) for the transformers library
- [NLTK](https://www.nltk.org/) for natural language processing tools 