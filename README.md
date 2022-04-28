# Ford-Fulkerson을 위한 기본 개념
## 최대 유량 문제  
정의 : 정한 지점에서 다른 지점으로, 얼마나 많은 유량(flow)을 동시에 보낼 수 있는지 계산하는 문제
용량 c(c,V) : 정점 u에서 v로 전송 할수 있는 최대 용량  
유량 (Flow) : f(u, v) : 정점 u 에서 v 로 실제 흐르고 있는 유량  
잔여 용량 (Residual Capacity) : r(u, v) = c(u, v) – f(u, v), 간선의 용량과 살제로 흐르는 유량의 차이 
소스 (Source) : s = 모든 유량이 시작되는 정점  
싱크 (Sink) : t = 모든 유량이 도착하는 정점   
증가 경로 : 소스에서 싱크로 유량을 보낼 수 있는 경로 
## 최대 유량 문제의 기본 속성
용량 제한 속성 : 유량은 용량보다 작거나 같습니다.
유량의 대칭성 : u 에서 v 로 유량이 흐르면, v 에서 u 로 음수의 유량이 흐르는 것과 동일  
유량의 보존성 : 각 정점에 들어오는 유량과 나가는 유량은 같습니다.  
## 최대 유량 문제의 문제점  
경로 탐색시, 탐색 순서에 따라서 모든 경로를 찾지 못하고 최대 유량을 결정 지어 버리고 프로그램이 중지한다 왜냐면 최대치를 찾을 때, 비교하는 반복문을 사용하기 때문
## 문제점을 해결하기 위한 방법 : 유량 상쇄(Cancellation)  
유량 상쇄란 모든경로에 기존에 존재하는 간선들과 반대 되는 방향의 간선을 추가한 뒤, 각 간선으로 유량을 흘려 보낼 때, 반대 방향으로 음의 유량을 보냄으로써 유량을 상쇄 시키는 것을 의미한다. 물리적으로 현실에서는 불가능 하지만 잔여 용량을 남겨 추가적인 경로를 탐색할 수 있도록 하기 위한 작업(이거 생각한 사람 천재인듯하다.)

---
# Ford-Fulkerson 알고리즘 정의  
Greedy 알고리즘을 이용해 최대 유량 문제을 계산하는 것   
## Ford-Fulkerson 알고리즘의 통시적 발전 흐름  
1956년 Ford-fulkerson 알고리즘은 1956년 ford와 fulkerson에 의해 발표되었다. 사실 이때는 유량 상쇄를 통한 명확한 탐색 순서에 대한 정의가 내려지지 않았기 때문에 알고리즘이 아닌 방법이라고 부르는 게 맞는 단어 선택이다.  
1970년 Dinic 알고리즘은 유량 상쇄를 통한 탐색 순서에 대한 방법론이 추가된 알고리즘이 Yeflim에 의하여 발표되었다. 이 알고리즘은 BFS와 DFS를 결합하여 알고리즘을 해결 하였다.  
1972년 Edmond-Karp 알고리즘은 Dinic과 함께 연구하다가 Edmond와 Karp가 독자적으로 BFS 탐색법을 통하여 Dinic알고리즘보다 좀더 시간적으로 효율적인 즉 시간복잡도가 더좋은 알고리즘을 발표하였다.  
## Ford-Fulkerson 알고리즘의 경로 탐색법에 따른 알고리즘 종류
Edmond-Karp 알고리즘 (BFS 방식)  
Dinic 알고리즘 (BFS 방식과 DFS방식)   
DFS 방식을 이용한 ford-fulkerson 알고리즘   

---
### 실행 결과 및 성능 분석

Edmond-Karp 알고리즘 실행 결과 
![Edmond karp 결과값](https://user-images.githubusercontent.com/101388180/165814101-6b7a76cd-810b-45d9-883c-eea342c249c8.PNG)

# 결론

