# 3장 응용 SW 기초 기술 활용  

### 134p - 3번 : 기억공간이 15K, 23K, 22K, 21K 순으로 빈 공간이 있을 때 기억 장치 배치 전력으로 "First Fit"을 사용하여 17K의 프로그램을 적재할 경우 내부 단편화의 크기는 얼마인가?  
1. 5K
2. 6K
3. 7K
4. 8K
> 정답 : 2번, 23K-17K=6K이다.  

First Fit은 프로그램/데이터가 들어갈 수 있는 크기의 빈 영역 중 첫 번째 분할 영역에 배치시키는 방법으로, 17K의 프로그램은 23K의 빈 영역에 저장된다.  
그러므로 내부 단편화의 크기는 23K-17K=6K이다.  

**-> 배치(Placement) 전략의 종류를 이해하는 것이 중요하다!**

배치 전략 : 새로 반입되는 프로그램/데이터를 주기억장치의 어디에 위치시킬 것인지를 결정하는 전략  

- 최초 적합(First Fit) : 프로그램/데이터가 들어갈 수 있는 크기의 빈 영역 중에서 **첫 번째 분할 영역에 배치시키는 방법**  
- 최적 적합(Best Fit) : 프로그램/데이터가 들어갈 수 있는 크기의 빈 영역 중에서 **단편화를 가장 작게 남기는 분할 영역에 배치시키는 방법**  
- 최악 적합(Worst Fit) : 프로그램/데이터가 들어갈 수 있는 크기의 빈 영역 중에서 **단편화를 가장 많이 남기는 분할 영역에 배치시키는 방법**  

단편화 : 주기억장치의 분할된 영역에 프로그램/데이터를 할당할 경우, 분할된 영역이 프로그램/데이터보다 작거나 커서 생기는 빈 기억 공간을 의미  
- 내부 단편화 : 분할된 영역의 크기 > 할당될 프로그램의 크기, 프로그램이 할당된 후 사용되지 않고 남아 있는 빈 공간  
- 외부 단편화 : 분할된 영역의 크기 < 할당될 프로그램의 크기, 프로그램이 할당될 수 없어 사용되지 않고 빈 공간으로 남아있는 분할된 전체 영역  
***
### 143p - 6번 : 페이징 기법에 대한 설명으로 옳지 않은 것은?  
1. 동적 주소 변환 기법을 사용하여 다중 프로그래밍의 효과를 증진시킨다.
2. 내부 단편화가 발생하지 않는다.
3. 프로그램을 동일한 크기로 나눈 단위를 페이지라고 하며, 이 페이지를 블록으로 사용하는 기법이다.
4. 페이지 맵 테이블이 필요하다.
> 정답 : 2번, 페이징 기법에서는 내부 단편화가 발생할 수 있다.  

페이징(Paging) 기법 : 가상기억장치에 보관되어 있는 프로그램과 주기억장치의 영역을 동일한 크기로 나눈 후 나눠진 프로그램(페이지)을 동일하게 나눠진 주기억장치의 영역(페이지 프레임)에 적재시켜 실행하는 기법이다.  
- 페이지(Page) : 프로그램을 일정한 크기로 나눈 단위  
- 페이지 프레임(Page Frame) : 페이지 크기로 일정하게 나누어진 주기억장치의 단위  

**-> 외부 단편화는 발생하지 않으나 내부 단편화는 발생할 수 있다!**  
페이지 크기가 4KB이고, 사용할 프로그램이 17KB라면 프로그램은 페이지 단위로 4KB씩 나누어진다.  
이때 마지막 페이지의 실제 용량은 1KB가 되고, 이것이 주기억장치에 적재되면 3KB의 내부 단편화가 발생된다.  
***
### 155p - 2번 : 선점 기법과 대비하여 비선점 스케줄링 기법에 대한 설명으로 옳지 않은 것은?  
1. 모든 프로세스들에 대한 요구를 공정히 처리한다.
2. 응답 시간의 예측이 용이하다.
3. 많은 오버헤드(Overhead)를 초래할 수 있다.
4. CPU의 사용 시간이 짧은 프로세스들이 사용 시간이 긴 프로세스들로 인하여 오래 기다리는 경우가 발생할 수 있다.
> 정답 : 3번, 선점 스케줄링은 비선점 스케줄링에 비해 오버헤드가 많다.

오버헤드(Overhead) : 어떤 처리를 하기 위하여 들어가는 간접적인 처리 시간, 메모리  
선점 스케줄링의 경우에는 우선순위가 높은 프로세스를 먼저 처리하는 기법을 사용하기 때문에 문맥 교환에 많은 시간이 소요된다.
