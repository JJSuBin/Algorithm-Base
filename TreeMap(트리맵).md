## 📘 TreeMap(트리맵)
💡 트리맵(TreeMap)이란?
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136732237-297e174d-0a77-4bc9-bf41-855ff8e0f876.png" width="600" height="300"/></p>
    
    ◻️ TreeMap 클래스는 키와 값을 한 쌍으로 하는 데이터를 이진 검색 트리(binary search tree)의 형태로 저장한다.
    ◻️ TreeMap에 객체를 저장하면 자동으로 정렬되는데 숫자 타입일 경우 오름차순으로 정렬되고, 문자열 타입일 경우 유니코드 순으로 정렬된다.
    ◻️ 정렬된 상태로 Map을 유지해야 하거나 정렬된 데이터를 조회해야 하는 경우 사용된다.
    ◻️ TreeMap의 가장 큰 장점은 객체를 저장하면 자동으로 정렬된다는 점과, 내장 함수를 사용하여 최솟 값과 최댓값에 접근이 가능하다는 점이다.
<br/>

💡 트리맵(TreeMap) 선언

      TreeMap<V,T> map = new TreeMap<Integer,String>(); // key 값의 자료형은 V, value 값의 자료형은 T인 TreeMap 생성
<br/>

💡 트리맵(TreeMap)에 값 삽입
      
      map.put(1, "사과"); // 값 삽입
<br/>

💡 트리맵(TreeMap)에 값 삭제

      map.remove(1); // key 값 1 제거 -> 값도 함께 제거
      map.clear(); // TreeMap 초기화
<br/>

💡 트리맵(TreeMap) 값 참조

      System.out.println(map); // 맵에 저장된 값 전체 출력
      System.out.println(map.get(1)); // key값 1의 value얻기
      System.out.println(map.firstEntry());// 최소 key 값의 value 출력
      System.out.println(map.firstKey()); // 최소 Key값 출력
      System.out.println(map.lastEntry()); // 최대 key값의 value 출력
      System.out.println(map.lastKey()); // 최대 Key값 출력
<br/>

💡 Itertor 사용

      Iterator<Entry<Integer, String>> entries = map.entrySet().iterator();
      while(entries.hasNext()){
          Map.Entry<Integer, String> entry = entries.next();
          System.out.println("[Key]:" + entry.getKey() + " [Value]:" +  entry.getValue());
      }
<br/>
