# 04. 어떻게 학습하는가

지식 증류는 항상 같은 방식으로 학습되는 것이 아니다. teacher를 언제 준비하느냐, 누가 누구를 가르치느냐, teacher와 student 사이에 중간 단계를 둘 것이냐에 따라 여러 방식으로 나뉜다. 그래서 지식 증류를 이해할 때는 무엇을 전달하는가와 함께, 어떤 학습 구도로 전달하는가를 같이 봐야 한다.

이를 학원 구조에 비유하면 훨씬 직관적이다. 이미 완성된 스타 강사가 학생을 가르치면 offline 방식에 가깝다. 친구들끼리 서로 설명하며 함께 실력이 오르면 online 방식이다. 스스로 요약 노트를 만들고 자기 자신을 다시 가르치면 self distillation에 가깝다. 그리고 너무 어려운 강사 대신 중간 수준의 조교를 거치는 방식은 teacher assistant에 해당한다.

## 핵심 설명
가장 전통적인 방식은 offline distillation이다. 먼저 큰 teacher를 충분히 학습시킨 뒤, teacher를 고정하고 student를 학습한다. 구조가 단순하고 안정적이어서 가장 널리 쓰인다.

```mermaid
flowchart TD
    A[지식 증류 학습 방식] --> B[Offline]
    A --> C[Online]
    A --> D[Self]
    B --> B1[완성된 teacher가 student를 가르침]
    C --> C1[여러 모델이 동시에 서로 가르침]
    D --> D1[같은 모델의 더 깊은 층 또는 이전 세대가 teacher 역할]
```

online distillation은 미리 완성된 teacher가 없어도 된다. 여러 모델이 동시에 학습하면서 서로의 예측을 참고해 함께 좋아진다. Deep Mutual Learning은 이 흐름의 대표 사례다. 여기서는 상호작용 자체가 학습 신호가 된다.

self distillation은 이름 그대로 모델이 자기 자신에게서 배우는 방식이다. 하나의 네트워크 안에서 더 깊은 층의 정보를 얕은 층에 전달하거나, 이전 세대 모델이 다음 세대 모델을 가르치는 식으로 구현된다. Born Again Networks와 Be Your Own Teacher는 지식 증류가 꼭 큰 teacher와 작은 student의 고정 구도만을 뜻하지 않는다는 점을 잘 보여 준다.

teacher와 student의 크기 차이도 중요하다. 상식적으로는 teacher가 클수록 좋을 것 같지만, 실제로는 teacher와 student의 간극이 너무 크면 지식이 잘 전달되지 않을 수 있다. Teacher Assistant 방식은 중간 크기의 모델을 한 단계 넣어 큰 teacher의 지식을 여러 단계로 나누어 전달한다.

```mermaid
flowchart LR
    A[큰 teacher] --> B[중간 크기 assistant]
    B --> C[작은 student]
    A -. 직접 전달보다 안정적일 수 있음 .-> C
```

이 도식은 큰 teacher에서 아주 작은 student로 곧바로 가는 것이 항상 최선이 아니라는 점을 보여 준다. 때로는 중간 다리가 있어야 student가 더 잘 배운다.

## 학습 방식 비교

| 방식 | teacher 상태 | 장점 | 약점 | 대표 예시 |
| --- | --- | --- | --- | --- |
| offline distillation | 미리 학습 완료 | 단순하고 안정적 | 강한 teacher를 미리 준비해야 함 | Hinton 2015 |
| online distillation | 동시에 학습 | teacher가 없어도 상호 학습 가능 | 학습 설계가 복잡할 수 있음 | Deep Mutual Learning |
| self distillation | 자기 자신 또는 이전 세대 사용 | 추가 teacher 없이도 가능 | 구조 설계가 중요함 | Born Again Networks, Be Your Own Teacher |
| teacher assistant | 중간 teacher 추가 | 큰 capacity gap 완화 | 단계가 늘어나고 비용이 증가 | Teacher Assistant |

실제로 어떤 방식을 고를지는 상황에 따라 다르다. 이미 강한 teacher가 있고 student를 빠르게 만들고 싶다면 offline이 좋다. 여러 모델을 함께 학습시키며 성능을 끌어올리고 싶다면 online이 유리하다. 추가 teacher 없이 자기 구조를 개선하고 싶다면 self distillation이 실용적이다. teacher와 student 차이가 너무 크다면 teacher assistant를 고려해야 한다.

## 심화 박스
Deep Mutual Learning은 사전에 고정된 거대 teacher 없이도 서로 가르치는 구조가 강력할 수 있다는 점을 보여 준 대표 연구다. Born Again Networks는 같은 크기의 student가 teacher보다 더 좋아질 수 있음을 보여 주었다. Be Your Own Teacher는 네트워크 내부 구조를 이용한 self distillation을 보여 주었고, Teacher Assistant는 너무 큰 teacher가 항상 최적은 아니라는 현실적 문제를 해결했다.

즉 지식 증류는 하나의 알고리즘 이름이 아니라, teacher와 student 사이의 지식 전달 설계를 어떻게 하느냐에 대한 넓은 프레임워크다.

## 자주 생기는 오해
- offline distillation만이 정석이라는 생각은 틀리다. online과 self 방식도 중요한 연구 축이다.
- online distillation에는 반드시 미리 학습된 큰 teacher가 필요한 것은 아니다.
- teacher가 클수록 항상 student 성능이 올라가는 것은 아니다. capacity gap이 너무 크면 오히려 전달이 어려워질 수 있다.

## 더 읽기
- [무엇을 전달하는가](03-what-gets-transferred.md)
- [LLM 시대의 지식 증류](06-llm-distillation.md)
- [용어집](glossary.md)
