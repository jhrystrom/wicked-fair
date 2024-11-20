# Measuring Performance Disparity in Political Embeddings: Evidence from Danish Political Parties

🚧 **This work is currently under construction. Please star the repository to follow our progress!** 🚧

## Overview
This repository contains research on measuring resolution in text embeddings, with a case study focusing on Danish political parties' positions on mental health and climate change. Our work introduces a novel quality measure called "resolution" to evaluate how well embedding models represent different parts of the political spectrum.

## Mathematical Definition
We define resolution in two ways:

### Statement-level Resolution
For statement resolution we draw on the work of Bolukbasi et al. (2016) and Gordon et al. (2020) extended to sentences. The key idea is to investigate the difference between a negative and a positive version of a position. This is related to how Tessler et al. (2024) calculates disagreement in political delibration. 

Given embeddings of topics and their positive/negative versions, we define resolution as:

$$
Res_{statement} = \frac{\langle topic^+ - topic, topic - topic^- \rangle}{\| topic^+ - topic \| \cdot \| topic - topic^- \|}
$$

Where:
- $topic$ is an embedding of the base topic
- $topic^+$ is an embedding of a positive stance on the topic
- $topic^-$ is an embedding of a negative stance on the topic

### Topic-level Resolution
The proportion of statement pairs that are placed in different clusters, measuring how well the embedding space distinguishes between different political positions on a topic.


## Dataset
Our dataset consists of carefully constructed pairs of opposing political statements derived from Danish political party positions. The construction process involved:
1. **Scrape political statements**: We scrape articles from the parties websites on mental health and climate change. 
2. **Syntethic variations**: We use an LLM to generate synthetic variations of the statements to clustering possible.  
3. **Translate to English**: We translate to english to allow for cross-lingual comparisons.
4. **Construct opposing pairs**: Transforming each policy position into pairs of opposing statements



## Future Release
We plan to release both code and data accompanying this research once we have published our full paper. Stay tuned!

## References
Bolukbasi, T., Chang, K.-W., Zou, J. Y., Saligrama, V., & Kalai, A. T. (2016). Man is to computer programmer as woman is to homemaker? Debiasing word embeddings. Advances in Neural Information Processing Systems, 29, 4349–4357.

Gordon, J., Babaeianjelodar, M., & Matthews, J. (2020). Studying Political Bias via Word Embeddings. Companion Proceedings of the Web Conference 2020, 760–764. https://doi.org/10.1145/3366424.3383560

Tessler, M. H., Bakker, M. A., Jarrett, D., Sheahan, H., Chadwick, M. J., Koster, R., Evans, G., Campbell-Gillingham, L., Collins, T., Parkes, D. C., Botvinick, M., & Summerfield, C. (2024). AI can help humans find common ground in democratic deliberation. Science, 386(6719), eadq2852. https://doi.org/10.1126/science.adq2852



---
**Note**: This is ongoing research. Code and data will be made available upon paper publication.