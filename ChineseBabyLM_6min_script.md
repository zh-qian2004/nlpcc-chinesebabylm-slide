# ChineseBabyLM Shared Task: 6-Minute Slide Script

## Presentation constraints

- Language: English
- Typeface: Arial throughout
- Format: 16:9 widescreen
- Occasion: NLPCC 2026 oral presentation by the paper authors / task organizers
- Voice: concise academic reporting in the first-person plural
- Visual style: plain white background, no background template, no decorative frame
- Accent colors: dark red and warm gold, used sparingly for numbers and emphasis
- Total: 7 slides, approximately 6 minutes
- Citations: keep source details in the speaker notes of the final PowerPoint

---

## Slide 1: The First ChineseBabyLM Challenge

**Target time: 0:20**

### On-slide text

**The First ChineseBabyLM Challenge**

Training Data-efficient and Cognitively Plausible Language Models for Chinese

Siyuan Song, Zhiheng Qian, Yunhao Zhang, Linyang He, et al.

NLPCC 2026

### Visual direction

Use a conventional academic title slide. Keep the paper title, abbreviated author list, and venue left aligned. Use an oversized “102M” as a pale red typographic accent on the right. In the final deck, underline or color the presenter's name.

### Speaker notes

In this work, we present the first ChineseBabyLM Challenge. We ask how much Chinese linguistic competence a model can acquire from a developmentally motivated data budget. We turn this question into a shared task with controlled training data and evaluation across language understanding, Chinese character knowledge, and cognitive alignment.

### Sources

