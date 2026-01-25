# 05_AI (10pt / 664 solves)

## 問題文

2026年時点でも、ChatGPTやGemini、Grok、Claudeといった様々なAIサービスが使われていたはずです。  
未来に比べて、データの汚染もさほど深刻ではないでしょう。調査において強い味方になると思います。  
あなた達は調査において、AIをどのように捉えるべきでしょうか？

- A: AIを使用してはならない。すべての情報が虚偽である可能性が高いため、不正となる。
- B: AIを使用しても構わない。ただし、出力された情報は提出前に自分で精査する。
- C: AIを使用しても構わない。AIの出力結果は高精度で間違いがないので、そのまま信じて提出を行う。

`SWIMMER{A}`、`SWIMMER{B}`、`SWIMMER{C}` のいずれかで答えてください。

As of 2026, various AI services like ChatGPT, Gemini, Grok, and Claude were in use.  
Data contamination should be less severe than in the future, so AI can be a strong ally in investigations.  
How should you regard AI in your investigation?

- A: You must not use AI. The information could all be false, so it would be cheating.
- B: You may use AI, but you must review its output yourself before submitting.
- C: You may use AI. Its output is highly accurate and error-free, so trust it as-is and submit.

Answer with one of `SWIMMER{A}`, `SWIMMER{B}`, or `SWIMMER{C}`.


## 解法

ルールには以下のような記載があります。

> あなたや AI が禁止事項に違反しない限り、ChatGPT や Gemini、Claude などの AI サービスを 調査 に利用してもかまいません（CTF 問題サーバに対するいかなる機械的なアクセスも禁止されている点には留意してください）。ただし、AI エージェントを自律的に動作させた場合に何らかの違反行為が発生した場合、あなたの責任となります。

> You may use AI services such as ChatGPT, Gemini, and Claude for research, as long as you (and the AI) do not violate the prohibitions (note that any automated access to the CTF server is prohibited).
> 
> If you operate an AI agent autonomously and it results in any prohibited activity, you are responsible.

これより、Bが正解となります。

> B: AIを使用しても構わない。ただし、出力された情報は提出前に自分で精査する。
> B: You may use AI, but you must review its output yourself before submitting.

Flag: **`SWIMMER{B}`**