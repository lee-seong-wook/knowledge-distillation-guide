# 용어집

## teacher
student가 따라 배울 기준이 되는 모델이다. 보통 더 크고 성능이 좋지만, 항상 거대 모델일 필요는 없다.

## student
teacher의 지식을 받아 더 낮은 비용 구조 안에서 비슷한 판단을 재현하려는 모델이다.

## hard label
정답 클래스 하나만 강하게 주어진 일반적인 정답 레이블이다.

## soft target
teacher가 각 클래스에 대해 내놓는 확률 분포다. 정답 외 클래스들에 대한 상대적 정보도 포함한다.

## dark knowledge
정답이 아닌 클래스들에 숨어 있는 유사도 정보다. soft target이 중요한 이유를 설명할 때 자주 등장한다.

## logit
softmax를 적용하기 전의 점수 값이다. 확률 분포보다 더 직접적인 teacher 신호로 사용되기도 한다.

## temperature
softmax 분포를 더 부드럽거나 날카롭게 만드는 조절 값이다. 보통 지식 증류에서는 soft target을 더 잘 드러내기 위해 사용한다.

## KD loss
student가 teacher의 분포나 표현을 따르도록 만드는 손실 항이다. 보통 정답 손실과 함께 사용한다.

## response-based distillation
teacher의 logit이나 확률 분포 같은 최종 출력을 student가 따라 하게 만드는 증류 방식이다. 고전적 KD의 출발점에 해당한다.

## feature-based distillation
teacher의 중간 표현을 student가 닮도록 만드는 증류 방식이다. FitNets가 대표 사례다.

## attention distillation
teacher가 어디에 집중하는지를 student가 따라 하게 만드는 방식이다. 보통은 feature-based 또는 구조 보존 계열의 중요한 하위 방식으로 다룬다.

## relation-based distillation
샘플들 사이의 거리, 구조, 유사도 관계를 student가 보존하도록 만드는 방식이다.

## offline distillation
미리 학습이 끝난 teacher를 고정하고 student를 학습시키는 방식이다.

## online distillation
여러 모델이 동시에 학습하며 서로의 출력을 참고하는 방식이다.

## self distillation
모델이 자기 자신이나 이전 세대 버전에게서 배우는 방식이다.

## teacher assistant
teacher와 student 사이에 중간 크기 모델을 두어 지식 전달 간극을 줄이는 방식이다.

## white-box distillation
teacher의 logit, hidden state, attention 등 내부 정보에 접근할 수 있는 환경에서 수행하는 증류다.

## black-box distillation
teacher의 내부 정보는 보지 못하고, 입력과 출력 응답만 이용해 student를 학습시키는 방식이다.

## synthetic data
teacher가 생성한 응답이나 예시로 만든 학습 데이터다. LLM distillation에서 특히 중요하다.

## latency
입력이 들어온 뒤 모델이 응답을 내놓기까지 걸리는 시간이다. 실시간 서비스에서 매우 중요하다.

## pruning
모델 안의 불필요한 연결이나 가중치를 제거해 더 가볍게 만드는 압축 기법이다.

## quantization
가중치와 활성값의 숫자 표현을 더 낮은 비트 정밀도로 바꾸어 메모리와 연산량을 줄이는 기법이다.
