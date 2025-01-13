---
title: "The Open Arabic LLM Leaderboard 2"
thumbnail: /blog/assets/leaderboards-on-the-hub/thumbnail_arabic.png
authors:
- user: alielfilali01
  guest: true
  org: 2A2I
- user: Manel-Hik
  guest: true
  org: OALL
- user: tarickMorty
  guest: true
  org: OALL
- user: amztheory
  guest: true
  org: tiiuae
- user: rcojocaru
  guest: true
  org: tiiuae
- user: Basma-b
  guest: true
  org: tiiuae
- user: HakimHacid
  guest: true
  org: tiiuae
- user: clefourrier

---

# The Open Arabic LLM Leaderboard 2

## Current status of Arabic LLMs leaderboards --> Ali + Basma (DONE)
The growing availability of LLMs supporting Arabic, both as monolingual and multilingual models, prompted the community to create dedicated Arabic language leaderboards. 

Previously, Arabic-focused leaderboards were typically confined to narrow benchmarks introduced by specific authors, often as demos for their work. In these cases, the authors would set up leaderboards to demonstrate how models performed on a particular task or dataset. Alternatively, other leaderboards required users to run evaluations on their own computing resources and then submit a JSON file containing their results for display.

While these approaches helped spark initial interest in Arabic benchmarking, they also introduced several challenges:
1. **Resource Limitations**: Many community members lack access to the substantial computational resources needed to evaluate their models—especially if they want to conduct frequent, iterative experiments (e.g., testing a new fine-tuning technique or hyperparameter setting) which helps improving the models capabilities in Arabic and contribute to the collective research efforts by the community. This high cost in both time and compute power can become a major barrier to participation.

2. **Integrity of Reported Results**: Because some platforms required users to evaluate their models independently and then simply submit a file of scores, there was no robust mechanism to ensure those results were accurate or even produced through a genuine evaluation. This lack of centralized verification could potentially undermine the credibility and fairness of the leaderboard.

These limitations underscore the need for a more unified, accessible, and transparent benchmarking platform—one that not only enables but encourages genuine and reproducible experimentation for the entire Arabic NLP community.

In May 2023, 2A2I, TII, and HuggingFace launched the Open Arabic LLM Leaderboard, the first on HuggingFace to feature over 50 selective Arabic benchmarks including reading comprehension, sentiment analysis, and question answering. Shortly after, a collaboration between SDAIA and the King Salman Global Academy for Arabic Language introduced the Balsam Index, which includes approximately 1,400 datasets with 50,000 questions covering 67 tasks, such as grammar correction, paraphrasing, cause-and-effect classification, and text comprehension. Later, in December, Inception and MBZUAI unveiled the AraGen Leaderboard, a generative tasks evaluation pipeline, which introduced the 3C3H evaluation measure, uses dynamic evaluation cycles with private testing, and provides a specialized Arabic evaluation dataset to assess LLMs across four main tasks.

## Impact of the previous leaderboard --> Ahmed + Basma

In less than 7 months after its launch, the first version of the Open Arabic LLM Leaderboard quickly became a vital platform for the Arabic AI community, attracting over 40,000 unique visitors and more than 3,000 visits in the past month. The HuggingFace space received over 100 likes and 6 citations on Google Scholar. The community submitted more than 700 models, ranging from 1B to over 70B parameters. The leaderboard sparked numerous engaging discussions across social media, HuggingFace, Reddit, and more, making it the most prominent Arabic leaderboard to date.

- citations -> Rux
- likes
- total models submitted
- plot activity per month --> Rux
- compare to other language leaderboards

| Total visits        |  45,135 |
| Total likes         |     119 |
| Models evaluated    |     698 |
| Model organizations |     184 |
| Academic citations  |       8 |

<p align="center">
    <img src="https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/leaderboard-arabic-v2/leaderboard_comparison.png" />
</p>

## Why do we need a new leaderboard ? --> Ali
- Translated tasks are not suitable/issues
- Cultural irrelevancy in previous version
- We want Arabic related benchmarks: Arabic grammar, historical relevant,
- Cite some discussions from the community (critics of OALL)
- Justify the deletion of some benchmarks (saturation on some benchmarks, some of them are MT)

---

