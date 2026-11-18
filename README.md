# How many tokens each model counts for the same text

A model's price is given per million tokens. But models don't cut the same text into the same number of tokens, so two models at the same price per token don't cost the same.

This repository holds measurements of that gap: for one text, how many tokens Claude, Gemini, DeepSeek and Mistral count for each token OpenAI counts.

**How to read a figure:** `1.50` means 1.5 times as many tokens as OpenAI for the same text. OpenAI is the reference (`1.00`) because its tokenizer, o200k, is public and exact.

These figures feed the free [AI token calculator](https://finngarden.com/tools/ai-token-calculator) on finngarden.com, which applies them to your own text and gives the cost on each model.

## By kind of text

| Kind of text | Claude | Gemini | DeepSeek V4 | Mistral Small 4 | Mistral Large 4 |
|---|---|---|---|---|---|
| English prose | 1.50 | 1.05 | 1.00 | 1.02 | 1.01 |
| French, Spanish or Italian prose | 1.75 | 1.06 | 1.13 | 1.03 | 0.97 |
| German prose | 2.17 | 1.06 | 1.18 | 1.04 | 0.96 |
| Code | 1.60 | 1.15 | 1.02 | 1.06 | 1.02 |
| Data (JSON files, event logs) | 1.45 | 1.20 | 1.05 | 1.10 | 1.01 |
| Tables of figures | 1.19 | 1.20 | 1.01 | 1.43 | 1.00 |

## In thirty more languages

Claude's count runs from 1.17 times OpenAI's in Japanese to 2.60 times in Bengali.

| Language | Claude | Gemini 4 | Gemini 3.x | DeepSeek V4 | Mistral Small 4 | Mistral Large 4 |
|---|---|---|---|---|---|---|
| Arabic | 2.15 | 1.06 | 1.10 | 1.19 | 0.95 | 0.96 |
| Bengali | 2.60 | 0.87 | 0.72 | 1.23 | 1.24 | 0.93 |
| Bulgarian | 1.23 | 0.97 | 0.97 | 1.21 | 1.03 | 1.00 |
| Catalan | 1.47 | 1.07 | 1.07 | 1.12 | 1.03 | 1.04 |
| Chinese | 1.41 | 0.85 | 0.89 | 0.77 | 1.17 | 1.01 |
| Croatian | 1.56 | 0.99 | 1.01 | 1.23 | 1.06 | 1.09 |
| Czech | 1.39 | 0.95 | 0.97 | 1.09 | 1.03 | 1.12 |
| Danish | 1.60 | 1.05 | 1.05 | 1.19 | 1.12 | 1.09 |
| Dutch | 1.98 | 1.13 | 1.13 | 1.23 | 1.21 | 0.97 |
| Finnish | 1.77 | 1.07 | 1.10 | 1.23 | 1.11 | 1.14 |
| Greek | 1.85 | 1.03 | 1.04 | 1.27 | 1.06 | 1.12 |
| Hebrew | 1.80 | 1.14 | 1.22 | 1.20 | 1.15 | 0.94 |
| Hindi | 2.35 | 0.95 | 0.86 | 1.90 | 1.18 | 1.04 |
| Hungarian | 1.37 | 0.95 | 0.95 | 1.12 | 0.93 | 1.04 |
| Indonesian | 2.05 | 0.91 | 0.93 | 1.10 | 1.13 | 1.07 |
| Japanese | 1.17 | 0.65 | 0.69 | 0.85 | 0.97 | 0.98 |
| Korean | 1.84 | 0.89 | 0.97 | 1.17 | 0.92 | 0.96 |
| Norwegian | 1.64 | 1.05 | 1.05 | 1.20 | 1.11 | 1.09 |
| Persian | 2.07 | 0.95 | 0.95 | 1.19 | 0.99 | 0.91 |
| Polish | 1.56 | 0.86 | 0.91 | 1.03 | 1.02 | 1.14 |
| Portuguese | 1.79 | 1.03 | 1.03 | 1.18 | 1.09 | 0.96 |
| Romanian | 1.45 | 0.98 | 0.98 | 1.18 | 1.03 | 1.06 |
| Russian | 1.56 | 0.98 | 0.99 | 1.15 | 1.12 | 1.02 |
| Slovak | 1.42 | 0.95 | 0.98 | 1.14 | 1.03 | 1.08 |
| Swedish | 1.56 | 1.03 | 1.05 | 1.19 | 1.12 | 1.10 |
| Thai | 2.14 | 0.77 | 0.82 | 0.94 | 1.31 | 1.30 |
| Turkish | 1.82 | 0.96 | 0.98 | 1.43 | 1.11 | 0.97 |
| Ukrainian | 1.26 | 0.93 | 0.93 | 1.25 | 1.05 | 1.04 |
| Urdu | 2.41 | 1.03 | 0.92 | 1.50 | 1.13 | 0.96 |
| Vietnamese | 2.03 | 0.95 | 0.95 | 1.55 | 1.02 | 0.98 |

## Which models each column covers

| Column | Models | Counted with |
|---|---|---|
| OpenAI (the reference) | GPT-6.2 Astra, GPT-6.2 Sol, GPT-6 Astra, GPT-6.1 Sol, GPT-6 Luna | OpenAI's public tokenizer, o200k |
| Claude | Claude Fable 5.2, Fable 5.1, Opus 5.5, Sonnet 5.5, Haiku 5.5 | Anthropic's token counting endpoint |
| Gemini 4 | Gemini 4 Carbon, Hydrogen, Argon | Google's token counter |
| Gemini 3.x | Gemini 3.8 Flash, Gemini 3.5 Flash-Lite | Google's token counter |
| DeepSeek V4 | DeepSeek V4 Pro, DeepSeek V4.1 Flash | The tokenizer DeepSeek publishes |
| Mistral Small 4, Mistral Large 4 | One column each: they use different tokenizers | The tokenizers Mistral publishes |

In the first table, "Gemini" covers all five Gemini models. Grok isn't here: there is no reliable public way to count its tokens.

## How it was measured

- **By kind of text.** A fixed set of 114 texts: prose in English, French, German, Spanish and Italian, prompts, emails, chats, code in about fifteen programming languages, data files and tables of figures. Each text was counted with o200k and with each maker's own counter or published tokenizer. Claude and Gemini were last counted on 16 November 2026, the published tokenizers on 2 November 2026.
- **By language.** Four texts in each language, counted on 16 November 2026: the Universal Declaration of Human Rights in two halves, and two everyday texts (a shop's instructions to its AI assistant, a message to a colleague). A language's figure is the mean of the formal and the everyday texts. The Declaration's texts come from [simonw/udhr-markdown](https://github.com/simonw/udhr-markdown).
- **One figure for all Claude models.** Anthropic's endpoint gave exactly the same count for the five models on every one of the 114 texts.
- **The reference, checked.** OpenAI doesn't say which tokenizer its GPT-6 models use. On 18 November 2026, OpenAI's own token counter was asked about 234 texts, the 114 above and the 120 texts of the language set, for the five GPT models. On every text it gave o200k's count plus 6, the tokens that frame a message.

## Limits

- **These are averages for a kind of text.** A single text can differ. For Claude, the figures by kind were worked out on 59 of the 114 texts and checked on the other 55: the estimate was less than 3.5% off Anthropic's own count for half of them, less than 8.8% off for nine in ten, and 18.7% off at worst, on a table of figures.
- **Formal and everyday texts don't count alike.** In Polish, Claude counted 1.52 times as many tokens as OpenAI on the Declaration and 1.61 on the everyday texts. In Japanese, 1.09 and 1.24. Both figures are in `data/by-language.csv`.
- **Four texts a language is a small sample.** Read the language figures as a good first estimate, not as a law.
- **Tokenizers change.** Anthropic changed Claude's in April 2026, with Claude Opus 4.7. These figures hold for the models listed above, on the dates given.

## Files

- [`data/by-kind.csv`](data/by-kind.csv) and [`data/by-language.csv`](data/by-language.csv): the two tables.
- [`data/ratios.json`](data/ratios.json): both tables in one file, with the models and the dates.

## Reuse

The data and this text are under [CC BY 4.0](LICENSE): use them freely, with a credit and a link to [finngarden.com](https://finngarden.com/tools/ai-token-calculator).

If you measure something different, I'd like to hear about it: [finngarden.com/about](https://finngarden.com/about).
