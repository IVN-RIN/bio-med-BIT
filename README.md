# Data and source code for *Localising In-Domain Adaptation of Transformer-Based Biomedical Language Models*

Manuscript available at [arxiv.org/abs/2212.10422](https://arxiv.org/abs/2212.10422)


## Abstract

In the era of digital healthcare, the huge volumes of textual information generated every day in hospitals constitute an essential but underused asset that could be exploited with task-specific, fine-tuned biomedical language representation models, improving patient care and management. For such specialized domains, previous research has shown that fine-tuning models stemming from broad-coverage checkpoints can largely benefit additional training rounds over large-scale in-domain resources. However, these resources are often unreachable for less-resourced languages like Italian, preventing local medical institutions to employ in-domain adaptation. In order to reduce this gap, our work investigates two accessible approaches to derive biomedical language models in languages other than English, taking Italian as a concrete use-case: one based on neural machine translation of English resources, favoring quantity over quality; the other based on a high-grade, narrow-scoped corpus natively written in Italian, thus preferring quality over quantity. Our study shows that data quantity is a harder constraint than data quality for biomedical adaptation, but the concatenation of high-quality data can improve model performance even when dealing with relatively size-limited corpora. The models published from our investigations have the potential to unlock important research opportunities for Italian hospitals and academia. Finally, the set of lessons learned from the study constitutes valuable insights towards a solution to build biomedical language models that are generalizable to other less-resourced languages and different domain settings.

*Keywords*: Natural Language Processing | Deep Learning | Language Model | Biomedical Text Mining | Transformer

*Correspondence*: buonocore.tms@gmail.com

## NLP Checkpoints

Best-performing checkpoints have been published on the [Huggingface Hub](https://huggingface.co/IVN-RIN) 


| Model      | Domain  | Type              | Details                                                     |
|------------|---------|-------------------|-------------------------------------------------------------|
| [BioBIT](https://huggingface.co/bmi-labmedinfo/bioBIT)| Biomedical | MaskedLM Pretrain | BERT model trained after [dbmdz/bert-base-italian-xxl-cased](https://huggingface.co/dbmdz/bert-base-italian-xxl-cased) with 28GB Pubmed abstracts (as in BioBERT) that have been translated from English into Italian using Google Neural Machine Translation (GNMT). |
| [MedBIT](https://huggingface.co/bmi-labmedinfo/medBIT)| Medical | MaskedLM Pretrain | BERT model trained after [BioBIT](https://huggingface.co/bmi-labmedinfo/bioBIT) with additional 100MB of medical textbook data without any regularization. |
| [MedBIT-R3+](https://huggingface.co/bmi-labmedinfo/medBIT-r3-plus) (recommended)| Medical | MaskedLM Pretrain | BERT model trained after [BioBIT](https://huggingface.co/bmi-labmedinfo/bioBIT) with additional 200MB of medical textbook data and web-crawled medical resources in Italian. Regularized with LLRD (.95), Mixout (.9), and Warmup (.02). |
