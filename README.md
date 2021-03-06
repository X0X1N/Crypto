# Crypto
고전 암호


## 서론 


이 주제를 선정한 이유는 암호학에 대해 애매하게 아는것 보다 기초부터 차근차근 올라가며 공부해보고싶고 어떤 원리로 암호화되는 건지 궁금해서 이 주제를 선정하였습니다. Dream Hack을 통해 공부했고, 네이버 자료를 사용했습니다.


## 본론


### 고전 암호란? 


고전 암호는 컴퓨터와 같은 고성은 연산 장치가 발명되기 전에, 비교적 간단란 기계와 손 등으로 암호화를 수행하던 암호를 말한다. 
고전 암호는 일반적으로 치환과 전치의 방법으로 설계된다. 단순한 고전 암호는 한 가지 원리만을 사용하는 치환 암호 또는 전치암호 이고, 복잡한 고전 암호는 두 원리를 모두 사용한다.




###### 전치 (Transposition) : 평문 문자들의 위치를 바꾸는 것 
###### 치환 (Substitution) : 평문의 문자를 다른 문자로 바꾸는 것 
###### 치환 암호는 단일 문자 치환암호, 다중 문자 치환 암호로 나누어 진다. 



### 단일 문자 치환 암호란?


단일 문자 치환 암호 (Monoalphabetic Substitution Cipher)는 평문의 각 문자를 약속된 다른 문자로 치환하는 암호이다. 복호화를 위해 치환의 대응 관계는 일대일 대응이다. 

##### ex) 평문의 ‘A’가 암호문의 ‘B’로 치환된다면, 평문의 다른 어떤 문자도 ‘B’로 치환되지 않는다.




### 카이사르 암호



단일 문자 치환 암호의 대표적인 예로 기원전 줄리어스 카이사르가 사용한 카이사르 암호(Caesar Cipher)이 있다.
카이사르 암호는 평문의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 치환한다. 
이를 복호화할 때는 암호문의 각 문자를 다시 원래 위치로 밀어서 평문을 구한다.
카이사르 암호는 알파벳을 밀어낸 횟수만 알면 해독할 수 있다. 

##### ex) 알파벳을 밀어낸 횟수를 키(key)라고 한다면, 알파벳은 총 26자이므로 가능한 키의 갯수는 26개 이다.




<img width="617" alt="스크린샷 2022-03-15 08 26 32" src="https://user-images.githubusercontent.com/78540248/158277023-58ba4d61-07c6-4a06-a9f9-a2af3d32f508.png">


##### 위 표는 3번 밀어내는 카이사르 암호를 도식화한 것이다.
##### 예를 들어 ‘ADD’를 암호화하면 ‘DGG’가 출력 된다.



암호학에서 가능한 모든 키의 집합을 키 공간(Key Space)이라고 하는데 이를 이용하여 위의 예시를 다시 표현하면, 카이사르 암호에서 키 공간의 크기는 26이라고 한다.
알파벳 A부터 Z를 0부터 25까지 대응 시키면 n글자씩 밀어내는 카이사르 암호를 아래와 같이 합동식으로 표현할 수 있다.



<img width="247" alt="스크린샷 2022-03-15 08 28 32" src="https://user-images.githubusercontent.com/78540248/158277211-055269e9-f10e-4d3b-b7ce-a07b99dbbce1.png">





### 춤추는 인형과 코드북 암호



앞서 살펴본 카이사르 암호는 알파벳을 밀어서 암호화하는 특성상, 키 공간의 크기가 작기 때문에 컴퓨터를 사용하면 쉽게 복호화된다. 보다 조금 더 복잡한 단일 치환 암호로는 춤추는 인형 암호가 있다. 
##### 이 암호는 사람 한 명이 글자 하나에 대응된다.




<img width="340" alt="스크린샷 2022-03-15 11 35 16" src="https://user-images.githubusercontent.com/78540248/158294530-df74066b-4657-4bca-ad8b-3a6c4b4a7bc0.png">


춤추는 인형 암호는 모든 알파벳을 서로 다른 기호와 무작위로 일대일 대응 시켜 치환하며 키 공간의 크기는 26!이다.


단일 치환 암호는 언어가 지닌 통계적 특성이 유지된다는 단점이 있다. 

통계적으로, 영어 문장에서 가장 많이 사용되는 알파벳은 e이다. 
따라서 단일 치환 암호가 적용된 어떤 암호문에서 b가 가장 많이 등장한다면, b는 e가 치환된 것이라 추측할 수 있다.





### 다중 문자 치환 암호란?

다중 문자 치환 암호는 하나의 문자가 여러 다른 문자로 바뀔 수 있다. 즉 평문의 A가 H가 될 수도, Y가 될 수도 있다는 말이다. 
다중 문자 치환 암호 (Polyalphabetic Substitution Cipher)는 단일 문자 치환 암호와 달리, 평문의 한 문자가 암호문에서 여러 종류의 문자로 치환될수 있다. 
대표적인 다중 문자 치환 암호로는 **비제네르 암호 (Vigenere Cipher)** 가 있다.





### 비제네르 암호


비제네르, 비즈네르라고도 불리는 이 암호는 프랑스 외교관이였던 블레즈드 비즈네르에 의하여 발표된 암호이다.
비즈네르 암호는 ‘비즈네르 표’가 
있는데 이 표는 원문 알파벳 아래에 26가지 사이퍼 알파벳이 나열되어있다. 사이퍼 알파벳은 한 줄 내려갈 떄마다 한 자씩 뒤로 이동하게 되며, 줄은 1칸 이동 카이사르 사이퍼 알파벳과 동일하다.


