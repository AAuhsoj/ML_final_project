## 24-1 빅데이터 기말 과제

### Scratch coding : Mixture-of-Gaussian Clustering

2024310815  
빅데이터응용학과  
정 솔  

### Description of MGC
원형 벡터를 이용해 클러스터링 구조에 대해 형상화하는 **k-means, LVQ**와는 달리 **확률 모델을 이용해** 클러스터의 프로토타입을 표현하는 알고리즘

![수도코드 캡처_영어](./img/수도코드_캡처_영문.png)
<br>
<br>

### 코드 설명

#### input
   Data set D = {x1, x2,..., xm}  
   Number of Gaussian mixture components k

   - 여기서는 교재에 사용된 수박 데이터 세트 4.0을 사용한다.  (표 9.1)
   - 가우시안 혼합 성분 개수 k도 교재와 동일하게 3으로 설정한다.
   - 이외에도 아래 파라미터를 통해 반복 횟수와 재현성을 조절 한다.  
     - epsilon: 우도 함수 업데이트에 대한 임계값  
     - max_iter : 최대 반복 횟수  
     - random_state : 재현성을 위한 시드 설정

<br>

#### Process  
1. Initialize the parameters  
   
   ![1번_라인](https://github.com/AAuhsoj/ML_final_project/assets/141807643/63aff12d-b65a-4bb3-a875-780d1da15d78)  
   <br>
   가우시안 혼합분포의 모델 파라미터를 초기화한다.  

<br>

1.  The E-step of the EM algorithm  
   ![estep](https://github.com/AAuhsoj/ML_final_project/assets/141807643/4a628298-433b-4b0d-9c26-87f953648d3b)  
   <br>
   아래 식(9.30)에 따라 x_j가 각 혼합 성분에 의해 생성될 사후확률을 계산한다.  
   ![사후확률](https://github.com/AAuhsoj/ML_final_project/assets/141807643/677ec405-db13-45f7-81f9-b1b0bc18f0dd)


<br>

3. The M-step of the EM algorithm  
   ![mstep](https://github.com/AAuhsoj/ML_final_project/assets/141807643/ea78d5b1-f947-41c6-826b-be4a3a4f682c)  

   EM 알고리즘과 계산된 사후 확률을 통해 모델 파라미터를 갱신한다.

<br>

4. EM 알고리즘이 종료 조건 (최대 반복 횟수 도달 또는 우도 함수의 증가량이 매우 작을 때)을 만족할 때까지 반복한다.

<br>

5. 반복이 종료되면 얻어진 가우시안 혼합분포에 따라 클러스터 분할을 결정하고 최종 결과를 반환한다.  
   ![레이블 결정](https://github.com/AAuhsoj/ML_final_project/assets/141807643/59a88df2-1770-4d6b-bee0-614f5d0d7598)  

<br>

### 결과 비교
- 과제로 작성한 코드의 클러스터링 결과  
  ![결과](https://github.com/AAuhsoj/ML_final_project/assets/141807643/dd54ad7b-a48a-4798-8011-0f5d3fab93c2)  


<br>
<br>

(실행 코드의 자세한 설명은 ipynb파일에 기술되어 있습니다.)


