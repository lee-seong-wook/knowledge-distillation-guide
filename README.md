# 지식 증류 가이드

지식 증류(Knowledge Distillation)는 큰 모델의 판단 방식을 작은 모델로 옮기는 학습 전략이다. 핵심은 정답을 맞히는 능력만 복사하는 것이 아니라, teacher가 문제를 어떻게 보고 무엇을 비슷하다고 느끼는지까지 student에게 전달하는 데 있다. 그래서 지식 증류는 모델 압축이면서 동시에 학습 설계 문제다.

처음에는 앙상블이나 대형 모델을 더 작은 모델로 압축하려는 목적이 강했지만, 지금은 CNN, Transformer, LLM까지 이어지는 넓은 프레임워크가 되었다. 출력 분포를 전달할 수도 있고, 중간 특징이나 attention, 샘플 간 관계를 옮길 수도 있다. 학습 방식도 offline, online, self distillation처럼 여러 갈래로 발전했다.

```mermaid
flowchart LR
    A[큰 모델 teacher] --> B[부드러운 정답과 판단 패턴]
    B --> C[작은 모델 student]
    C --> D[빠른 추론과 낮은 비용]
```

이 도식의 요점은 student가 teacher의 가중치를 베끼는 것이 아니라, teacher의 판단 기준을 배우는 데 있다. 그래서 지식 증류는 경량화 기법으로만 이해하면 부족하고, 어떤 지식을 어떤 방식으로 옮길지 설계하는 문제로 이해해야 한다.

## 개념 지도
- [지식 증류란 무엇인가](docs/01-knowledge-distillation-is.md)
  - teacher-student 구조, 앙상블 압축, 왜 이 문제가 생겼는지
- [왜 잘 작동하는가](docs/02-why-it-works.md)
  - soft target, dark knowledge, temperature, 손실 조합
- [무엇을 전달하는가](docs/03-what-gets-transferred.md)
  - 출력, 특징, attention, 관계 지식
- [지식 증류의 종류 정리](docs/types-of-knowledge-distillation.md)
  - 전달 대상, 학습 구도, teacher 구성, 적용 상황 기준의 전체 분류
- [어떻게 학습하는가](docs/04-how-training-works.md)
  - offline, online, self distillation, teacher assistant
- [실제로 어디에 쓰이는가](docs/05-real-world-use-cases.md)
  - 모바일, 서버 비용, 실시간 응답, 제품화
- [LLM 시대의 지식 증류](docs/06-llm-distillation.md)
  - white-box, black-box, response distillation, 법적 제약
- [한계와 오해, FAQ](docs/07-limitations-misconceptions-faq.md)
  - capacity gap, teacher 오류 전파, pruning과 quantization과의 관계

## 보조 문서
- [용어집](docs/glossary.md)
- [핵심 논문 타임라인](docs/paper-timeline.md)
- [참고 자료](docs/references.md)

## 핵심 질문
### 1. 지식 증류는 무엇을 해결하려고 시작됐는가
큰 모델은 정확하지만 무겁고 느리다. 작은 모델은 빠르지만 성능이 부족할 수 있다. 지식 증류는 이 둘 사이의 간극을 줄이기 위해 등장했다.

### 2. 왜 정답 하나보다 teacher의 분포가 더 도움이 되는가
teacher는 정답 외 클래스들에 대해서도 유사도 정보를 담고 있다. student는 이 정보를 통해 문제 구조를 더 부드럽게 배운다.

### 3. 꼭 최종 출력만 따라 해야 하는가
아니다. 중간 특징, attention, 샘플 간 관계처럼 더 깊은 구조도 증류 대상이 될 수 있다.

### 4. 항상 미리 학습된 큰 teacher가 필요한가
아니다. 여러 student가 동시에 서로 배우는 online distillation도 있고, 모델이 자기 자신에게서 배우는 self distillation도 있다.

### 5. LLM에서도 같은 논리가 통하는가
통한다. 다만 출력이 긴 텍스트가 되고, synthetic data와 라이선스 문제가 함께 중요해진다는 점이 다르다.

## 흐름으로 보는 대표 논문
- Hinton 2015는 teacher의 soft target을 student가 따라 배우는 고전적 틀을 정리했다.
- FitNets는 최종 출력이 아니라 중간 표현도 증류할 수 있음을 보여 주었다.
- Attention Transfer는 모델이 어디를 보고 판단하는지까지 전달할 수 있음을 보여 주었다.
- Deep Mutual Learning, Born Again Networks, Teacher Assistant, Be Your Own Teacher는 지식 증류가 하나의 고정된 알고리즘이 아니라는 점을 드러냈다.
- DistilBERT, TinyBERT, MiniLM은 Transformer 압축에서 지식 증류가 실전 전략이 될 수 있음을 보여 주었다.
- 최근에는 이 흐름이 LLM distillation으로 이어져, 더 작은 언어 모델을 배포 가능한 수준으로 끌어올리는 핵심 방법 중 하나가 되었다.
