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

## Current status of Arabic LLMs leaderboards --> Ali + Basma
The growing availability of LLMs supporting Arabic, both as monolingual and multilingual models, prompted the community to create dedicated Arabic language leaderboards. In May 2023, TII, A2I2, and HuggingFace launched the Open Arabic LLM Leaderboard, the first on HuggingFace to feature over 50 selective Arabic benchmarks including reading comprehension, sentiment analysis, and question answering. Shortly after, a collaboration between SDAIA and the King Salman Global Academy for Arabic Language introduced the Balsam Index, which includes approximately 1,400 datasets with 50,000 questions covering 67 tasks, such as grammar correction, paraphrasing, cause-and-effect classification, and text comprehension. Later, in December, Inception and MBZUAI unveiled the AraGen leaderboard, which introduces the 3C3H measure for evaluating model responses, uses dynamic evaluation cycles with private testing, and provides a specialized Arabic evaluation dataset to assess LLMs across various tasks and domains.

- They were dedicated to specific benchmarks
- You do the eval on your own and submit results

## Impact of the previous leaderboard --> Ahmed + Basma

In less than 7 months after its launch, the first version of the Open Arabic LLM Leaderboard quickly became a vital platform for the Arabic AI community, attracting over 40,000 unique visitors and more than 3,000 visits in the past month. The HuggingFace space received over 100 likes and 6 citations on Google Scholar. The community submitted more than 700 models, ranging from 1B to over 70B parameters. The leaderboard sparked numerous engaging discussions across social media, HuggingFace, Reddit, and more, making it the most prominent Arabic leaderboard to date.

- citations -> Rux
- plot activity per month --> Rux
- compare to other language leaderboards

## Why do we need a new leaderboard ? --> Ali
- Translated tasks are not suitable/issues
- Cultural irrelevancy in previous version
- We want Arabic related benchmarks: Arabic grammar, historical relevant,
- Cite some discussions from the community (critics of OALL)
- Justify the deletion of some benchmarks (saturation on some benchmarks, some of them are MT)
  
## What's new in this version ? --> Rux + Manel
- keep alghafa native tasks
- Arabic MMLU native 
- Arabic-MMLU-HT
- Madina QA (madina website)
- Ara-trust a safety benchmark
- Arabic exams
- Ara stem not available yet
- Alrag --> Manel

## Results from V1 and V2 --> Rux + Basma
- Some analysis on the two leaderboards
[to be continued]
