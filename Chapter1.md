# Python for Coding Test
## 본 내용은 '이것이 코딩 테스트' 책을 근거로 본인 이해한 내용을 정리 할 목적으로 작성하였습니다. 저자권에 문작 되면 삭제 하겠습니다.
![codingtest](https://github.com/DooHub/Python/assets/99073912/d6bb3304-70a4-49e6-bb38-f261ecd47534)
1. Basic Python
   - Input method
     ```python
     n,m,k=map(int,input().split())
     data =list(map(int,input().split()))

     대용량 입력

     import sys
     sys.stdin.readline().rstrip()
     ```
     rstrip() 엔터 입력으로 인한 공백 문자 제거

   - 표준 라이브러리 사용
     1) eval()함수는 수학 수식이 문자열 형식으로 들오면 해당 수식을 게산한 결과를 반환- int
       ```python
       result=eval("(3+5)*7")
       ```
     2) permutations함수는 리스트에서 n개를 data를 뽑아 나열하는 모든 순열을 계산해 줌. 계산 값은 list로 받아함.
      ```python
      from itertools import permutations
      data=['A','B','C','D']
      result=list(permutations(data,3))
      ```
     3) combinations는 n개 data를 순서를 고려하지 않고 조합한 값을 계산해 줌. 계산 값은 list로 받야함
     ```python
     from itertools import combinations
     data=['A','B','C','D']
     result=list(combinations(data,3))
     ```
     
2. Greedy  
   현재 상황에서 지금 당장 좋은 것만 고르는 방법. 정당성(예외 발생)을 검토하는 것 까지 완료 되어야 적용 가능
3. 
