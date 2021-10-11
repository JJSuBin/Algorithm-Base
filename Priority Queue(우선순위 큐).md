## 📘 우선순위 큐

💡 우선순위 큐(Priority Queue)란?
    
    ◻️ 일반적인 큐의 구조 FIFO(First In First Out)를 가지지만, 데이터가 들어온 순서대로 데이터가 가는 것이 아닌
    우선순위를 먼저 결정하고, 우선순위가 높은 데이터가 먼저 나가는 자료구조이다. 
    
💡 우선순위 큐 특징
     
     ◻️ 높은 우선순위의 오소를 먼저 꺼내서 처리하는 구조(큐에 들어가는 원소를 비교가 가능한 기준이 있어야 함)
     ◻️ 내부 요소는 힙으로 구성되어 이진트리 구조로 이루어져 있음 -> 시간 복잡도 O(nLogn)
     ◻️ 우선순위를 중요시해야 하는 상황에서 사용

💡 우선순위 큐 선언
      
      import java.util.PriorityQueue; // import

      // 자료형이 V형인 priorityQueue 선언 (낮은 숫자가 우선순위)
      PriorityQueue<V> priorityQueue = new PriorityQueue<>();

      // 자료형이 V형인 priorityQueue 선언 (높은 숫자가 우선순위)
      PriorityQueue<V> priorityQueue = new PriorityQueue<>(Collections.reverseOrder());

💡 우선순위 큐에 값 삽입      
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136642835-e41a13c9-0fd3-4ee6-ab40-7b2d0178e7be.png" width="800" height="600"/></p>
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136642837-a3869e9b-f824-4860-b868-e834562758ec.png" width="800" height="600"/></p>     
     
     priorityQueue.add(1);     // 값 1 추가
     priorityQueue.offer(2);   // 값 3 추가

💡 우선순위 큐에 값 삭제
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136642839-c1e790a0-cdea-4ec4-973a-8f6822bdfeb3.png" width="800" height="600"/></p>
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136642840-f714a1a3-016a-41d9-a7ea-f43984c36385.png" width="800" height="600"/></p>

     priorityQueue.poll();       // 첫번째 값을 반환하고 제거, 큐가 비어있다면 null
     priorityQueue.remove();     // 첫번째 값 제거
     priorityQueue.clear();      // priorityQueue 초기화

💡 우선순위 큐에 값 참조

     priorityQueue.peek();       // priorityQueue의 첫 번째 값 참조 -> 즉, 우선순위가 가장 높은 값 참조(삭제 X)
