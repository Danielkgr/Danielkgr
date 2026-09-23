<div align="center">

# Daniel Glynn-Roe

### Lawyer and tinkerer in Melbourne

I build AI systems for legal work, and the measurement that decides whether a model can be trusted with it.

![Python](https://img.shields.io/badge/Python-57606a?style=for-the-badge&logo=python&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-57606a?style=for-the-badge&logo=typescript&logoColor=white) ![Next.js](https://img.shields.io/badge/Next.js-57606a?style=for-the-badge&logo=nextdotjs&logoColor=white) ![React](https://img.shields.io/badge/React-57606a?style=for-the-badge&logo=react&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-57606a?style=for-the-badge&logo=fastapi&logoColor=white) ![Hugging Face Transformers](https://img.shields.io/badge/Transformers-57606a?style=for-the-badge&logo=huggingface&logoColor=white) ![pytest](https://img.shields.io/badge/pytest-57606a?style=for-the-badge&logo=pytest&logoColor=white)

</div>

<br>

> Most AI writing reports the systems that work.  In legal practice the work that matters is the distance between a model that sounds authoritative and a model that is correct.  **That gap is where the risk sits**, and it has to be measured rather than assumed.

<br>

## Selected work

> 🟢 published with results, 🟡 working prototype, ⚪ built but not yet measured

| Project | What it is | Where it stands |
|---|---|---|
| [**auslawexam&#8209;bench**](https://github.com/Danielkgr/auslawexam-bench) | A reproducible benchmark of Australian legal reasoning for LLMs.  Its headline metric is how often a model invents a citation, which is the exposure a law firm actually carries. | 🟡 16 provisional questions and 85 tests.  The whole pipeline runs offline on a deterministic mock, and each real model slot switches on with an API key. |
| [**Contract&#8209;clause&#8209;classifier**](https://github.com/Danielkgr/Contract-clause-classifier) | A zero-shot LLM against a fine-tuned transformer on CUAD contract clauses, compared on precision, recall, F1, cost, and latency.  It is framed as a build-or-buy decision. | ⚪ Runs end to end on CUAD with a test model, with 28 tests.  No comparison run has been published yet. |
| [**legislation&#8209;monitor**](https://github.com/Danielkgr/legislation-monitor) | Change detection over Commonwealth and Victorian legislation.  It fetches each Act, hashes the text, diffs it against the last version, and shows the amendment, so the law it tracks stays current without a manual review cycle. | 🟡 Runs locally against both official registers, with 22 tests. |
| [**legal&#8209;rag&#8209;evaluation**](https://github.com/Danielkgr/legal-rag-evaluation) | Hybrid retrieval over Australian statute, with a local OpenAI-compatible backend and an evaluation that says plainly what it has and has not run. | 🟡 One two-Act run is committed with its provenance.  A hand-written routing probe put the right Act first in 7 of 8 queries. |
| [**local&#8209;llm&#8209;inference&#8209;notes**](https://github.com/Danielkgr/local-llm-inference-notes) | Fifteen measurement investigations from one workstation, eight of them negative.  The method the rest of the work leans on. | 🟢 Published, with the written method and the five tools that enforce it. |

<br>

## What I bring to legal engineering

| Capability | In practice | Where to look |
|---|---|---|
| **Evaluation before deployment** | Measurement that says whether a model is safe to rely on, beyond whether it sounds right.  I declare noise bands before the run, build benchmarks that reproduce, and count invented citations. | [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench), [local&#8209;llm&#8209;inference&#8209;notes](https://github.com/Danielkgr/local-llm-inference-notes) |
| **Grounded retrieval for legal text** | Retrieval over statute and case law, with precision and recall measured, so that an answer traces to the authority behind it. | [legal&#8209;rag&#8209;evaluation](https://github.com/Danielkgr/legal-rag-evaluation), [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench) |
| **Provenance a regulated firm can audit** | Content-hashed questions, append-only runs, contamination canaries, and results kept under version control. | [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench) |
| **Full-stack delivery** | The data pipeline and the model, then the FastAPI backend and the React and TypeScript interface a practitioner uses. | [legislation&#8209;monitor](https://github.com/Danielkgr/legislation-monitor), [Contract&#8209;clause&#8209;classifier](https://github.com/Danielkgr/Contract-clause-classifier), [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench) |

<br>

## How I work

I declare noise bands and success criteria before a run.  A band chosen after seeing the numbers is a rationalisation.  The rules are written down in [METHOD.md](https://github.com/Danielkgr/local-llm-inference-notes/blob/HEAD/METHOD.md) for the inference notes and [METHODOLOGY.md](https://github.com/Danielkgr/auslawexam-bench/blob/HEAD/paper/METHODOLOGY.md) for the benchmark.

Negative results get published.  Eight of the fifteen inference investigations end in no, and several of them overturned a claim the repository had already made.

Every benchmark, prompt, and result is a commit, so any number in a README traces back to the code and the run that produced it.
