Each checkpoint weights more than 500MB, therefore it is not feasible to host them on a GitHub repository.
The best performing models are published on [HuggingFace](https://huggingface.co/IVN-RIN).


| Model      | Domain  | Type              | Details                                                     |
|------------|---------|-------------------|-------------------------------------------------------------|
| [BioBIT](https://huggingface.co/bmi-labmedinfo/bioBIT)| Biomedical | MaskedLM Pretrain | BERT model trained after [dbmdz/bert-base-italian-xxl-cased](https://huggingface.co/dbmdz/bert-base-italian-xxl-cased) with 28GB Pubmed abstracts (as in BioBERT) that have been translated from English into Italian using Google Neural Machine Translation (GNMT). |
| [MedBIT](https://huggingface.co/bmi-labmedinfo/medBIT)| Medical | MaskedLM Pretrain | BERT model trained after [BioBIT](https://huggingface.co/bmi-labmedinfo/bioBIT) with additional 100MB of medical textbook data without any regularization. |
| [MedBIT-R3+](https://huggingface.co/bmi-labmedinfo/medBIT-r3-plus) (recommended)| Medical | MaskedLM Pretrain | BERT model trained after [BioBIT](https://huggingface.co/bmi-labmedinfo/bioBIT) with additional 200MB of medical textbook data and web-crawled medical resources in Italian. Regularized with LLRD (.95), Mixout (.9), and Warmup (.02). |
