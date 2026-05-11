# I Tested Every Gemma 4 Model with OpenUI — Here’s What Actually Worked

*This is a submission for the [Gemma 4 Challenge: Write About Gemma 4](https://dev.to/challenges/google-gemma-2026-05-06)*

Over the past few days, I tested multiple Gemma 4 variants with OpenUI using both local Ollama setups and hosted inference through OpenRouter.

I wanted to answer a simple question:

> Are smaller Gemma 4 models actually usable for structured UI generation workflows?

The answer was more complicated than I expected.

Some models struggled badly with OpenUI generation. Others were surprisingly capable and produced stable, structured UI layouts consistently.

In this article, I’ll walk through:

- the models I tested
- what broke
- which Gemma 4 variants worked best
- why larger hosted models dramatically improved OpenUI generation quality
- and what I learned about local AI workflows in the process

---

# Why I Tested Gemma 4 with OpenUI

OpenUI is interesting because it pushes models beyond normal chatbot interactions.

Instead of generating plain text, the model needs to:

- follow structured formats correctly
- generate coherent component trees
- maintain layout consistency
- follow UI-oriented instructions reliably

That becomes difficult very quickly for smaller models.

A simple prompt like:

```txt
Create a responsive dashboard with analytics cards and a sidebar
```

is no longer “just text generation.”

The model now has to:

- reason about layout structure
- maintain valid output formatting
- avoid malformed component hierarchies
- generate coherent UI patterns

This makes OpenUI a surprisingly good stress test for model quality.

---

# My Setup

I tested Gemma 4 models using:

- OpenUI
- Ollama
- OpenRouter
- local inference
- hosted inference APIs

## Hardware

- 16GB RAM system
- Windows setup
- Ollama running locally

## Models Tested

| Model | Type | Tested Via |
| --- | --- | --- |
| Gemma 4 E2B | Small | Ollama |
| Gemma 4 E4B | Small | Ollama |
| Gemma 4 26B | MoE | OpenRouter |
| Gemma 4 31B | Dense | OpenRouter |

For OpenUI specifically, I quickly noticed that structured UI generation was far more demanding than normal chat prompting.

---

# What Happened with Smaller Models

This was the biggest surprise during testing.

The smaller Gemma 4 variants could sometimes handle simple UI prompts, but larger or more complex layouts often broke down quickly.

Common issues included:

- malformed component structures
- incomplete layouts
- broken rendering
- hallucinated UI elements
- inconsistent instruction following

Here’s an example of the kind of failures I frequently encountered:

- incomplete dashboard sections
- broken nesting
- invalid structured output
- partially generated layouts

For simple forms or tiny components, the smaller models were usable.

But once prompts became more layout-heavy, reliability dropped significantly.

---

# Why 26B and 31B Performed Much Better

Once I switched to the larger hosted Gemma 4 models through OpenRouter, the difference became obvious immediately.

Both the 26B and 31B variants produced:

- more stable component trees
- cleaner layouts
- stronger instruction following
- fewer malformed outputs
- more coherent UI structure

The 31B model consistently gave the best results overall.

It handled:

- larger dashboard prompts
- more complex layout instructions
- nested UI structures
- longer generations

with much better consistency.

The 26B model was also surprisingly strong and felt like a good balance between performance and output quality.

---

# Model Comparison Results

| Model | Result | Notes |
| --- | --- | --- |
| E2B | Weak | Frequently broke structured layouts |
| E4B | Better but unstable | Usable for simple prompts |
| 26B | Strong | Stable OpenUI generation |
| 31B | Best overall | Most reliable structured output |

This became one of the clearest takeaways from my testing:

> Structured UI generation is significantly more demanding than standard chat interactions.

Smaller models may still work for lightweight UI tasks, but larger models handled OpenUI workflows much more reliably.

---

# Local vs Cloud Reality

One thing I appreciated during testing was how easy OpenRouter made experimentation.

Running smaller models locally through Ollama was accessible and fun to experiment with, but hosted larger models dramatically improved output quality.

That tradeoff is important.

Local inference gives:

- privacy
- offline access
- lower long-term cost

But larger hosted models currently provide a noticeably better OpenUI generation experience.

For developers working with structured UI workflows, reliability matters more than raw token generation speed.

---

# Screenshots and Results

## Smaller Model Failures

_Add screenshots here_

## 26B and 31B Outputs

_Add screenshots here_

## OpenUI Dashboard Examples

_Add screenshots here_

---

# Final Thoughts

After testing every Gemma 4 variant with OpenUI, my biggest takeaway was this:

> Smaller models are improving rapidly, but structured UI generation still benefits heavily from larger reasoning-capable models.

The larger Gemma 4 variants made OpenUI workflows feel significantly more usable and reliable.

At the same time, the fact that smaller open models can even attempt these workflows locally is already impressive.

The local AI ecosystem is evolving fast.

And honestly, OpenUI turned out to be one of the most interesting ways to evaluate how well these models handle structured generation beyond normal chatbot use cases.

---

# Resources

- [OpenUI](https://openui.com/)
- [Ollama](https://ollama.com/)
- [OpenRouter](https://openrouter.ai/)
- [Gemma 4](https://ai.google.dev/gemma)
- [Hugging Face Gemma Models](https://huggingface.co/models?search=gemma)