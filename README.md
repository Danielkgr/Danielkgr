<div align="center">

# Daniel Glynn-Roe

**Lawyer and AI Technical Engineer · Melbourne, Australia**

I build AI systems for legal work and test whether they are accurate enough to rely on.

Python · TypeScript · Claude API · FastAPI · React · Next.js · Hugging Face Transformers · pytest

</div>

---

## About

Law firms ask three questions before they adopt an AI tool:

1. **Accuracy.**  Is the model accurate enough for this work, measured on the firm's own tasks?
2. **Confidentiality.**  Where does confidential and privileged client material go, and who can see it?
3. **Cost.**  What does each answer cost?

Each project below answers at least one of them.  Every README states what the tool does, what it cannot do, and which of its results I have measured.

## Projects

| Project | What it does | Status |
|---|---|---|
| [**intake&#8209;agent**](https://github.com/Danielkgr/intake-agent) | Triages new client enquiries with Claude.  The agent checks conflicts through a tool, applies the firm's intake policy, and drafts a summary and a holding reply.  Code runs the conflict check, the routing rules, and an advice check on the reply, and sends every doubtful case to a person. | **Prototype.**  One run on the live Claude API scored 30 of 30 on every field across 30 synthetic enquiries, for $0.90.  An offline keyword baseline also scored 30 of 30, so the test set is too easy to separate the two.  The audit trail records every model turn, tool call, and cost. |
| [**auslawexam&#8209;bench**](https://github.com/Danielkgr/auslawexam-bench) | Benchmarks LLMs on Australian legal reasoning.  The headline metric is how often a model invents a citation. | **Prototype.**  16 provisional questions, with every authority in the answer key checked against public sources.  The repository holds two runs with their raw outputs: Claude Opus 5.5 on the live API and a local open-weight model.  The checker's corpus is small, so the fabricated-citation rates are upper bounds until a legal review. |
| [**contract&#8209;clause&#8209;classifier**](https://github.com/Danielkgr/contract-clause-classifier) | Compares a zero-shot LLM with a fine-tuned transformer on CUAD contract clauses, as a build-or-buy decision.  It reports precision, recall, F1, cost, and latency. | **Prototype.**  I measured both on the 56 CUAD test contracts.  Zero-shot Claude reached a macro F1 of 0.818 at six cents a contract.  A fine-tuned RoBERTa reached 0.736 and ran twelve times faster on a local GPU, with no contract text leaving the machine. |
| [**legislation&#8209;monitor**](https://github.com/Danielkgr/legislation-monitor) | Detects changes to Commonwealth and Victorian legislation.  It fetches each Act on request and compares it with the last version.  Claude or a local model then writes a plain-English brief of the amendment, labelled with its source. | **Prototype.**  113 tests, with CI on every push.  I have not yet checked it against the live registers. |
| [**legal&#8209;rag&#8209;evaluation**](https://github.com/Danielkgr/legal-rag-evaluation) | Runs hybrid retrieval over Australian statute.  Claude answers with citations to the exact sections it retrieved, and a checker flags any section reference the retrieved text does not support. | **Prototype.**  The repository holds one earlier run over two Acts, with its provenance.  A provisional set of 36 Fair Work Act questions is ready to run at section level. |
| [**local&#8209;llm&#8209;inference&#8209;notes**](https://github.com/Danielkgr/local-llm-inference-notes) | Records twenty investigations into the local inference system I run on two machines: a workstation with two 32 GB Radeon AI PRO R9700 cards (64 GB of VRAM) and a Ryzen AI Max+ 395 mini PC.  The workstation serves eight model configurations across four inference engines and can keep one model loaded on each card.  Every change goes through a written qualification suite with a rollback plan.  The notes report what I measured, what I rejected, and where the measurement itself was wrong.  My other projects use the method written here. | **Published.**  The notes cover the setup up to the 7 November 2026 review.  I replaced the workstation's cards on 13 November and have not yet written that up.  The largest model now runs across both cards with a 262k-token context.  A coding model on the second machine failed its full suite on 6 November, and the repository says so.  It includes the written method and five tools, all tested in CI. |

## Skills

- **Model evaluation.**  I build reproducible benchmarks, set noise bands before each run, and count invented citations.  See [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench) and [local&#8209;llm&#8209;inference&#8209;notes](https://github.com/Danielkgr/local-llm-inference-notes).
- **Building with Claude.**  I build agents with strict tool use, safety rules enforced in code, cited answers, structured outputs, and prompt caching.  I track cost from each response's usage data.  Refusals and truncated answers go to a person.  See [intake&#8209;agent](https://github.com/Danielkgr/intake-agent), [legal&#8209;rag&#8209;evaluation](https://github.com/Danielkgr/legal-rag-evaluation), and [legislation&#8209;monitor](https://github.com/Danielkgr/legislation-monitor).
- **Retrieval over legal text.**  I keep each statutory section whole and pair vector search with keyword matching, so every answer traces to the provision behind it.  See [legal&#8209;rag&#8209;evaluation](https://github.com/Danielkgr/legal-rag-evaluation).
- **Audit and provenance.**  I use append-only runs, contamination canaries, and audit trails of every model turn and tool call.  Every score sits next to the raw output it came from.  See [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench) and [intake&#8209;agent](https://github.com/Danielkgr/intake-agent).
- **Full-stack delivery.**  I build the data pipeline, the model, the backend, and the React and TypeScript interface.  See [auslawexam&#8209;bench](https://github.com/Danielkgr/auslawexam-bench) for FastAPI with React, [legislation&#8209;monitor](https://github.com/Danielkgr/legislation-monitor) for Next.js, and [contract&#8209;clause&#8209;classifier](https://github.com/Danielkgr/contract-clause-classifier) for the model pipeline.

## How I work

- **I set success criteria before I run a test.**  I write down the noise band and the pass mark first.  The rules are in [METHOD.md](https://github.com/Danielkgr/local-llm-inference-notes/blob/HEAD/METHOD.md) for the inference notes and [METHODOLOGY.md](https://github.com/Danielkgr/auslawexam-bench/blob/HEAD/paper/METHODOLOGY.md) for the benchmark.
- **I publish negative results.**  The inference notes record six rejected engine updates, a speed claim I withdrew, and a deployed model that failed its full suite.
- **I commit everything.**  Every benchmark, prompt, and result is in version control, so each number in a README traces to the code and the run that produced it.  Linters and tests run in CI on every push, with type checks where the project has them.
- **I send fixes upstream.**  The maintainer of [molbal/ComfyUI&#8209;GGUF](https://github.com/molbal/ComfyUI-GGUF/pull/12) merged my crash fix for GGUF tensors the night I reported it.  [Note 10](https://github.com/Danielkgr/local-llm-inference-notes/blob/HEAD/notes/10-carrying-a-patch-against-upstream.md) records what carrying the patch locally had cost.
