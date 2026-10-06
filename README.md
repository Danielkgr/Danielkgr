<div align="center">

# Daniel Glynn-Roe

### Lawyer and tinkerer in Melbourne

I build AI systems for legal work, and the measurement that decides whether a model can be trusted with it.

![Python](https://img.shields.io/badge/Python-57606a?style=for-the-badge&logo=python&logoColor=white) ![Claude API](https://img.shields.io/badge/Claude_API-57606a?style=for-the-badge&logo=anthropic&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-57606a?style=for-the-badge&logo=typescript&logoColor=white) ![Next.js](https://img.shields.io/badge/Next.js-57606a?style=for-the-badge&logo=nextdotjs&logoColor=white) ![React](https://img.shields.io/badge/React-57606a?style=for-the-badge&logo=react&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-57606a?style=for-the-badge&logo=fastapi&logoColor=white) ![Hugging Face Transformers](https://img.shields.io/badge/Transformers-57606a?style=for-the-badge&logo=huggingface&logoColor=white) ![pytest](https://img.shields.io/badge/pytest-57606a?style=for-the-badge&logo=pytest&logoColor=white)

</div>

<br>

> Most AI writing reports the systems that work.  In legal practice the work that matters is the distance between a model that sounds authoritative and a model that is correct.  **That gap is where the risk sits**, and it has to be measured rather than assumed.

For a law firm that comes down to three questions.  Is the model accurate enough for this work, measured on the firm's own tasks rather than on a vendor's?  Where does confidential and privileged client material go, and who can see it?  What does each answer cost?  Everything below is built to answer one of them.

<br>

## Selected work

> 🟢 published with results, 🟡 working prototype, ⚪ built but not yet measured

| Project | What it is | Where it stands |
|---|---|---|
| [**intake&#8209;agent**](https://github.com/Danielkgr/intake-agent) | A Claude agent that triages a new client enquiry.  It checks conflicts through a tool, applies the firm's intake policy, and drafts a summary and a holding reply.  The conflict check, the routing rules, and an advice check on the reply run in code, so every doubtful case goes to a person. | 🟡 Run once against the live Claude API on 30 synthetic enquiries, with every model turn, tool call, and cost in the audit trail.  It scored 30 of 30 on every field for $0.90, but an offline keyword baseline also scores 30 of 30, so the set is too easy to separate them. |
| [**auslawexam&#8209;bench**](https://github.com/Danielkgr/auslawexam-bench) | A reproducible benchmark of Australian legal reasoning for LLMs.  Its headline metric is how often a model invents a citation, which is the exposure a law firm actually carries. | 🟡 16 provisional questions, with every authority in the answer key checked against public sources.  Two real runs are committed with their raw outputs, Claude Opus 5.5 on the live API and a local open-weight model.  Their fabricated-citation rates are upper bounds until a legal review, because the checker's corpus is small. |
| [**contract&#8209;clause&#8209;classifier**](https://github.com/Danielkgr/contract-clause-classifier) | A zero-shot LLM against a fine-tuned transformer on CUAD contract clauses, compared on precision, recall, F1, cost, and latency.  It is framed as a build-or-buy decision. | 🟡 The zero-shot Claude arm has been run on the 56 CUAD test contracts, for a macro F1 of 0.818 at $3.35, asking about every clause type in one call per chunk.  The fine-tuned arm has not been run, so the comparison is still open. |
| [**legislation&#8209;monitor**](https://github.com/Danielkgr/legislation-monitor) | Change detection over Commonwealth and Victorian legislation.  It fetches each Act on request, diffs it against the last version, and has Claude or a local model write a plain-English brief of the amendment, labelled with where the brief came from. | 🟡 113 tests and CI on every push.  It has not yet been checked against the live registers. |
| [**legal&#8209;rag&#8209;evaluation**](https://github.com/Danielkgr/legal-rag-evaluation) | Hybrid retrieval over Australian statute.  Claude answers with citations to the exact sections it retrieved, and a checker flags any section reference the retrieved text does not support. | 🟡 One earlier two-Act run is committed with its provenance.  A provisional 36-question Fair Work Act set is ready to run at section level. |
| [**local&#8209;llm&#8209;inference&#8209;notes**](https://github.com/Danielkgr/local-llm-inference-notes) | Sixteen measurement investigations from one workstation, eight of them negative, with a plain-English summary of what running models locally means for client confidentiality.  The method the rest of the work leans on. | 🟢 Published, with the written method and the five tools that enforce it, tested in CI. |

<br>

## What I bring to legal engineering

| Capability | In practice | Where to look |
|---|---|---|
| **Evaluation before deployment** | Measurement that says whether a model is safe to rely on, beyond whether it sounds right.  I declare noise bands before the run, build benchmarks that reproduce, and count invented citations. | [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench), [local&#8209;llm&#8209;inference&#8209;notes](https://github.com/Danielkgr/local-llm-inference-notes) |
| **Building with Claude** | Agents with strict tool use and safety rules enforced in code, answers grounded through document citations, structured outputs, prompt caching, and cost read from every response's usage.  Refusals and truncated answers route to a person instead of failing open. | [intake&#8209;agent](https://github.com/Danielkgr/intake-agent), [legal&#8209;rag&#8209;evaluation](https://github.com/Danielkgr/legal-rag-evaluation), [legislation&#8209;monitor](https://github.com/Danielkgr/legislation-monitor) |
| **Grounded retrieval for legal text** | Retrieval over statute that keeps each section whole and pairs vector search with keyword matching, so that an answer traces to the provision behind it.  A citation that matches no known authority is counted as invented. | [legal&#8209;rag&#8209;evaluation](https://github.com/Danielkgr/legal-rag-evaluation), [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench) |
| **Provenance a regulated firm can audit** | Append-only runs, contamination canaries, audit trails of every model turn and tool call, and every score kept next to the raw output it came from. | [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench), [intake&#8209;agent](https://github.com/Danielkgr/intake-agent) |
| **Full-stack delivery** | The data pipeline and the model, then the FastAPI backend and the React and TypeScript interface a practitioner uses. | [legislation&#8209;monitor](https://github.com/Danielkgr/legislation-monitor), [contract&#8209;clause&#8209;classifier](https://github.com/Danielkgr/contract-clause-classifier), [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench) |
| **Explaining it to the people who decide** | Every README opens with what the tool is for and what it cannot do, in plain English, and says which of its numbers have been measured and which have not. | [intake&#8209;agent](https://github.com/Danielkgr/intake-agent), [local&#8209;llm&#8209;inference&#8209;notes](https://github.com/Danielkgr/local-llm-inference-notes) |

<br>

## How I work

I declare noise bands and success criteria before a run.  A band chosen after seeing the numbers is a rationalisation.  The rules are written down in [METHOD.md](https://github.com/Danielkgr/local-llm-inference-notes/blob/HEAD/METHOD.md) for the inference notes and [METHODOLOGY.md](https://github.com/Danielkgr/auslawexam-bench/blob/HEAD/paper/METHODOLOGY.md) for the benchmark.

Negative results get published.  Eight of the sixteen inference investigations end in no, and several of them overturned a claim the repository had already made.

Every benchmark, prompt, and published result is a commit, so any number in a README traces back to the code and the run that produced it.  Linters and tests run in CI on every push, with type checks where the project has them.

Fixes go upstream when they belong there.  A crash fix for GGUF tensors was [merged into molbal/ComfyUI&#8209;GGUF](https://github.com/molbal/ComfyUI-GGUF/pull/12) the night it was reported, and [note 10](https://github.com/Danielkgr/local-llm-inference-notes/blob/HEAD/notes/10-carrying-a-patch-against-upstream.md) records what carrying it locally had cost.
