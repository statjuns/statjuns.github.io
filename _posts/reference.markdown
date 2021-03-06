---
layout: post
title:  "종합 예술영역 Data Science와 딥러닝에 대한 소고(小考)"
subtitle:   "A Study on Data Science and Deep Learning, which is a fusion of diverse disciplines"
categories: memo
tags: think ai ml dl data science future 
comments: true
header-img: img/think/2019-06-25-think-future-ai-1.png
---



## 개요

> 종합 예술영역이라 일컬어질 정도로 다양한 학문이 융합된 데이터 사이언스, 딥러닝에 대해 그동안의 경험, 감(感)을 바탕으로 몇자 주절거려 봅니다.

- 목차
	- [딥러닝의 약점은 무엇일까?](#딥러닝의-약점은-무엇일까)
	- [Data Science? AI? 모두 예전에 우리가 했던 일이다.](#data-science-ai-모두-예전에-우리가-했던-일이다) 
	- [NLP가 세상 모든 데이터의 기본단위를 바꾸지 않을까?](#nlp가-세상-모든-데이터의-기본단위를-바꾸지-않을까)
	- [결국 논문이 Key이다.](#결국-논문이-key이다)
	- [Science위의 공학. 공학위의 Science](#science위의-공학-공학위의-science)
  - [개인이 생산한 데이터의 라벨링은 누가 해 줄 것인가?](#개인이-생산한-데이터의-라벨링은-누가-해-줄-것인가)
  - [세상 모든 논문들을 딥러닝이 이해할 수 있게](#세상-모든-논문들을-딥러닝이-이해할-수-있게)
  - [딥러닝은 사이언스인가? 또, 내부는 블랙박스인가?](#딥러닝은-사이언스인가-또-내부는-블랙박스인가)
  - [요약하며...](#요약하며)
  

## 딥러닝의 약점은 무엇일까?
---

딥러닝은 분명 만능이 아니다. 더불어 딥러닝이 해결할 수 있는 대다수의 데이터 사이언스 문제들은 사실 다른 ML기법으로도 충분히 해결이 가능한 경우가 많다. 비슷한 성능을 내는데 굳이 DL을 쓰지 않고 ML을 쓰는 이유는 컴퓨팅 자원의 효율성 때문이다. 

최근 기업에서 나오는 우스개 소리로 결재가 반려될 경우 "AI, 딥러닝, 빅데이터"라는 마법의 단어를 사용하면 결재를 득할 수 있다는 풍자가 나올 정도로 A.I는 분명 핵심 트렌드이다. 본 챕터에서는 이렇게 핫한 딥러닝의 약점을 찾아볼까 한다. 만능으로 일컬어지는 최신 트렌드의 기술을 폄하할 의도는 없으나 이를 비판하는 과정은 중요하다. 그 과정에서 기술을 더 객관적으로 볼 수 있는 시야를 확보할 수 있음은 물론 더 나은 기술을 위한 초석이 될 수 있기 때문이다.   

인류가 쌓아온 지식의 분야에서 특히 딥러닝이 강점을 보이는 분야는 "동영상, 이미지, 음성인식, NLP" 등의 분야일 것이다.이 분야의 공통점은 무엇일까? 대부분 비정형 데이터이면서 동시에 컴퓨터가 이해할 수 있는 형태로의 `2차 가공을 거친` 데이터들을 다루는 분야이다. 이 세상 그대로의 데이터를 컴퓨터가 이해할 수 있도록 전할 방법이 없기에 아날로그를 디지털화 하는 등 일종의 "변환" 작업을 거친다.   

그 과정에서 이 세상의 Real 데이터들은 Computing Vision, 신호처리, 푸리에 변환 등 인류가 장기간 축적해 온 지식들의 손바닥 안에서 놀 수 있는 데이터의 형태로 변환된다. Min ~ Max의 유한한 범위를 갖는 일종의 해석 가능한 범주 형태의 피처로 변환이 되고 축적된 지식으로 만든 모델의 Input값으로 최적화 되어있는 셈이다. 

연산의 시간 복잡도 문제는 컴퓨팅 파워만 충분하다면 해결 가능해졌고, 이러한 가공을 통해 피처 선정 및 추출, 모델의 선택에 있어 경우의 수를 크게 좁혀준 셈이다. 그렇다면 가공을 거치지 않은 Tabular 형태의 일반 데이터는? 데이터 사이언스가 등장했음에도 여전히 통계학이 중요한 이유이기도 하다.


## Data Science? AI? 모두 예전에 우리가 했던 일이다.
---
통계학 분야에서 종종 언급되는 말인데 필자는 부정하고 싶지않다. "딥러닝은 기존에 존재하던 Logit의 결합일 뿐인데 이를 최신 기술의 등장이라 말할 수 있는가? 마케팅아닌가?"라고 폄하하는 분도 있다. 

Tabular 기반의 데이터에서 - 2차 가공을 거치지 않은 세상의 진정한 의미가 담긴 데이터 - 가치있는 Insight를 추출하거나 미래를 예측하기 위해서는 모델링과 그 모델이 이해할 수 있는 형태로의 데이터 전처리, 그리고 모델링을 위한 수리통계학을 기반으로 한 과학이 필수임은 부인할 수 없다. 

그런 측면에서 딥러닝은 이미 전처리 및 관련 분야의 과학적 연구가 반영된 컴퓨터 비전, 영상, 음성 등의 데이터 셋을 다루고 과학적 지식이 없는 모델링을 통해 해석도 할 수 없는채로 AI, Data "Science"를 운운하고 있으니 시각에 따라서는 비판의 대상이 될 수 있다고 본다.

세상의 모든 진리는 기초 과학들이 밝히고 컴퓨터 공학은 그들이 쌓아놓은 금자탑 위에서 단물을 쪽쪽 빨아먹는다. 어찌보면 제일 하는것도 없는 것 같은데 연구비, 정부 지원금도 가장 많이 가져가는 편이다. 그것도 모자라 이젠 감히 능력도 없는 것들이 "Science"라는 단어를 운운해? 필자는 한명의 컴퓨터 공학도로써 죄송하고 감사할 뿐이다. 

그럼에도 컴퓨터 공학의 핵심 가치는 대중화와 커뮤니케이션이 아닐까 싶다. 기초 과학의 최전선에 서있는 천재 연구자와 필자같은 평범한 대중의 지식의 격차는 어느정도일까? 길게 쳐줘야 100년도 안되는 컴퓨터 공학의 역사이지만 인류의 정보 불균형 문제를 해소하는데 가장 큰 기여를 한 것은 컴퓨터 공학이 아닐까싶다. 짧은 역사에도 불구하고 산업과 자본을 이끌어 온 저력은 바로 이러한 대중화 능력이다. 이들은 컴퓨터를 만들었고 지금도 다른 학문의 모든 데이터를 컴퓨터에 집어넣고 이해시키기 위해 변환한다. 

이제 이런 나름의 한계속에 딥러닝을 위시로 한 컴퓨터 공학이 앞으로 미래를 어떻게 헤쳐나갈지 공상과학을 써보려 한다. 이어지는 글들을 읽으시며 "개똥철학의 정도도 유분수지 더는 못봐주겠다."라고 느끼는 분들이 분명 계신다면 언제든 욕 한 번 시원하게 내뱉으시고 본 블로그를 꺼주시기 바란다. 그저 지극히 학식이 없는 이가 근거도 없이 개인적으로 바라는 미래의 방향을 생각해보고 두서없이 정리한 글이기 때문이다. 

## NLP가 세상 모든 데이터의 `기본단위`를 바꾸지 않을까?  
---
필자는 NLP가 현재의 RDB를 비롯한 세상의 대부분의 데이터(적어도 우리가 컴퓨터, 모바일을 사용하면서 생산하는 데이터 만큼은)의 저장 형태 및 기본 단위를 바꿀것이라 생각한다. 딥러닝의 자동화를 위해서 말이다.  

자연어를 NLP 기술을 활용하여 `Data-Meta` 구조의 기본 단위로 변형하여 그에 적합하게 고안된 유한한 모델을 만든 후, 변환된 데이터와 모델들은 인공지능을 위한 가교 역할 일종의 중간 Layer를 담당하게 될 것이라 멋대로 추측해보곤 한다. 

데이터는 이런 기본단위의 규칙을 갖는 반정형 형태로 축적될 것이고, 모든 자료는 Json, XML과 유사하게 Tree등의 자료구조를 활용한 Meta 정보를 쌍으로 가질 것이라 생각한다. Meta도 결국 피처로 쓰이게 될 것이고 세상의 거의 모든 자료는 서적부터 동영상에 이르기까지 이런 형태의 'Data-Meta' 단위로 재편될 것이다.  

데이터가 재편되는데는 사실 그리 오랜 시간이 걸리지 않을 것이다. 요즘 Tabular, Pad 등 글을 생산하는 플랫폼을 전부 컴퓨터 공학에서 주도하고 있기 때문이다. Tabular 데이터도 결국은 이미 고안된 유한한 모델링의 일부에 활용될 것이다.   

기생산된 데이터의 재편이 어려울지도 모른다. 하지만 빠른 시일내에 원저자 혹은 관련 연구자들이 일종의 라벨링처럼 반정형 형태로의 변환을 가능하게끔 연구해 줄 것이라 생각한다.  

어려움에 봉착할지라도 신호처리, 푸리에 변환이 활용된 것처럼 `다른 학문에 쌓인 축적된 지식을 가져와 모델링`할 것이라 예측한다. 그 중심에 NLP가 있다.  


## 결국 논문이 Key이다.   
---
그동안 인류가 쌓아온 지식을 딥러닝이 이해할 수 있는 형태로 피처 형태를 정의하고 모델을 구성하는데 얼마나 오랜 시간이 걸릴까? 그동안 컴퓨가 보여준 실행력, 스피드, 실행가능성, 실용성, 자동화의 힘이라면 구현하여 활용하는데 그리 오랜 시간이 걸리지 않을 듯 하다. 

모든 학문 분야는 `"논문"이라는 일종의 공통된 언어`를 사용한다. `논문에는 대부분 가설이 존재하고 검증을 위한 모델이 담겨`있다. 중간에 NLP가 어떤 기능을 하느냐에 따라 딥러닝이 받아들이기 아주 쉬운 구조로 되어있다는 의미이다.


## Science위의 공학. 공학위의 Science
---
공학에는 짧은 시간동안 빠른 구현 및 활용을 위한 철학을 기저로 한 고민과 무수한 시행착오를 녹인 강한 실행력을 가진 나름의 Science가 존재하기에 기초 사이언스를 쉽게 받아들이고, 결합하고, 그 과정에서 창조적인 지식이 재탄생한다. 그리고 그 지식을 누구보다도 빠르게 구현할 수 있는 학문 분야를 연구한다.(`GAN` 등이 대표적인 예라고 할 수 있다.)  

더불어 언제나 누구든 쉽게 인사이트를 착상할 수 있게 고취시킬 수 있는 환경을 가지고 있다. 때문에 세상의 자본을 쥐락펴락할 수 있는 것이 아닐까?(물론 이러한 강점이 인문학적인 측면에서, 기초 과학과 진리의 측면에서 사람이 살아가야 할 방향과 일치하느냐고 물으신다면 별개라고 답하고 싶다.)  


## 개인이 생산한 데이터의 라벨링은 누가 해 줄 것인가?   
---
마땅한 예제가 떠오르지 않아 수준 낮은 예시를 하나들까 한다. NLP없이 컴퓨터 비전 지식만 활용한다고 가정시 이 문제를 어떻게 해결할 수 있을까?

> 본인이 패드 또는 종이에 글을 쓰고 텍스트로 자동 변환하는 솔루션을 개발한다고 가정하자. 이때 [Space]는 어떻게 변환이 될까? 단어 간 띄어쓰기가 1cm일 때 스페이스를 넣을 것인가? 아니면 1mm?  

이 애매한 기준을 가지고는 과적합 발생 시 한글자 한글자마다 스페이스가 생겨 사용자로 하여금 노가다를 유발시키는 저질 변환이 이루어질 것이고, 과소 적합시에는 아에 줄 글로 주욱 붙어있어 스페이스를 찾기 어려운 지경에 빠질지도 모른다.  

그렇다면 이를 해결하기 위해 무엇이 필요할까? 당연히 데이터다. 더 정확하게 말하면 이 사람이 쓴 글의 이미지와 그에 기반한 텍스트로 변환된 라벨링이 필요하다. 피처가 단순히 이 사람의 라벨링에 기반한 스페이스 부분의 길이 정보 하나라면, 당연히 Min ~ Max의 띄어쓰기 길이가 존재할 것이고 한 글자 간 거리또한 유효한 범위가 존재할테니, 아주 간단한 경우에는 2개의 길이가 겹치는 지점에 대한 학습을 수행하여 정확도를 판별할 것이고, 더 나아간다면 특정 글자또는 단어가 들어가는 경우 스페이스의 길이가 줄어드는 특징을 잡아내어 정확도를 높일 수도 있을 것이다.  

여기서 중요한 것은 누군가는 라벨링을 해야한다는 것이다. 물론 사람의 눈은 이미 타인의 글도 상당히 정확하게 읽어내는 능력이 있으므로 라벨링 대행업체가 존재하겠지만 결국 딥러닝의 품질을 향상시키기 위해서 글쓴이의 라벨링이 직접 필요해질 수 밖에 없다. 그런데 과연 사람들이 이 귀찮은 라벨링을 순순히 참여할까? 이 문제에 대한 몫은 솔루션을 개발하는 사업가의 몫이다. 바로 개인들의 데이터에 대한 라벨을 어떻게 자연스럽게 어렵지 않게 수집할 것인지 말이다.  

이 예는 비단 NLP관련 극히 일부의 사례다. 앞으로 모바일을 통해서 더 많은 개인 데이터가 수집될 것이다. 개인화된 라벨을 마치 산소 마시듯이 편리하고 자연스럽게 축적시켜 기왕이면 개인정보 관련 본인의 동의여부 통제하에 제공될 수 있는 플랫폼을 가진 회사가 향후 딥러닝을 위시한 인공지능의 미래를 주도할 큰 축이 될 것임을 조심스럽게 예측해본다.  


## 세상 모든 논문들을 딥러닝이 이해할 수 있게  
---
위에서도 잠깐 언급한 바와 같이 학문의 축적된 기술과 이론을 피처 및 모델과 연동시키는 분야가 유망하지 않을까 조심스레 점쳐본다. 이 산업 분야는 상기의 과제 외에도 논문, 연구와 관련된 메카가 될 것이다.  

나아가 특허청과 유사한 역할로 블록체인을 활용하여 최초 지식 생산자부터의 위변조 감지도 담당할 것이고, 축적된 기술을 피처와 연관짓는 과정의 산출물로 특허 지식의 실현가능성, 적합성 등을 판단하여 특허 등록에 대한 엄밀한 예행 판단을 서비스 할 수 있게 될지도 모른다. 뉴턴과 라이프니치의 미적분 발명 논쟁도 이젠 역사속으로 사라진다.  

Review 논문의 역할과 유사한 `Reference Map + 그 위에 핵심 아이디어(해당 논문이 전달하고자 하는)`만 간략히 Graph형태로 배치될 것이고, 연구 지식이 가장 효율적인 형태로 축적된 신 인류의 지식 저장소 역할을 수행할 것이며, 사회적으로도 단일국가 탄생을 견인할 가능성도 까지 이어질지도 모르겠다고 한다면 너무 과도한 생각일까?  

학문적 깊이와 연결되기 힘든 `일반인들의 창의적인 발상`을 기존 학문이 축적한 깊이에 연결시켜 줌으로써 인류 지식의 초고속 발전에 기여하게 될지도 모른다.  


## 딥러닝은 사이언스인가? 또, 내부는 블랙박스인가?  
---
위에서 잠깐 언급했듯이 딥러닝은 Science가 아니다라는 견해가 있다. 딥러닝 관련 논문 중 `전체 매커니즘에 관해 수식으로 표현하는` 논문이 없다. 엄밀한 증명을 적용할 수식이 없고 나아가 알파고를 이길 수 있었던 규칙이 무엇이었는지, 어떤 수학적 알고리즘으로 승리한 것인건지 만든 창조자도 설명을 못한다. 그래서 블랙박스라고 표현하기도 한다.   

개인적으로는 엄밀히 블랙박스는 아니라고 생각한다. 특정 은닉층의 값을 출력해보면 weight의 값이 0.32943.., bias가 0.324, .. 등 수치적으로 분명히 확인할 수 있으니 보이지 않는다고 표현할 수는 없다. 다만, 내부에 엄청나게 많은 노드와 가중치, 그리고 노드들의 활성 여부를 `사람의 기억력으로는 전체를 바라볼 수 없어` 수식과 같은 연역적 규칙으로 표현하지 못하는 것이다. 

아직까지 사람이 가진 수식으로는 표현 못하는 거대함이 숨어있는 것이다. 사실 노드 하나하나의 활성화 과정은 Logit과 거의 유사하므로 부분만 놓고보면 수식으로 충분히 표현할 수 있음은 물론 매우 쉽다. 하지만 전체를 설명 못하는 것이다.

그렇다면 그냥 동작방식을 모른채로 살아가야 하는가? 원하는 결과만 얻으면 되는가? 그렇지 않다. 인류는 어떤 형태로든 항상 답을 구해왔으니 결국은 이뤄내지 않을까? DARPA의 XAI 프로젝트와 같이 이미 내부를 들여다보기 위한 여러 시도들이 이루어지고 있다. 특히 CNN과 같은 Vision 분야의 경우 피처 자체가 시각 데이터임에 착안하여 층별 시각화 이미지를 통해 내부를 들여다 보고 전체 로직을 설명하기 위한 필터시각화 등의 연구가 이루어지는 것으로 알고 있다. 

이와 관련하여 앞으로 개인적으로 해보고 싶은것이 있다. 전체 숲은 모를지언정 부분의 판단이 나오게 된 원인을 수식으로 변환하는 시도를 해보고 싶다. 특정 결론이 나오기까지 영향을 미친 노드들은 전체노드는 아닐 것이다. 관련 노드들 N개만 추출하여 해당 노드간의 수식을 구한다면 전체를 추적하는 것보다는 분명 쉽게 수식을 도출할 수 있을 것이라 생각한다. 

물론 ReLU함수와 같이 구해도 별 의미도 없는 수식이 등장할지도 모르겠다. 하지만 유의미한 수식이 도출될 가능성도 있다. 학습이 부족하여 ReLU 형태의 수식이 등장한 것인지도 모른다. 데이터 사이언스의 고유 업무 중의 하나가 패턴을 찾아내는 일이므로 패턴속의 규칙을 찾아내려는 시도 및 연구 결과가 모여 이 무의미한 수식들을 유의미한 수식으로 바꿔갈 것으로 기대한다. 

파격적으로 생각하면 수학에 새로운 방식의 표현이 등장할 것으로 예상한다. ~~시나리오 쓰고있다.~~ Sigma와 같이 동일 패턴의 묶음을 상징하는 기호가 많이 등장하여 천문학적인 IF의 갯수를 파격적으로 줄여주거나, `수없이 다양한 패턴이 표준 기호화`되어 그 데이터 위의 패턴을 찾으려는 시도가 진행되지 않을까 예측해본다. 너무 어려운 분야의 이야기를 얕은 지식으로 표현하였기에 허무맹랑한 이야기가 되었는지 모르겠으나 일부 역사에서 그래왔듯이 이 허무맹랑함이 인류의 과학 문명을 업그레이드시키는 씨앗이 되었으면 좋겠다.


## 요약하며  
---
> "너만의 개똥철학에 경의를 표한다."

본 포스팅의 요약이다. 어디가서 떠들면 욕먹을 것이 자명하기에 개인 블로그외에 남길곳이 없어 포스팅한 자료이니 그냥 가볍게 재미로 너그러이 봐주셨으면 한다. ~~어차피 읽는 분도 없는 것 알고 있다.~~   

개인적으로 위와 관련된 주제의 연구를 하고싶고 또는 유관 산업에서 일을 하고 싶다. 그 중에서도 '세상 모든 논문들을 딥러닝이 이해할 수 있게'라는 소제목으로 표현한 분야에 가장 관심이 많은데 네이처 논문지, 특허청 같은 유사 기관들이 이미 설립되어 있으므로 그 곳에서 변화를 주도하던가, 아니면 꿈틀대는 태동기의 회사를 찾아 들어가던가, 아니면 새로 만들던가 하고 싶지만 생업에 종사하느라 열심히 갈고 닦을 시간이 부족함에 눈물이 난다. 

대부분의 연구자 분들의 한탄이겠지만 가방 끈 짧고 더 늦게 출발한 사짜 연구자의 심정은 오죽하랴. 그저 하루종일 데이터 사이언스 분야만 할 수 있길 바랄 뿐.

아무쪼록 긴 글임에도 여기까지 읽어주심에 깊이 감사드린다. 

> 주1) 최초 버전의 글이 창피하여 다시 작성한다.

> 주2) 필자가 블로그 이름을 `TheoryDB`라고 지은 이유는 논문들을 AI가 이해할 수 있도록 'Data-Meta' DB로 재편하고 싶은 욕구 때문이다.  