- Song et al. (2026), abstract and Section 1
- [ChineseBabyLM official website](https://chinese-babylm.github.io/)

---

## Slide 2: Motivation and contributions

**Target time: 0:45**

### On-slide text

**Research question**

How well can models learn Chinese from **no more than 102M words**?

**Three contributions**

- A standardized Chinese pretraining corpus and open evaluation pipeline
- Fourteen tasks covering NLU, Hanzi knowledge, and cognitive alignment
- Results and system analysis from 18 teams and 28 submitted models

### Visual direction

Place the research question in large type across the upper half. Present the three contributions as three short horizontal statements below it, separated by thin rules rather than boxes.

### Speaker notes

BabyLM studies sample-efficient pretraining under data budgets inspired by human language acquisition, but previous shared tasks focused mainly on English. Chinese adds language-specific questions about segmentation, compounding, and the structural and phonological information carried by characters. Our contribution is a complete shared-task framework: a standardized corpus and evaluation pipeline, 14 tasks across three complementary tracks, and an empirical comparison of 28 submitted models from 18 teams. This setup shifts attention from access to massive corpora toward choices in data, representation, and learning objective.

### Sources

- Song et al. (2026), Sections 1 and 3
- [ChineseBabyLM overview](https://chinese-babylm.github.io/#overview)

---

## Slide 3: Training protocol

**Target time: 0:50**

### On-slide text

**Data constraint**

- Official 102M-word corpus derived from BabyBabelLM
- Naturalistic sources: speech, children’s books, educational text, subtitles, and child-oriented reference text
- A self-compiled corpus was allowed under the same word budget

**Training rules**

- Any tokenizer or architecture
- Any number of training epochs
- No pretrained checkpoints or distillation from existing large models

### Visual direction

Show a simple left-to-right flow: corpus sources, the 102M-word constraint, and training from random initialization. Add architecture examples as small text labels. Use thin rules, not filled panels.

### Speaker notes

We provided a 102-million-word corpus derived from the Chinese portion of BabyBabelLM. It combines child-available and child-directed speech with books, educational material, subtitles, and child-oriented reference text. Teams could instead compile their own corpus under the same limit, measured with a fixed Jieba word-counting procedure. We placed no restriction on the tokenizer, architecture, or number of epochs. However, every model had to start from random initialization. Pretrained checkpoints and distillation from existing large models were prohibited. The protocol therefore controlled access to linguistic data while leaving the main modeling decisions open.

### Sources

- Song et al. (2026), Section 3
- [ChineseBabyLM training data](https://chinese-babylm.github.io/#data)

---

## Slide 4: Evaluation design

**Target time: 0:55**

### On-slide text

**14 tasks in three complementary tracks**

**NLU: 8 tasks**  
Grammar, semantic judgments, inference, classification, and reading comprehension

**Hanzi: 4 tasks**  
Character structure and pinyin through zero-shot minimal pairs

**Cognitive Modeling: 2 tasks**  
Word- and discourse-level alignment with human fMRI responses

**Open development tasks + hidden final tasks**

### Visual direction

Use three vertical typographic bands labeled NLU, HANZI, and COG, with “8”, “4”, and “2” as the dominant visual elements. Add an open-versus-hidden evaluation strip along the bottom.

### Speaker notes

We evaluated models on 14 tasks. The NLU track combined two zero-shot minimal-pair benchmarks with six fine-tuning tasks, covering grammar, semantic compatibility, inference, classification, coreference, and reading comprehension. The Hanzi track used four minimal-pair tasks to test character structure and pinyin, including initials, finals, and tones. Minimal-pair tasks used accuracy, while an unrecognized target or component counted as a failure in the Hanzi evaluation. The Cognitive Modeling track fitted encoding models from hidden states to human fMRI responses for isolated words and spoken stories, then used correlation-based scores. We combined open development tasks with hidden final tasks to limit direct tuning to the test set.

### Sources

- Song et al. (2026), Section 2 and Table 1
- [ChineseBabyLM evaluation tracks](https://chinese-babylm.github.io/#tracks)

---

## Slide 5: Shared-task results

**Target time: 1:05**

### On-slide text

**18 teams, 28 models, 74 result files**

| Rank | System | Architecture | Overall |
|---:|---|---|---:|
| 1 | BabyDragon-v4 | DeBERTa-v2 | **61.49** |
| 2 | KADeBERTa-v2 | DeBERTa-v2 | **57.79** |
| 3 | Pinyin-code-97M | GPT-2 | **54.90** |

**Track winners**

- NLU: BabyDeBERTa-zh, 60.99
- Cognitive Modeling: RepDuet, 33.96
- Hanzi: BabyDragon-v4, 91.56

*Overall = macro-average of the three track scores*

### Visual direction

Use a horizontal podium or ranked bar chart for the top three. Place the three track winners in a single line below it. Keep the scoring rule as a small annotation, not a separate box.

### Speaker notes

We received 28 distinct models and 74 result files from 18 teams. For the official leaderboard, we retained one system per team. Before the competition, our four 14-million-parameter baselines covered BERT, T5, Mamba, and Pythia. BERT was strongest on NLU and cognitive modeling, while Mamba led the Hanzi baseline results. Among submissions, BabyDragon ranked first overall with 61.49, followed by KADeBERTa-v2 and the TUM pinyin-code system. We computed the overall score as a macro-average of the three tracks, giving each track equal weight, and assigned zero to missing tasks. BabyDeBERTa-zh won NLU, RepDuet received the verified Cognitive Modeling award, and BabyDragon won Hanzi. Thirteen of the 18 ranked systems used BERT-family or DeBERTa-v2 encoders, although a decoder-only GPT-2 system placed third overall.

### Sources

- Song et al. (2026), Section 5 and Table 4
- [ChineseBabyLM final leaderboard](https://chinese-babylm.github.io/#results)

---

## Slide 6: Cross-system analysis

**Target time: 1:10**

### On-slide text

**Architecture distribution**

- BERT family: **13 of 18** ranked systems
- GPT-2: **5 of 18** ranked systems

**Score ranges across submitting teams**

| Track | Minimum | Maximum | Spread |
|---|---:|---:|---:|
| NLU | 43.98 | 60.99 | 17.01 |
| Cognitive Modeling | 30.38 | 34.10 | 3.72 |
| Hanzi | 1.19 | 91.56 | 90.37 |

**No single system won all three tracks**

### Visual direction

Use one narrow stacked bar for the architecture distribution and three horizontal range lines for the track spreads. Make the Hanzi range visibly much longer. Keep the exact values as small labels beside the lines.

### Speaker notes

Looking across the full leaderboard, encoder-only architectures dominated. Eleven ranked systems used BERT and two used DeBERTa-v2, compared with five GPT-2 systems. The top two systems were encoder-only, although a decoder-only system placed third, so competitive performance was not limited to one architecture. The larger finding is the difference in score dispersion. NLU covered about 17 points, Cognitive Modeling fewer than four, and Hanzi about 90. Because the overall result gives equal weight to each track, the high-variance Hanzi track strongly separated systems in the final ranking. No system won every track, which confirms that the benchmark captures distinct capabilities, but the unequal spreads also reveal differences in task discriminability.

### Sources

- Song et al. (2026), Sections 5.2 and 6.2

---

## Slide 7: Benchmark lessons and next steps

**Target time: 0:55**

### On-slide text

**Retain and strengthen**

- ZhoBLiMP, NLI, and Hanzi tasks
- Harder variants where pinyin performance approaches the ceiling

**Revise and extend**

- Revisit word fMRI, AFQMC, and CLUEWSC
- Add segmentation, morphology, discourse, and developmental measures

**Research target: one limited-data model that is competitive across all three tracks**

### Visual direction

Use two aligned text groups, “Retain and strengthen” and “Revise and extend”, separated by one vertical rule. Place the research target in larger type across the bottom.

### Speaker notes

These results suggest concrete changes for future editions. ZhoBLiMP, the NLI tasks, and the Hanzi benchmarks separated systems well and should remain, with harder variants where top scores approach the ceiling. Word-level fMRI, AFQMC, and CLUEWSC produced compressed results and should be revised or replaced. We can also expand the benchmark with Chinese word segmentation, morphology, discourse coherence, reading-time modeling, and age-of-acquisition prediction. More broadly, the comparison with English BabyLM shows why language-specific evaluation matters. Our next research target is a unified limited-data model that performs competitively across NLU, Hanzi knowledge, and cognitive alignment rather than optimizing for only one track.

### Sources

- Song et al. (2026), Sections 6.2, 6.3, and 7

---

## Timing summary

| Slide | Time |
|---|---:|
| 1. The First ChineseBabyLM Challenge | 0:20 |
| 2. Motivation and contributions | 0:45 |
| 3. Training protocol | 0:50 |
| 4. Evaluation design | 0:55 |
| 5. Shared-task results | 1:05 |
| 6. Cross-system analysis | 1:10 |
| 7. Benchmark lessons and next steps | 0:55 |
| **Total** | **6:00** |

## Source list

- Song, S., Qian, Z., Zhang, Y., et al. (2026). *The First ChineseBabyLM Challenge: training data-efficient and cognitively plausible language models for Chinese*. Workspace PDF and [arXiv:2607.10745](https://arxiv.org/abs/2607.10745).
- [ChineseBabyLM Challenge official website](https://chinese-babylm.github.io/), including the overview, data description, evaluation tracks, and final leaderboard.