Recent community discussions, including critiques of the Open Arabic LLM Leaderboard (OALL) and similar projects, have revealed significant gaps in current benchmarking approaches. Researchers, developers, and language enthusiasts have called for more direct evaluations of Arabic-centric tasks, greater transparency in benchmark creation, and more inclusive datasets that span different dialects, domains, and applications. Addressing these concerns has been a key driver behind the design of the new leaderboard.

Arabic poses unique challenges and features that deserve specialized evaluation, beyond those captured by general-purpose NLP tasks. These include aspects such as Arabic grammar, complex morphology, dialectal diversity, and culturally sensitive safety-related questions. A leaderboard that focuses on these nuances can more effectively assess how well models perform in real-world Arabic language contexts.

A significant portion of the datasets and tasks used in the first version of OALL stemmed from content or contexts tied to non-Arabic-speaking regions. These tasks, when repurposed for Arabic, often failed to resonate with real-world use cases or address the practical needs of Arabic-speaking communities. Additionally, many of the tasks relied on direct translations from English, which frequently resulted in linguistic and contextual mismatches. Subtle morphological and syntactic nuances unique to Arabic were often lost in the translation process, making these tasks less reliable measures of true Arabic language understanding and modeling.

By incorporating evaluation tasks developed natively in Arabic, in this new leaderboard we try to capture essential aspects of the language, such as its rich morphology, nuanced syntax, and context-specific usage that are often overlooked in translated tasks. This shift ensures more authentic and meaningful benchmarks for assessing Arabic LLM performance.

Also, it is worth mentioning that over time, we observed that some benchmarks used in the first version of OALL became saturated. Models achieved near-maximum scores, rendering these benchmarks less useful for distinguishing between incremental improvements. To address this, the new leaderboard removes or replaces such tasks, ensuring a more up-to-date evaluation suite.

As part of this release, we also introduce ALRAGE (Arabic Language RAG Evaluation), a public, native Arabic benchmark designed to assess model performance in simulated RAG scenarios. ALRAGE evaluates how effectively models handle Arabic-specific challenges in retrieval and generation, offering a robust metric for tasks that simulate real-world usage of RAG-based systems.

---

## What's new in this version ? --> Rux + Manel
- keep alghafa native tasks
- Arabic MMLU native 
- Arabic-MMLU-HT
- Madina QA (madina website)
- Ara-trust a safety benchmark
- Arabic exams
- Ara stem not available yet
- Alrage --> Manel

### Benchmark Datasets
In reforming the leaderboard, we follow two guiding principles: remove machine translated tasks, due to inherent lower quality and possible cultural bias, and add newly available high quality native or human curated benchmarks to increase the coverage of the evaluation.

