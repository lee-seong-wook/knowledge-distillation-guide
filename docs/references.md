# 참고 자료

이 문서는 참고 자료를 개념 기여 기준으로 묶어 정리한다. 먼저 서베이로 큰 그림을 잡고, 그 다음 원논문을 읽으면 흐름이 자연스럽다.

## 1. 큰 그림을 잡는 서베이
- Jianping Gou 외, 2020, Knowledge Distillation: A Survey
  - 역할: 고전적인 지식 증류의 분류, 학습 방식, 응용을 정리한 대표 서베이
  - 공개 PDF: https://eprints.bbk.ac.uk/id/eprint/44038/1/KD_Survey-arxiv.pdf
- Chuanguang Yang 외, 2023, Categories of Response-Based, Feature-Based, and Relation-Based Knowledge Distillation
  - 역할: response, feature, relation 기준과 offline, online, self 같은 scheme 기준을 함께 정리한 분류 중심 서베이
  - 공개 PDF: http://arxiv.org/pdf/2306.10687
- Xiaohan Xu 외, 2024, A Survey on Knowledge Distillation of Large Language Models
  - 역할: LLM distillation을 알고리즘, 능력, 도메인 축으로 정리한 서베이
  - 관련 정리 저장소: https://github.com/Tebmer/Awesome-Knowledge-Distillation-of-LLMs
- Amir M. Mansourian 외, 2025, A Comprehensive Survey on Knowledge Distillation
  - 역할: foundation model, LLM, diffusion, multimodal까지 포함한 최신 종합 서베이
  - 프로젝트 저장소: https://github.com/IPL-Sharif/KD_Survey

## 2. 개념의 출발점
- Geoffrey E. Hinton 외, 2015, Distilling the Knowledge in a Neural Network
  - 역할: teacher-student와 soft target 기반 고전적 지식 증류의 출발점
  - 논문 페이지: https://www.semanticscholar.org/paper/0c908739fbff75f03469d13d4a1a07de3414ee19

## 3. 최종 출력 밖으로 확장된 연구
- Adriana Romero 외, 2014, FitNets: Hints for Thin Deep Nets
  - 역할: 중간 표현과 hint 기반 증류를 대표하는 논문
  - 논문 페이지: https://www.semanticscholar.org/paper/8604f376633af8b347e31d84c6150a93b11e34c2
- Sergey Zagoruyko 외, 2016, Paying More Attention to Attention: Improving the Performance of Convolutional Neural Networks via Attention Transfer
  - 역할: attention을 직접 전달하는 증류 흐름의 대표 사례
  - 논문 페이지: https://www.semanticscholar.org/paper/f7b032a4df721d4ed2bab97f6acd33d62477b7a5

## 4. 학습 방식이 다양해지는 흐름
- Ying Zhang 외, 2017, Deep Mutual Learning
  - 역할: online distillation과 상호 학습 흐름의 대표 사례
  - 논문 페이지: https://www.semanticscholar.org/paper/f06a12928307e17b1aff2b9f4a6c11791f19b6a7
- Tommaso Furlanello 외, 2018, Born Again Neural Networks
  - 역할: 같은 크기 또는 유사한 크기의 student도 teacher를 이길 수 있음을 보여 준 사례
  - 논문 페이지: https://www.semanticscholar.org/paper/2444be7584d1f5a7e2aa9f65078de09154f14ea1
- Seyed Iman Mirzadeh 외, 2019, Improved Knowledge Distillation via Teacher Assistant
  - 역할: teacher와 student 차이가 너무 클 때 중간 단계를 두는 전략 제안
  - 논문 페이지: https://www.semanticscholar.org/paper/bc6dfc6bda2d929fec91042dce1831fd07999b39
- Linfeng Zhang 외, 2019, Be Your Own Teacher: Improve the Performance of Convolutional Neural Networks via Self Distillation
  - 역할: self distillation의 대표 사례
  - 논문 페이지: https://www.semanticscholar.org/paper/a8cab29d2230924dffe89d6dda15ba42790c5ebf

## 5. Transformer와 NLP 압축의 대표 사례
- Victor Sanh 외, 2019, DistilBERT, a distilled version of BERT: smaller, faster, cheaper and lighter
  - 역할: BERT 압축의 대표 사례이자 산업 활용 관점에서 자주 인용되는 모델
  - 논문 페이지: https://www.semanticscholar.org/paper/a54b56af24bb4873ed0163b77df63b92bd018ddc
- Xiaoqi Jiao 외, 2019, TinyBERT: Distilling BERT for Natural Language Understanding
  - 역할: Transformer 내부 구조까지 더 세밀하게 증류한 대표 사례
  - 공식 논문 페이지: https://aclanthology.org/2020.findings-emnlp.372/
- Wenhui Wang 외, 2020, MiniLM: Deep Self-Attention Distillation for Task-Agnostic Compression of Pre-Trained Transformers
  - 역할: self-attention 자체를 증류 대상으로 삼아 효율적 압축을 보여 준 사례
  - 논문 페이지: https://www.semanticscholar.org/paper/c6c734e16f66fbfcefac7625cc64599e83292c1e

## 연결 문서
- [무엇을 전달하는가](03-what-gets-transferred.md)
- [지식 증류의 종류 정리](types-of-knowledge-distillation.md)
- [어떻게 학습하는가](04-how-training-works.md)
- [LLM 시대의 지식 증류](06-llm-distillation.md)
- [핵심 논문 타임라인](paper-timeline.md)
