# 참고 자료

아래는 이 저장소의 핵심 참고 자료입니다. 먼저 서베이로 큰 그림을 잡고, 그 다음 대표 원논문을 읽으면 흐름이 자연스럽습니다.

## 입문자가 먼저 읽기 좋은 자료
- Jianping Gou 외, 2020, Knowledge Distillation: A Survey
  - 역할: 고전적인 지식 증류 분류를 한 번에 정리해 주는 대표 서베이
  - 공개 PDF: https://eprints.bbk.ac.uk/id/eprint/44038/1/KD_Survey-arxiv.pdf
- Xiaohan Xu 외, 2024, A Survey on Knowledge Distillation of Large Language Models
  - 역할: LLM distillation을 알고리즘, 능력, 도메인 축으로 정리한 서베이
  - 관련 정리 저장소: https://github.com/Tebmer/Awesome-Knowledge-Distillation-of-LLMs
- Amir M. Mansourian 외, 2025, A Comprehensive Survey on Knowledge Distillation
  - 역할: foundation model과 LLM, diffusion까지 포함한 최신 종합 서베이
  - 프로젝트 저장소: https://github.com/IPL-Sharif/KD_Survey

## 대표 원논문
- Geoffrey E. Hinton 외, 2015, Distilling the Knowledge in a Neural Network
  - 역할: teacher-student와 soft target 기반 고전적 지식 증류의 출발점
  - 검색 키워드: Distilling the Knowledge in a Neural Network
- Adriana Romero 외, 2014, FitNets: Hints for Thin Deep Nets
  - 역할: 중간 표현과 hint 기반 증류를 대표하는 논문
  - 검색 키워드: FitNets Hints for Thin Deep Nets
- Sergey Zagoruyko 외, 2016, Paying More Attention to Attention
  - 역할: attention을 직접 전달하는 증류 흐름의 대표 사례
  - 검색 키워드: Paying More Attention to Attention Improving the Performance of Convolutional Neural Networks via Attention Transfer
- Ying Zhang 외, 2017, Deep Mutual Learning
  - 역할: online distillation과 상호 학습 흐름의 대표 사례
  - 검색 키워드: Deep Mutual Learning
- Tommaso Furlanello 외, 2018, Born Again Neural Networks
  - 역할: 같은 크기 또는 유사한 크기의 student도 teacher를 이길 수 있음을 보여 준 사례
  - 검색 키워드: Born Again Neural Networks
- Seyed Iman Mirzadeh 외, 2019, Improved Knowledge Distillation via Teacher Assistant
  - 역할: teacher와 student의 크기 차이가 너무 클 때 중간 단계를 두는 방법 제안
  - 검색 키워드: Improved Knowledge Distillation via Teacher Assistant
- Linfeng Zhang 외, 2019, Be Your Own Teacher
  - 역할: self distillation의 대표 사례
  - 검색 키워드: Be Your Own Teacher Improve the Performance of Convolutional Neural Networks via Self Distillation

## NLP와 Transformer 압축의 대표 논문
- Victor Sanh 외, 2019, DistilBERT, a distilled version of BERT: smaller, faster, cheaper and lighter
  - 역할: BERT 압축의 대표 사례이자 산업 활용 관점에서 자주 인용되는 모델
  - 검색 키워드: DistilBERT a distilled version of BERT smaller faster cheaper and lighter
- Xiaoqi Jiao 외, 2019, TinyBERT: Distilling BERT for Natural Language Understanding
  - 역할: Transformer 내부 구조까지 더 세밀하게 증류한 대표 사례
  - 공식 논문 페이지: https://aclanthology.org/2020.findings-emnlp.372/
- Wenhui Wang 외, 2020, MiniLM: Deep Self-Attention Distillation for Task-Agnostic Compression of Pre-Trained Transformers
  - 역할: self-attention 자체를 증류 대상으로 삼아 효율적 압축을 보여 준 사례
  - 검색 키워드: MiniLM Deep Self-Attention Distillation for Task-Agnostic Compression of Pre-Trained Transformers

## 읽는 흐름
- 개념을 먼저 잡고 싶다면 Hinton 2015와 Gou 2020 survey를 먼저 읽으면 좋습니다.
- 중간 특징과 attention이 궁금하다면 FitNets와 Attention Transfer를 보면 됩니다.
- 학습 방식의 차이를 이해하고 싶다면 Deep Mutual Learning, Born Again Networks, Teacher Assistant, Be Your Own Teacher를 순서대로 보면 됩니다.
- NLP와 LLM으로 넘어가고 싶다면 DistilBERT, TinyBERT, MiniLM 다음에 2024 LLM survey를 읽는 흐름이 자연스럽습니다.
