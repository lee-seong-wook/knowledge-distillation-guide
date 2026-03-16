# 핵심 논문 타임라인

지식 증류는 한 번에 완성된 기술이 아니다. 아래 흐름을 따라가면 이 분야가 무엇을 문제로 삼아 왔고, 어떤 방향으로 확장되었는지 한눈에 잡을 수 있다.

| 연도 | 논문 | 무엇을 바꿨는가 |
| --- | --- | --- |
| 2014 | FitNets | 최종 출력뿐 아니라 중간 표현도 student가 따라 할 수 있음을 보여 주었다. |
| 2015 | Distilling the Knowledge in a Neural Network | teacher-student와 soft target 기반 고전적 지식 증류 구조를 정리했다. |
| 2016 | Attention Transfer | 모델이 어디를 보고 판단하는지까지 전달할 수 있음을 보여 주었다. |
| 2017 | Deep Mutual Learning | 고정된 큰 teacher 없이도 여러 모델이 서로 가르치며 좋아질 수 있음을 보였다. |
| 2018 | Born Again Neural Networks | 같은 크기의 student도 teacher보다 더 좋아질 수 있음을 보여 주었다. |
| 2019 | Improved Knowledge Distillation via Teacher Assistant | teacher와 student 차이가 너무 클 때 중간 단계를 넣는 전략을 제시했다. |
| 2019 | Be Your Own Teacher | 자기 자신 안에서 지식을 재활용하는 self distillation 흐름을 대표했다. |
| 2019 | DistilBERT | Transformer 압축에서 지식 증류가 실전 모델 전략이 될 수 있음을 보여 주었다. |
| 2019 | TinyBERT | Transformer 내부 구조까지 더 정교하게 증류하는 방향을 보여 주었다. |
| 2020 | MiniLM | self-attention 자체를 핵심 증류 대상으로 삼아 효율적 압축을 보여 주었다. |
| 2020 | Knowledge Distillation: A Survey | 고전적인 KD 분류와 연구 지형을 한 번에 정리한 대표 서베이다. |
| 2023 | Categories of Response-Based, Feature-Based, and Relation-Based Knowledge Distillation | response, feature, relation 분류와 학습 scheme을 함께 정리한 분류 중심 서베이다. |
| 2024 | A Survey on Knowledge Distillation of Large Language Models | LLM distillation을 별도의 연구 축으로 체계화했다. |
| 2025 | A Comprehensive Survey on Knowledge Distillation | foundation model, diffusion, multimodal, LLM까지 포함한 최신 큰 그림을 정리했다. |

## 이 타임라인과 연결되는 문서
- [지식 증류란 무엇인가](01-knowledge-distillation-is.md)
- [무엇을 전달하는가](03-what-gets-transferred.md)
- [지식 증류의 종류 정리](types-of-knowledge-distillation.md)
- [어떻게 학습하는가](04-how-training-works.md)
- [LLM 시대의 지식 증류](06-llm-distillation.md)
