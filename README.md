# Sequence-level unlikelihood fine-tuning KoBART

## 1. Backgroud
Current Korean text abstractive generation models suffer from ```text degeneration```, which includes text repetition issue.

Applying advanced <b>stochastic decoding strategies</b> such as ```top-k sampling``` and ```nucleaus sampling``` can mitigate text repetition issue with open-ended language generation tasks. 

Recent research([Cho et al.2019](https://github.com/facebookresearch/unlikelihood_training)) suggests unlikelihood training to resolve text degeneration issue.

I applied unlikelihood training scheme to finetune pretrained ```KoBART```(Korean BART).

## 2. Data Preparation

1. Set directory : ```$cd data/```
2. Download ```.json```file to current dir from the <b>AI hub</b> [link](https://aihub.or.kr/aidata/8054)

## 3. Training

1. Set directory : ```$cd code/```
2. Training + Validation : ```$python main.py```

## 4. Demo
News Article 1
```
일본 극우 매체인 산케이신문의 논객이 한국의 일본제품 불매운동에 대해 "보기 흉하다"고 지적했다.
그러나 불매운동의 원인을 제공한 일본 정부에 대한 비판은 전혀 찾아볼 수 없어 한쪽으로 치우친 주장이라는 비판을 받고 있다.
구로다 가쓰히로 산케이신문 서울주재 객원 논설위원은 10일 자신의 고정칼럼 '서울 여보세요'에 '보기 흉한 반일 불매운동'이라는 제목의 칼럼을 실었다.
구로다 위원은 35년간 서울 생활을 한 최장수 서울특파원으로도 유명하다.
구로다 위원은 이 칼럼에서 "반일 불매운동의 이번 주 하이라이트(?)는 한 방송 진행자가 뉴스 프로그램이 끝날 시간에 '방송 중에 제가 들고 있는 이 볼펜이 
일제가 아니냐는 시청자의 항의 전화가 왔다. 일본에 대한 우리 국민의 분노가 얼마나 큰지 실감할 수 있었다. 이 볼펜은 국산'이라고 방송을 마무리한 
것"이라고 비꼬았다.
그는 "평소 일본 NHK나 영국 BBC를 본보기로 하고 있는 공영 방송이 감정적인 반일 애국 캠페인을 벌이고 있다니 볼썽사납다"고 비난했다.
구로다 위원은 또 이해찬 더불어민주당 대표의 사케 논란에 대해 "문재인 정권을 떠받치는 여당 간부가 점심에 일본 요리를 먹고 일본 술을 마신 것에 대해 
야당이 추궁하자 술은 '국산 청주'라고 변명했다"면서 "위세 좋던 불매운동도 이제 끝난 것이냐"라고 적었다.
그는 "그냥 음식을 먹는 것은 죄가 아니다. 문재인 대통령도 주요 20개국(G20) 정상회의 때 숙소에서 스시를 즐겼다고 외교 소식통에게 들었다"며 "이 국제화 
시대에 일본제품 불매운동이라니 참으로 비열한 것 같다"고 지적했다.
구로다 위원은 한국의 불매운동을 국제화에 역행하는 수준 낮은 행동으로 치부하면서도 불매운동의 원인을 제공한 일본 정부의 조치에 대해서는 일절 언급하지 
않았다.
한국 최대 수출품인 반도체 핵심소재에 대한 수출을 규제하고, 한국만 콕 집어 백색국가(화이트리스트·수출 간소화 대상)에서 제외한 일본 정부야말로 국제화와 
자유무역주의를 거스른 것이 명백하다.
그러나 구로다 위원은 이 문제는 의도적으로 외면한 채 불매운동 때리기에만 골몰하는 것처럼 보인다.
```

Abstractive Summarization 1
```
구로다 가쓰히로 산케이신문 서울주재 객원 논설위원은 10일 자신의 고정칼럼 '서울 여보세요'에 '보기 흉한 반일 불매운동'이라는 제목의 칼럼을 실었는데, 
일본의 극우 매체인 산케이 신문의 논객이 한국의 일본제품 불매운동을 국제화에 역행하는 수준 낮은 행동으로 치부하면서도 불매운동의 원인을 제공한 일본 
정부의 조치에 대해서는 일절 언급하지 않아 한쪽으로 치우친 주장이라는 비판을 받고 있다.
```

News Article 2
```
결의만으로는 한계…제도적 보완장치 있어야
전문건설사들이 지급을 중단했던 타워크레인 월례비가 건설현장 대부분에서 다시 지급되고 있는 것으로 나타났다.
건설 노동조합 사이의 일자리 다툼은 갈수록 격해져 최근 부상자까지 발생했다.
건설 노사정이 건설현장의 불합리한 관행을 없애보자고 결의한 지 반년이 지났지만, 변화의 모습은 보이지 않고 있다.
18일 건설업계에 따르면 지난 6월 전문업종인 철근콘크리트 업계가 타워크레인 기사에게 월례비를 주지 않겠다고 선언한 지 반년 정도 지난 현재 건설현장 
대부분에서 월례비가 예전처럼 지급되고 있는 것으로 파악됐다.
타워크레인 월례비는 전문건설사가 일을 빨리 처리해달라는 명목으로 타워크레인 기사에게 주는 '급행료' 개념이다.
그런데 금액이 매월 수백만원에 이를 정도로 커지면서 부담을 느낀 철콘업계가 지급 중단을 선언했다.
그러자 타워크레인 기사들이 안전 등을 이유로 작업 속도를 평소보다 늦췄고, 건설현장 가동에 부담을 느낀 많은 철콘업체들이 다시 월례비를 지급하고 있다는 게 
업계의 전언이다.
수도권에 주택건설현장을 둔 한 건설사 관계자는 "월례비 지급 중단 선언 이후 철콘사가 강경하게 나왔지만 결국 철콘사가 다시 월례비를 지급하고 있는 것으로 
안다"면서 "원청에서도 월례비 지급 문제를 고민해 봤지만 뾰족한 해법이 없어 다시 예전 방식으로 돌아갔다"라고 말했다.
타워크레인 가동을 정상화하려고 철콘사가 지급하지 않은 월례비를 원청사나 타워임대업계가 대신 지급하는 방안도 고민했으나 양쪽 모두 지급방식이나 근거를 찾지 
못했다는 설명이다.
건설현장 일자리를 두고 건설 노조 사이에 벌어지는 갈등도 점차 수위가 높아지고 있다.
지난 13일 인천의 한 주택건설현장에서는 타워크레인 기사 일자리를 두고 한국노총 전국건설산업노동조합(건설산업노조) 소속 타워크레인 기사와 한국노총 
연합노련 한국타워크레인조종사노동조합 소속 타워크레인 기사 사이에 싸움이 일어나 건설산업노조 소속 조합원 2명이 화상을 입는 일까지 벌어졌다.
건설산업노조 관계자는 "일자리 문제로 다툼이 벌어져 연합노련 조합원이 건설산업노조 조합원에게 화상을 입혔다"라고 주장했다.
지금까지는 주로 건설현장 타워크레인을 점거하고 고공농성을 벌이며 일자리를 요구했지만, 최근에는 물리적 충돌로 이어지는 등 일자리 갈등 문제가 갈수록 
악화되는 상황이다.
건설 노사정이 지난 6월 불법적인 요소가 많은 월례비와 같은 금품수수나 일자리 요구를 줄여보자며 결의문까지 마련했지만 상황은 오히려 악화되고 있는 셈이다.
건설업계는 월례비나 일자리 문제 모두 금전적인 이해관계가 걸린 사안인 만큼 단순한 결의만으로 해결되기는 어려울 것으로 보고 있다.
제도적 보완 장치가 필요하다는 지적이다.
건설업계 관계자는 "타워크레인만 하더라도 임대는 종합건설에서 하지만 실제 사용은 전문건설에서 하면서 관리 측면에서 애매한 부문이 생긴다"면서 "계약 체결 
방식 등을 새로 검토할 필요가 있다"라고 말했다.
```

Abstractive Summarization 2
```
18일 건설업계에 따르면 지난 6월 전문업종인 철근콘크리트 업계가 타워크레인 기사에게 월례비를 주지 않겠다고 선언한 지 반년 정도 지난 현재 건설현장 
대부분에서 월례비가 예전처럼 지급되고 있는 것으로 파악되었으며 건설 노사정이 건설현장의 불합리한 관행을 없애보자고 결의한 지 반년이 지났지만 건설 
노동조합 사이의 일자리 다툼은 갈수록 격해져 최근 부상자까지 발생했다고 밝혔다.
```

News Article 3
```
실증 연구과제 사업대상자 선정［중부매일 홍종윤 기자］ 세종시가 한국데이터산업진흥원이 공모한 '본인정보(MyData) 실증 연구과제' 공모 사업에 선정돼 내달 
사업에 착수한다.
본인정보 실증서비스 연구과제는 본인의 에너지 사용정보를 제공한 주민에게 빅데이터 맞춤 서비스를 제공하는 사업으로, 세종시와 데이터 전문기업이 참여하는 
컨소시엄이 사업대상자로 선정됐다.
이에 따라 시는 세종절전소 4개 단지를 대상으로 전기, 가스, 난방, 상수도, 하수도 등 5대 에너지 사용 데이터를 수집하고, 데이터 제공자들에게 에너지 
절약을 위한 최적의 솔루션을 제공하게 된다.
세종절전소에 참여하는 4개 단지는 ▶가재마을4단지 ▶범지기마을9단지 ▶새뜸마을10단지 ▶호려울마을6단지 등으로 사업 기간은 5월부터 11월까지 7개월간이며, 
국비 약 10억 원의 사업비가 세종시민을 위해 사용된다.
주요 서비스로는 ▶에너지 사용량이 증가할 때 알림서비스를 제공 ▶비용 절감 방안 제시 ▶에너지 소비패턴 분석 ▶가구유형별 대비 방안 분석 등의 서비스를 
스마트폰 앱(App)을 통해 제공한다.
시는 이번 공모사업을 통해 참여자에게 계획적이고 합리적인 에너지 소비를 위한 서비스를 제공하고, 참여자 중 에너지 절약에 노력한 가구에는 인센티브도 제공할 
계획이다.
또 실증성과를 바탕으로 5-1생활권 스마트시티 국가시범도시의 혁신서비스(에너지 분야)로 발전시켜 나갈 예정이다.
노동영 미래전략담당관은 "잠들어 있는 본인정보를 활용해 새로운 비즈니스 모델을 만들고, 향후에는 에너지 저장과 거래로 소득을 창출하거나 기부를 할 수 있는 
형태로 확산시켜 스마트 에너지 건강도시로 변화할 수 있도록 지원하겠다"고 말했다.
```

Abstractive Summarization 3
```
세종시가 한국데이터산업진흥원이 공모한 '본인정보(MyData) 실증 연구과제' 공모 사업에 선정되어 에너지 사용정보를 제공한 주민에게 빅데이터 맞춤 서비스를 제공하는 사업에 착수하며 이번 공모사업을 통해 참여자에게 계획적이고 합리적인 에너지 소비를 위한 서비스를 제공하고, 참여자 중 에너지 절약에 노력한 가구에는 인센티브도 제공할 예정이라고 밝혔다.
```

## 5. Result

Evaluated by Dacon AI Hub korean text summarization dataset

| Rouge 1 | Rouge 2 | Rouge L |
|:---|:---|:---|
| 0.51745055 | 0.34709406 | 0.41186391 |

## 6. How to use
1. Clone repository : ```$ git clone https://github.com/dongdori Unlikelihood-training-BART-for-text-summarization.git```

2. Save file containing korean articles to be summarized at ```../data/test.jsonl```

3. Run code for inference : ```$ python summarize.py --batch_size 16 --max_length 128 --num_beams 5 --n_ngram 3```

4. csv file containing summarization will be saved at ```../submission/output.csv```