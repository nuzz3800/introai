# 3i4K intent classification (cleaned copy for a course project)

This repository holds one data file used in the term project of *Introduction to AI (2026 Fall), Pusan National University*.

| File | Rows | Columns |
|---|---|---|
| `3i4k_intent.csv` | 57,063 | `text` (Korean utterance), `label` (intention, 7 classes) |

## Source and license

- Original dataset: **3i4K — Intonation-aided intention identification for Korean** (FCI corpus, `data/fci.txt`)
- Repository: https://github.com/warnikchow/3i4k
- Paper: Won Ik Cho, Hyeon Seung Lee, Ji Won Yoon, Seok Min Kim, Nam Soo Kim, *Speech Intention Understanding in a Head-final Language: A Disambiguation Utilizing Intonation-dependency*, arXiv preprint, 2018.
- License: **CC BY-SA 4.0** (stated in the original repository). This cleaned copy is shared under the same license (CC BY-SA 4.0).

## Changes made to the original

1. Converted the tab-separated `label<TAB>text` file to a UTF-8 CSV with a header and replaced label numbers with names.
2. Removed 215 sentences (536 rows) that appear more than once with **different** labels.
3. Removed 3,656 exact duplicate sentences, so that the same sentence cannot end up in both the training and the test split.
4. Shuffled the row order (the original file is sorted by label). The train / validation / test split is made later by the notebook.

## Labels

| label | meaning | share |
|---|---|---|
| `statement` | 서술 (평서문) | 31.1% |
| `question` | 질문 | 29.4% |
| `command` | 명령·요청 | 21.1% |
| `fragment` | 조각 (명사, 명사구, 미완성 문장) | 9.0% |
| `intonation_dependent` | 억양에 따라 의도가 달라지는 문장 (글만으로는 판단이 어려움) | 5.3% |
| `rhetorical_question` | 수사의문문 (대답을 기대하지 않는 질문) | 2.8% |
| `rhetorical_command` | 수사명령문 (명령 형태지만 실제 명령이 아님) | 1.4% |