From the first version of the Open Arabic LLM Leaderboard (OALL), we keep the following benchmark datasets:
- [AlGhafa benchmark](https://gitlab.com/tiiuae/alghafa)[2]: from the original benchmark released by TII, we keep only the native Arabic datasets, including the 2 Arabic tasks from [Meta's Belele](https://huggingface.co/datasets/facebook/belebele)[3] and the [Arabic EXAMS benchmarks]()[4].

We enrich the leaderboard by adding the following datasets, released in the past 9 months:
- [Native Arabic MMLU](https://huggingface.co/datasets/MBZUAI/ArabicMMLU)[5]: a native Arabic benchmark released by MBZUAI and inspired by the original English MMLU dataset; consists of 40 tasks and almost 15,000 multiple-choice questions in Modern Standard Arabic (MSA), sourced from school exams. 
- Human Translated MMLU[6]: a human translation of the original English MMLU dataset containing 57 tasks, curated by MBZUAI as part of the Jais project.
- [MedinaQA](https://huggingface.co/datasets/MBZUAI/MadinahQA)[5]: released as part of MBZUAI's ArabicMMLU project, this dataset focuses on general Arabic language and grammar aspects.
- [AraTrust](https://huggingface.co/datasets/asas-ai/AraTrust)[7]: a dataset comprising of 522 human-written multiple-choice questions covering different aspects related to safety and truthfulness.

Finally, We also introduce the ALRAGE task: Arabic Language Retrieval Augmented Generation Evaluation. 
It introduces a comprehensive framework for evaluating Large Language Models' retrieval-augmented generation capabilities in Arabic. Built upon a meticulously curated dataset sourced from 40 Arabic books spanning diverse topics, from Arts & Literature to Technology & Innovation, the benchmark was created using meta-llama/Meta-Llama-3.1-70B for synthetic generation and validated by native Arabic speakers with a community sprint with argilla https://huggingface.co/spaces/OALL/alrage-sprint-progress. The dataset structure includes questions, ground-truth answers, candidate contexts retrieved through the BAAI/bge-m3 embedding model, and target candidate indices, all designed to authentically simulate real-world RAG scenarios in Arabic.

The innovative aspect of ALRAGE lies in its evaluation methodology, which implements a LLM-as-judge metric within the lighteval framework. Using Qwen2.5-72B-Instruct as the judge model, the system evaluates generated responses through a structured Arabic prompt that compares the model's output against gold answers. The evaluation employs a nuanced 0-10 scoring rubric that assesses answer accuracy, relevance, and quality, with scores normalized to a 0-1 range for standardization. This technical implementation, manifested through a custom JudgeMetricWrapper class, provides a rigorous, reproducible method for evaluating Arabic language generation while maintaining sensitivity to Arabic linguistic nuances, effectively addressing the critical need for sophisticated evaluation metrics in Arabic NLP

## Results from V1 and V2 --> Rux + Basma
- Some analysis on the two leaderboards
[to be continued]

## Acknowledgements

The authors thank MBZUAI ...

## Citations
```
@misc{OALL2,
  author = {...},
  title = {The Open Arabic LLM Leaderboard 2},
  year = {2025},
  publisher = {OALL},
  howpublished = "\url{https://huggingface.co/spaces/OALL/Open-Arabic-LLM-Leaderboard-2}"
}
```
## References
[1] [Open Arabic LLM Leaderboard](https://huggingface.co/spaces/OALL/Open-Arabic-LLM-Leaderboard)(Elfilali et al., 2024)
[2] [AlGhafa Evaluation Benchmark for Arabic Language Models](https://aclanthology.org/2023.arabicnlp-1.21/) (Almazrouei et al., ArabicNLP 2023)
[3] [The Belebele Benchmark: a Parallel Reading Comprehension Dataset in 122 Language Variants](https://aclanthology.org/2024.acl-long.44/)(Bandarkar et al., ACL, 2023)
[4] [{EXAMS}: A Multi-subject High School Examinations Dataset for Cross-lingual and Multilingual Question Answering"](https://aclanthology.org/2020.emnlp-main.438/)(Hardalov et al., EMNLP, 2023)
[5] [ArabicMMLU: Assessing Massive Multitask Language Understanding in Arabic](https://aclanthology.org/2024.findings-acl.334/)(Koto et al., ACL, 2024)
[6] [Jais and jais-chat: Arabic-centric foundation and instruction-tuned open generative large language models.] (https://arxiv.org/abs/2308.16149)(Sengupta et al., 2023).
[7] [AraTrust: An Evaluation of Trustworthiness for LLMs in Arabic](https://arxiv.org/abs/2403.09017)(Alghamdi et al., 2024)
[8] [LightEval: A lightweight framework for LLM evaluation](https://github.com/huggingface/lighteval)(Fourrier et al., 2023)
 
```
@misc{OALL,
  author = {Elfilali, Ali and Alobeidli, Hamza and Fourrier, Clémentine and Boussaha, Basma El Amel and Cojocaru, Ruxandra and Habib, Nathan and Hacid, Hakim},
  title = {Open Arabic LLM Leaderboard},
  year = {2024},
  publisher = {OALL},
  howpublished = "\url{https://huggingface.co/spaces/OALL/Open-Arabic-LLM-Leaderboard}"
}

[1]\cite{almazrouei-etal-2023-alghafa}
@inproceedings{almazrouei-etal-2023-alghafa,
    title = "{A}l{G}hafa Evaluation Benchmark for {A}rabic Language Models",
    author = "Almazrouei, Ebtesam  and
      Cojocaru, Ruxandra  and
      Baldo, Michele  and
      Malartic, Quentin  and
      Alobeidli, Hamza  and
      Mazzotta, Daniele  and
      Penedo, Guilherme  and
      Campesan, Giulia  and
      Farooq, Mugariya  and
      Alhammadi, Maitha  and
      Launay, Julien  and
      Noune, Badreddine",
    editor = "Sawaf, Hassan  and
      El-Beltagy, Samhaa  and
      Zaghouani, Wajdi  and
      Magdy, Walid  and
      Abdelali, Ahmed  and
      Tomeh, Nadi  and
      Abu Farha, Ibrahim  and
      Habash, Nizar  and
      Khalifa, Salam  and
      Keleg, Amr  and
      Haddad, Hatem  and
      Zitouni, Imed  and
      Mrini, Khalil  and
      Almatham, Rawan",
    booktitle = "Proceedings of ArabicNLP 2023",
    month = dec,
    year = "2023",
    address = "Singapore (Hybrid)",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.arabicnlp-1.21",
    doi = "10.18653/v1/2023.arabicnlp-1.21",
    pages = "244--275",
    abstract = "Recent advances in the space of Arabic large language models have opened up a wealth of potential practical applications. From optimal training strategies, large scale data acquisition and continuously increasing NLP resources, the Arabic LLM landscape has improved in a very short span of time, despite being plagued by training data scarcity and limited evaluation resources compared to English. In line with contributing towards this ever-growing field, we introduce AlGhafa, a new multiple-choice evaluation benchmark for Arabic LLMs. For showcasing purposes, we train a new suite of models, including a 14 billion parameter model, the largest monolingual Arabic decoder-only model to date. We use a collection of publicly available datasets, as well as a newly introduced HandMade dataset consisting of 8 billion tokens. Finally, we explore the quantitative and qualitative toxicity of several Arabic models, comparing our models to existing public Arabic LLMs.",
}

@inproceedings{bandarkar-etal-2024-belebele,
    title = "The Belebele Benchmark: a Parallel Reading Comprehension Dataset in 122 Language Variants",
    author = "Bandarkar, Lucas  and
      Liang, Davis  and
      Muller, Benjamin  and
      Artetxe, Mikel  and
      Shukla, Satya Narayan  and
      Husa, Donald  and
      Goyal, Naman  and
      Krishnan, Abhinandan  and
      Zettlemoyer, Luke  and
      Khabsa, Madian",
    editor = "Ku, Lun-Wei  and
      Martins, Andre  and
      Srikumar, Vivek",
    booktitle = "Proceedings of the 62nd Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)",
    month = aug,
    year = "2024",
    address = "Bangkok, Thailand",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.acl-long.44/",
    doi = "10.18653/v1/2024.acl-long.44",
    pages = "749--775",
    abstract = "We present Belebele, a multiple-choice machine reading comprehension (MRC) dataset spanning 122 language variants. Significantly expanding the language coverage of natural language understanding (NLU) benchmarks, this dataset enables the evaluation of text models in high-, medium-, and low-resource languages. Each question is based on a short passage from the FLORES-200 dataset and has four multiple-choice answers. The questions were carefully curated to discriminate between models with different levels of general language comprehension. The English dataset on its own proves difficult enough to challenge state-of-the-art language models. Being fully parallel, this dataset enables direct comparison of model performance across all languages. We use this dataset to evaluate the capabilities of multilingual masked language models (MLMs) and large language models (LLMs). We present extensive results and findings, notably that despite significant cross-lingual transfer in English-centric LLMs, much smaller MLMs pretrained on balanced multilingual data still understand far more languages. Overall, Belebele opens up new avenues for evaluating and analyzing the multilingual capabilities of NLP systems."
}

@inproceedings{hardalov-etal-2020-exams,
    title = "{EXAMS}: A Multi-subject High School Examinations Dataset for Cross-lingual and Multilingual Question Answering",
    author = "Hardalov, Momchil  and
      Mihaylov, Todor  and
      Zlatkova, Dimitrina  and
      Dinkov, Yoan  and
      Koychev, Ivan  and
      Nakov, Preslav",
    editor = "Webber, Bonnie  and
      Cohn, Trevor  and
      He, Yulan  and
      Liu, Yang",
    booktitle = "Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP)",
    month = nov,
    year = "2020",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2020.emnlp-main.438/",
    doi = "10.18653/v1/2020.emnlp-main.438",
    pages = "5427--5444",
    abstract = "We propose EXAMS {--} a new benchmark dataset for cross-lingual and multilingual question answering for high school examinations. We collected more than 24,000 high-quality high school exam questions in 16 languages, covering 8 language families and 24 school subjects from Natural Sciences and Social Sciences, among others.EXAMS offers unique fine-grained evaluation framework across multiple languages and subjects, which allows precise analysis and comparison of the proposed models. We perform various experiments with existing top-performing multilingual pre-trained models and show that EXAMS offers multiple challenges that require multilingual knowledge and reasoning in multiple domains. We hope that EXAMS will enable researchers to explore challenging reasoning and knowledge transfer methods and pre-trained models for school question answering in various languages which was not possible by now. The data, code, pre-trained models, and evaluation are available at \url{http://github.com/mhardalov/exams-qa}."
}

@inproceedings{koto-etal-2024-arabicmmlu,
    title = "{A}rabic{MMLU}: Assessing Massive Multitask Language Understanding in {A}rabic",
    author = "Koto, Fajri  and
      Li, Haonan  and
      Shatnawi, Sara  and
      Doughman, Jad  and
      Sadallah, Abdelrahman  and
      Alraeesi, Aisha  and
      Almubarak, Khalid  and
      Alyafeai, Zaid  and
      Sengupta, Neha  and
      Shehata, Shady  and
      Habash, Nizar  and
      Nakov, Preslav  and
      Baldwin, Timothy",
    editor = "Ku, Lun-Wei  and
      Martins, Andre  and
      Srikumar, Vivek",
    booktitle = "Findings of the Association for Computational Linguistics: ACL 2024",
    month = aug,
    year = "2024",
    address = "Bangkok, Thailand",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.findings-acl.334/",
    doi = "10.18653/v1/2024.findings-acl.334",
    pages = "5622--5640",
    abstract = "The focus of language model evaluation has transitioned towards reasoning and knowledge-intensive tasks, driven by advancements in pretraining large models. While state-of-the-art models are partially trained on large Arabic texts, evaluating their performance in Arabic remains challenging due to the limited availability of relevant datasets. To bridge this gap, we present ArabicMMLU, the first multi-task language understanding benchmark for the Arabic language, sourced from school exams across diverse educational levels in different countries spanning North Africa, the Levant, and the Gulf regions. Our data comprises 40 tasks and 14,575 multiple-choice questions in Modern Standard Arabic (MSA) and is carefully constructed by collaborating with native speakers in the region. Our comprehensive evaluations of 35 models reveal substantial room for improvement, particularly among the best open-source models. Notably, BLOOMZ, mT0, LLama2, and Falcon struggle to achieve a score of 50{\%}, while even the top-performing Arabic-centric model only achieves a score of 62.3{\%}."
}

@misc{sengupta2023jaisjaischatarabiccentricfoundation,
      title={Jais and Jais-chat: Arabic-Centric Foundation and Instruction-Tuned Open Generative Large Language Models}, 
      author={Neha Sengupta and Sunil Kumar Sahu and Bokang Jia and Satheesh Katipomu and Haonan Li and Fajri Koto and William Marshall and Gurpreet Gosal and Cynthia Liu and Zhiming Chen and Osama Mohammed Afzal and Samta Kamboj and Onkar Pandit and Rahul Pal and Lalit Pradhan and Zain Muhammad Mujahid and Massa Baali and Xudong Han and Sondos Mahmoud Bsharat and Alham Fikri Aji and Zhiqiang Shen and Zhengzhong Liu and Natalia Vassilieva and Joel Hestness and Andy Hock and Andrew Feldman and Jonathan Lee and Andrew Jackson and Hector Xuguang Ren and Preslav Nakov and Timothy Baldwin and Eric Xing},
      year={2023},
      eprint={2308.16149},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2308.16149}, 
}

@misc{alghamdi2024aratrustevaluationtrustworthinessllms,
      title={AraTrust: An Evaluation of Trustworthiness for LLMs in Arabic}, 
      author={Emad A. Alghamdi and Reem I. Masoud and Deema Alnuhait and Afnan Y. Alomairi and Ahmed Ashraf and Mohamed Zaytoon},
      year={2024},
      eprint={2403.09017},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2403.09017}, 
}

@misc{lighteval,
  author = {Fourrier, Clémentine and Habib, Nathan and Wolf, Thomas and Tunstall, Lewis},
  title = {LightEval: A lightweight framework for LLM evaluation},
  year = {2023},
  version = {0.3.0},
  url = {https://github.com/huggingface/lighteval}
}
```
