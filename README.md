# 지식 증류 가이드

지식 증류(Knowledge Distillation)는 큰 모델의 판단 방식을 작은 모델이 배우도록 만드는 학습 방법입니다. 핵심은 정답 한 개만 전달하는 것이 아니라, teacher가 본 문제의 구조와 클래스 간 유사성까지 student에게 함께 전달하는 데 있습니다. 그래서 student는 더 작고 빠르면서도 teacher의 판단 패턴 일부를 이어받을 수 있습니다.

이 아이디어는 처음에는 모델 압축 문제에서 출발했지만, 지금은 CNN, Transformer, LLM까지 이어지는 넓은 학습 전략으로 확장되었습니다. 즉 지식 증류는 단순한 경량화 기법이 아니라, 작은 모델을 더 똑똑하게 학습시키는 방법으로 이해하는 편이 맞습니다.

```mermaid
flowchart LR
    A[큰 모델 teacher] --> B[부드러운 정답과 판단 패턴]
    B --> C[작은 모델 student]
    C --> D[빠른 추론과 낮은 비용]
```

이 그림의 요점은 student가 teacher의 가중치를 복사하는 것이 아니라, teacher의 판단 습관을 배우는 데 있습니다. 그래서 지식 증류는 모델 압축이면서 동시에 학습 설계 문제입니다.

## 이 저장소에서 다루는 내용
- teacher-student 구조와 soft target의 의미
- dark knowledge와 temperature가 중요한 이유
- 출력, 특징, attention, 관계처럼 무엇을 전달할 수 있는지
- offline, online, self distillation이 어떻게 다른지
- 모바일, 서버, NLP, LLM에서 왜 지식 증류가 중요한지
- 대표 논문이 각각 어떤 질문에 답했는지

## 읽기 순서
1. [지식 증류란 무엇인가](docs/01-knowledge-distillation-is.md)
2. [왜 잘 작동하는가](docs/02-why-it-works.md)
3. [무엇을 전달하는가](docs/03-what-gets-transferred.md)
4. [어떻게 학습하는가](docs/04-how-training-works.md)
5. [실제로 어디에 쓰이는가](docs/05-real-world-use-cases.md)
6. [LLM 시대의 지식 증류](docs/06-llm-distillation.md)
7. [한계와 오해, FAQ](docs/07-limitations-misconceptions-faq.md)
8. [참고 자료](docs/references.md)

## 핵심 흐름
- Hinton 2015는 teacher의 soft target을 student가 따라 배우는 고전적 구조를 제시했습니다.
- FitNets와 Attention Transfer는 최종 출력뿐 아니라 중간 특징과 attention도 전달할 수 있음을 보여 주었습니다.
- Deep Mutual Learning, Born Again Networks, Teacher Assistant, Self Distillation은 지식 증류가 한 가지 고정된 형태가 아니라는 점을 드러냈습니다.
- DistilBERT, TinyBERT, MiniLM은 Transformer와 NLP 환경에서 지식 증류가 실전 압축 전략이 될 수 있음을 보여 준 대표 사례입니다.
- 최근에는 이 흐름이 LLM distillation으로 확장되어, 더 작은 언어 모델을 배포 가능하게 만드는 핵심 전략으로 이어지고 있습니다.
