# Daniel Glynn-Roe

**Melbourne · lawyer and tinkerer**

I build and evaluate AI systems for legal work: the systems that put legal content in front of a model, and the measurement that says whether the model is to be trusted with it.

> Most AI writing reports the systems that work. In legal practice the work that matters is the distance between a model that sounds authoritative and a model that is correct. That gap is where the risk sits, and it has to be measured, not assumed.

## Selected work

- **[auslawexam-bench](https://github.com/Danielkgr/auslawexam-bench)**: a reproducible benchmark of Australian legal reasoning for LLMs, whose headline metric is fabricated-citation rate, how often a model invents authority. Working prototype with 16 provisional questions.
  *The metric a law firm actually has exposure to, made measurable and repeatable.*

- **[Contract-clause-classifier](https://github.com/Danielkgr/Contract-clause-classifier)**: zero-shot LLM vs fine-tuned transformer on the CUAD contract dataset, compared side by side on precision, recall, F1, cost and latency.
  *A build-vs-buy decision document, not just a model comparison.*

- **[legislation-monitor](https://github.com/Danielkgr/legislation-monitor)**: automated change detection over Australian federal and Victorian legislation: scrapes, hashes, diffs, surfaces amendments, versioned.
  *A governed knowledge asset: legal knowledge that stays current without a manual review cycle.*

- **[legal-rag-evaluation](https://github.com/Danielkgr/legal-rag-evaluation)**: retrieval over the Fair Work Act with precision/recall evaluation; the published results block is labelled illustrative sample output, pending a full committed run.
  *The shape of a RAG evaluation for statutory work, stated plainly as to what it has and has not run.*

- **[local-llm-inference-notes](https://github.com/Danielkgr/local-llm-inference-notes)**: fifteen measurement investigations from one workstation, eight of them negative results, reported as plainly as the positive ones.
  *The measurement discipline the rest of the work leans on: pre-registered noise bands, same-sitting controls, published null results.*

## How I work

- **Pre-registered evaluation.** Noise bands and success criteria declared before the run: a band chosen after seeing the numbers is a rationalisation, not a criterion. (METHOD.md in local-llm-inference-notes; METHODOLOGY.md in auslawexam-bench.)
- **Negative results are published, not buried.** Eight of the fifteen investigations end in "no", and several overturned a claim the repository had already published.
- **Version-controlled assets.** Every benchmark, prompt and result is a commit, so any number in a README can be traced back to the code and the run that produced it.
