## 📘 Minimum Spanning Tree(최소 비용 신장 트리)
💡 신장 트리(Spannint Tree)란?
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/142800028-6a9e7d1a-5ff5-4ac1-a410-90acd0f9c3ae.png" width="400" height="250"/></p>

    그래프 내의 모든 정점이 간선으로 연결되어 있고, 간선들 사이에 사이클이 없는 그래프
 </br>   

💡 신장 트리(Spannint Tree)란?    
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/142800200-45dc7212-26bd-4143-b668-5f8fd16fbf2d.png" width="550" height="230"/></p>
    
    Sapnnint Tree 중에서 사용된 간선들의 가중치 합이 최소인 트리 -> 최소 비용의 신장트리를 선택하는 것
    사이클이 포함되어선 안됌
    구현 방법 : 크루스칼 알고리즘, 프림 알고리즘
    간선의 개수가 적으면 크루스칼 알고리즘을, 간선의 개수가 많으면 프림 알고리즘을 선택한다.
    
</br>   
💡 Kruscal vs Prim?

    ◻️ Kruscal 알고리즘 
      1. 간선들을 가중치를 기준으로 오름차순 정렬한다.
      2. 정렬된 간선 리스트에서 순서대로 사이클을 형성하지 않는 간선을 선택한다.
        - 가장 낮은 가중치를 먼저 선택한다.
        - 사이클을 형성하는 간선리아면 다음 간선을 선택한다.
      3. 해당 간선을 현재의 MST(최소 비용 신장 트리)의 집합에 추가, (n-1)개의 간선이 선택될 때까지 반복한다.
      
    ◻️ Prim 알고리즘
      1. 시작 단계에서는 시작 정점만이 MST(최소 비용 신장 트리) 집합에 포함된다.
      2. 앞 단계에서 만들어진 MST 집합에 인접한 정점들 중에서 최소 간선으로 연결된 정점을 선택하여 트리를 확장한다.
         즉, 가장 낮은 가중치를 먼저 선택한다.
      3. 위의 과정을 트리가 (N-1)개의 간선을 가질 때까지 반복한다.
      
</br>   
💡 MST를 Prim 알고리즘으로 구현 : [백준 1197번](https://www.acmicpc.net/problem/1197) 
 
    import java.util.*;

    class Node_1197 implements Comparable<Node_1197> {
	    int node, weight;
	
	    public Node_1197(int node, int weight) {
		    this.node=node;
		    this.weight=weight;
	    }
	
	    @Override
	    public int compareTo(Node_1197 o) {
		    return this.weight-o.weight;
	    }
    }

    public class BaekJoon_1197 {
	    static ArrayList<ArrayList<Node_1197>> graph=new ArrayList<>();
	    static int v,e;
	    static boolean[] visited;
	    public static void main(String[] args) {
		    
        Scanner sc=new Scanner(System.in);
		    v=sc.nextInt();
		    e=sc.nextInt();
		
		    for(int i=0;i<=v;i++)
			    graph.add(new ArrayList<>());
		
		    for(int i=0;i<e;i++) {
			    int a=sc.nextInt();
			    int b=sc.nextInt();
			    int c=sc.nextInt();
			
			    graph.get(a).add(new Node_1197(b,c));
			    graph.get(b).add(new Node_1197(a,c));
		    }
		
		    System.out.println(prim());
	    }

	    /*
	    * Prim 방식
	    * - 인접 행렬 방식
	    * - 우선순위 큐에 시작 정점 1을 삽입하고 시작
	    * - 연결괸 정점의 모든 간선들 중 방문하지 않은 노드 탐색, 우선순위 큐에 삽입
	    * - 모든 노드를 방물 할때까지 반복 
	    */
	    static int prim() {
		    PriorityQueue<Node_1197> pq=new PriorityQueue<>();
		    pq.add(new Node_1197(1,0));
		    visited=new boolean[v+1];
		
		    int result=0;
		    int count=0;
		
		    while(!pq.isEmpty()) {
			    Node_1197 now=pq.poll();
			
			    if(visited[now.node]) // 이미 방문한 노드라면 넘어간다.
				    continue;
			
			    result+=now.weight; // 가중치 합  
			    count++; // 방문 노드 개수
			    visited[now.node]=true;
			
			    // 모든 노드를 방문했다면 종료
			    if(count==v)
				    return result;
			
			    // now와 인접한 노드 탐색
			    for(int i=0;i<graph.get(now.node).size();i++) {
				    Node_1197 next=graph.get(now.node).get(i);
				
				    if(visited[next.node])
					    continue;
				
				    pq.add(next);
			    }
		    }
		    return result;
	    }
    }
