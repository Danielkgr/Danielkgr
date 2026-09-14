# Daniel Glynn-Roe

**Melbourne · lawyer and tinkerer**

I build and evaluate AI systems for legal work: the systems that put legal content in front of a model, and the measurement that says whether the model is to be trusted with it.

> Most AI writing reports the systems that work. In legal practice the work that matters is the distance between a model that sounds authoritative and a model that is correct. That gap is where the risk sits, and it has to be measured, not assumed.

![Python](https://img.shields.io/badge/Python-3.10+-24598f?logo=python&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-Next.js-3178C6?logo=typescript&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-API-009688?logo=fastapi&logoColor=white) ![React](https://img.shields.io/badge/React-UI-61DAFB?logo=react&logoColor=black) ![Transformers](https://img.shields.io/badge/Transformers-HF-F7931E?logo=huggingface&logoColor=white) ![Pytest](https://img.shields.io/badge/Pytest-CI-0A4480?logo=pytest&logoColor=white)

## Selected work

- **[auslawexam-bench](https://github.com/Danielkgr/auslawexam-bench)**: a reproducible benchmark of Australian legal reasoning for LLMs, whose headline metric is fabricated-citation rate, how often a model invents authority. Working prototype with 16 provisional questions.
  *The metric a law firm actually has exposure to, made measurable and repeatable.*

- **[Contract-clause-classifier](https://github.com/Danielkgr/Contract-clause-classifier)**: zero-shot LLM vs fine-tuned transformer on the CUAD contract dataset, compared side by side on precision, recall, F1, cost and latency.
  *A build-vs-buy decision document, not just a model comparison.*

- **[legislation-monitor](https://github.com/Danielkgr/legislation-monitor)**: automated change detection over Australian federal and Victorian legislation: scrapes, hashes, diffs, surfaces amendments, versioned.
  *A governed knowledge asset: legal knowledge that stays current without a manual review cycle.*

- **[legal-rag-evaluation](https://github.com/Danielkgr/legal-rag-evaluation)**: hybrid retrieval over Australian statute with an OpenAI-compatible local backend.  One two-Act run is committed under `results/` with its provenance in `PROVENANCE.md`: the interpretable signal there is an eight-query routing probe, the auto-annotated scores are published as a caveat rather than a result, and the 10-test suite runs without torch.
  *The shape of a RAG evaluation for statutory work, stated plainly as to what it has and has not run.*

- **[local-llm-inference-notes](https://github.com/Danielkgr/local-llm-inference-notes)**: fifteen measurement investigations from one workstation, eight of them negative results, reported as plainly as the positive ones.
  *The measurement discipline the rest of the work leans on: pre-registered noise bands, same-sitting controls, published null results.*

## What I bring to Legal Engineering

- **Evaluation before deployment.** I build the measurement that says whether a model is safe to rely on, not just whether it sounds right: pre-registered noise bands, reproducible benchmarks, and fabricated-citation tracking. (auslawexam-bench, local-llm-inference-notes)
- **Grounded retrieval for legal text.** RAG over statute and case law with the precision/recall evaluation to prove it, so an answer is traceable to the authority that supports it. (legal-rag-evaluation, auslawexam-bench)
- **Provenance a regulated firm can audit.** Content-hashed items, append-only runs, contamination canaries, and version-controlled results: every number traces back to the code and the run that produced it. (auslawexam-bench)
- **Full-stack delivery.** From data pipeline and model to the FastAPI backend and the React/TypeScript interface a practitioner uses, with CI. (legislation-monitor, Contract-clause-classifier, auslawexam-bench)

## How I work

- **Pre-registered evaluation.** Noise bands and success criteria declared before the run: a band chosen after seeing the numbers is a rationalisation, not a criterion. (METHOD.md in local-llm-inference-notes; METHODOLOGY.md in auslawexam-bench.)
- **Negative results are published, not buried.** Eight of the fifteen investigations end in "no", and several overturned a claim the repository had already published.
- **Version-controlled assets.** Every benchmark, prompt and result is a commit, so any number in a README can be traced back to the code and the run that produced it.