<img width="579" alt="스크린샷 2022-03-15 11 41 14" src="https://user-images.githubusercontent.com/78540248/158295176-e2a8f4fd-2ec1-4dd6-bdbf-5408f386d876.png">



##### ex) 사이퍼 알파벳 4번을 사용하면 원문 a는 e로 원문 d는 h로 대체된다.


암호문 작성시 한가지 사이퍼 알파벳만 사용하게 되면 보완성이 낮은 카이사르 알파벳과 동일하여 빈도 분석법으로 충분히 해독이 가능하게 된다.
이를 보완하기 위해 키워드(열쇠)를 이용한다. 
키워드(열쇠)는 수신자와 송신자가 아무 단어나 선택할 수 있다.

키워드를 SKY로 하고 평문 ‘Hack’을 비즈네르 암호화하는 과정은


<img width="397" alt="스크린샷 2022-03-15 11 41 56" src="https://user-images.githubusercontent.com/78540248/158295258-37f58ef3-388b-4c41-9dec-08487e4635cb.png">




먼저 위와 같이 표에서 키의 각 문자인 ’S’, ‘K’, ‘Y’행을 고른다.
그 뒤 키워드를 반복하여 키워드의 각 행에서 평문의 문자에 대응되는 문자로 평문을 치환한다.



<img width="595" alt="스크린샷 2022-03-15 11 42 15" src="https://user-images.githubusercontent.com/78540248/158295279-e8b6d599-9693-4914-abaa-31687cec5676.png">


A부터 Z를 0부터 25까지 대응시키면 비즈네르 암호를 다음의 합동식으로 표현할 수 있다.

여기서 **C**는 **암호문**, **M**은 **평문**, **K**는 **키워드**를 의미하고, **Xi**는 **X의 i번째 요소**를 나타낸다.



<img width="262" alt="스크린샷 2022-03-15 11 43 21" src="https://user-images.githubusercontent.com/78540248/158295415-68063fb8-f0cf-4eff-8334-e079b000c638.png">






### 전치 암호


전치 암호는 평문을 구성하는 문자들의 순서를 재배열하여 암호문을 만든다. 
평문을 정해진 길이의 블록들로 나누고, 규칙을 적용하여 블록 안의 문자들을 재배치 한다.
전치 암호는 대표젓인 예시로는 기원전 450년에 고대 그리스인들이 발견한 스키테일 암호가 있다. 이 암호는 나무봉을 이용한 암호로, 먼저 메세지를 교환할 두 사람이 같은 크기의 나무봉을 제작하고, 송신자는 종이 테이프를 나무 봉에 감고, 종이 테이프를 풀어내면 순서가 뒤섞여 메세지를 읽을 수 없지만, 같은 나무봉을 가진 수신자는 테이프를 다시 나무에 감아 이를 해석할 수 있다.






### 고전 암호 공격


안전하다고 여겨졌던 고전 암호들은 암호 분석 도구와 기술의 발달로 쉽게 분석되었다.
고전 암호를 공격하는 방법으로는 대표적으로 전수 키 탐색 공격 (Exhaustive Key Search Attack)과 빈도수 분석 (Frequency Analysis)이 있다.






### 전수 키 탐색 공격이란? 


전수 키 탐색 공격은 평문과 암호문을 알 때, 키 공간을 전부 탐색하며 주어진 암호문과 같은 암호문을 생성하는 키를 찾는 방법이다. 
단순한 공격 방법이지만 키 공간의 크기가 작다면 빠른 시간안에 키를 찾고, 암호를 해독할 수 있다. 단일 피환 암호인 카이사르 암호는 키 공간이 26으로 매우 작기 때문에 전수 키 탐색 공격에 취약하다.






### 빈도수 공격


단일 치환 암호는 평문의 무자와 암호문의 문자가 항상 일대일 대응을 이루기 때문에 평문의 통계적 특성이 유지된다. 추측을 바탕으로 암호문을 복구하는 것을 빈도수 분석이라고 한다. 
이 암호문이 어떤 언어로 구성되어 있어도 대상 언어의 특성을 안다면 시도해볼 수 있다.
다중 치환 암호는 이러한 통계적 특성이 사라지기 때문에, 빈도수 공격으로부터 비교적 안전하다고 알려져 있다.






오늘 사용했던 키워드를 정리하며 마무리 하도록 하겠습니다.






**치환(Substitution)**: 평문의 각 문자를 다른 문자로 치환하는 기법. 평문의 문자와 암호문의 문자가 이루는 대응 관계에 따라 단일 치환 암호, 다중 치환 암호로 구분.

**전치(Transposition)**: 평문을 구성하는 문자들의 순서를 바꾸는 기법.

**전수 키 탐색 공격(Exhaustive Key Search Attack)**: 키 공간을 전부 탐색하는 공격 방법. 가능한 키의 수가 적으면 효과적일 수 있으나, 현대 암호는 키 공간의 크기가 매우 넓으므로 이를 대상으로 사용하기 어려움.

**빈도수 분석(Frequency Analysis**: 암호문에서 단어가 등장하는 빈도를 분석하여 통계적으로 복호화하는 공격 기법. 특수한 경우에서만 사용될 수 있음.

