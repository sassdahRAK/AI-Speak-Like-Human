# AI-Speak-Like-Human
This project for research methodology course and the future plan for Veaja. It is not a AI model but it the future. The purpose of this repo for research paper.

# Understand File Structure
```
.
├── Assets                     # Images, global fonts, and icons  
├── Course Requirements        # for teacher guideline & file instruction
├── LICENSE 
├── README.md                  # The global note to describe our method use and system architecture 
├── Referrences & Appendix     # for more note about our research link to src
│   ├── Note.md                # to write down and some explain
│   ├── PersonalNote.txt       # take some note for your self if you don't remember everything
│   └── src                    # that is the assets of our referrence. it can be img to preview in Note.md 
├── Report Docx                # that is our work space. to write report to teacher.
│   └── ResearchPaper.md
└── Research Paper To Review   # pick around 10 to 20 paper to review. 
```  

# Describe our research design

## Method
This is a **review-based (literature comparison) study**, not an experiment with our own model or live data collection.
- **Approach**: Qualitative, document/content analysis
- **Data source**: 4 selected papers and technical sources on neural TTS, grouped into four categories — foundational architectures (Tacotron 2, FastSpeech 2, VALL-E, VALL-E 2), prosody/expressiveness techniques, naturalness-evaluation methods, and commercial system documentation (e.g. ElevenLabs)
- **Sampling**: Purposive sampling — papers chosen deliberately to cover the timeline and the different technical approaches, not randomly
- **Analysis method**: Comparative/thematic analysis — build a comparison table across papers (architecture type, how it models prosody/naturalness, how it's evaluated) and look for patterns across time
- **Ethical consideration**: No human subjects or private data involved; all sources properly cited

## Objective
- To trace how TTS architectures evolved (Tacotron 2 → FastSpeech 2 → VALL-E → VALL-E 2) and identify which architectural changes improved naturalness
- To examine the specific techniques used to model prosody and expressiveness in modern TTS systems
- To evaluate how "naturalness" is measured in current research and the limitations of those methods
- To compare academic architectures against a commercial system's claims about human-like speech

## Question
- How have neural TTS architectures evolved to produce more natural, human-like speech?
- What techniques are used to control prosody and expressiveness in synthesized speech?
- How is naturalness measured (e.g. MOS), and how reliable is that measurement?
- How does a commercial TTS system's approach compare with academic research on naturalness?

## Result
We expect to find that naturalness gains track a shift from recurrent/autoregressive models toward non-autoregressive and discrete-codec/language-model approaches, with prosody control becoming an explicit, separately modeled component rather than a side effect. We also expect MOS-based listening tests to remain the dominant evaluation standard despite known subjectivity limits, and that commercial systems and academic research are converging in claimed naturalness even though their architectures aren't always public.

# Paper to review

## Foundational TTS architecture papers (the "how each model is built" backbone of your comparison)
- Tacotron 2 (Shen et al., 2018) — describes a recurrent sequence-to-sequence network that maps character embeddings to mel-spectrograms, followed by a modified WaveNet vocoder, achieving a mean opinion score close to professionally recorded speech. https://google.github.io/tacotron/publications/tacotron2/index.html GitHub
FastSpeech 2 (Ren et al., 2020) — a non-autoregressive model that improves on FastSpeech by training directly on ground-truth targets and conditioning on pitch, energy, and duration to better handle natural speech variation. https://arxiv.org/abs/2006.04558 arXivarXiv
VALL-E (Wang et al., 2023) — a neural codec language model that treats TTS as a conditional language-modeling task over discrete speech codes, able to clone a voice from just a 3-second sample. https://arxiv.org/pdf/2301.02111 arXiv
VALL-E 2 (Chen et al., 2024) — an improved version that reaches human parity on naturalness and speaker-similarity benchmarks. https://arxiv.org/abs/2406.05370 arXiv


## Prosody and expressiveness specific
- "Towards End-to-End Prosody Transfer for Expressive Speech Synthesis with Tacotron" (Skerry-Ryan et al., 2018) — introduces a learned prosody embedding space derived from reference audio, letting synthesized speech match the intonation, stress, and timing of a reference clip. https://arxiv.org/abs/1803.09047 arXiv
"Enhancing audio quality for expressive Neural Text-to-Speech" (Amazon TTS Research, Ezzerg et al.) — examines why highly expressive voices are harder to model and proposes GAN- and VAE-based techniques to close the naturalness gap. https://arxiv.org/pdf/2108.06270 arxiv


## Survey/review papers (great backbone sources — they summarize many models at once)
- "A Survey on Neural Speech Synthesis" (Tan et al., 2021) — a comprehensive survey covering text analysis, acoustic models, vocoders, and advanced topics including expressive and adaptive TTS. https://arxiv.org/abs/2106.15561 Semantic Scholar
"Text to Speech Synthesis: A Systematic Review, Deep Learning Based Architecture and Future Research Direction" (Mridha et al., 2022). https://www.researchgate.net/publication/364280141


## Evaluation methodology (for your "how is naturalness measured" research question)
- "Investigating Content-Aware Neural TTS MOS Prediction Using Prosodic and Linguistic Features" — discusses how naturalness evaluation has shifted toward style, prosody and expressiveness, with MOS listening tests still the standard subjective benchmark. https://arxiv.org/pdf/2211.00342 arxiv


## Commercial system documentation (for your real-world comparison angle)
- ElevenLabs technology overview — useful for describing a leading commercial system's claimed approach to naturalness, pacing, and emotion. https://elevenlabs.io/voice-library/natural