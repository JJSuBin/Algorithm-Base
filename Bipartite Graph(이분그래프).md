## 📘 이분그래프

💡 이분그래프란?
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136502673-d7bf0cfe-68d1-4988-8f31-fcfeb36f0dd3.png" width="700" height="300"/></p>

    ◼️ 이분 그래프(bipartite graph)란 모든 꼭짓점을 빨강과 파랑으로 색칠하되, 모든 변이 빨강과 파랑 꼭짓점을 포함하도록 색칠할 수 있는 그래프이다.
    ◼️ 즉, 인접한 정점끼리 서로 다른 색으로 칠해서 모든 정점을 두 가지 색으로만 나타낼 수 있는 그래프를 말한다. 

💡 이분그래프란 판별 방법

    ◼️ 이분 그래프인지 확인하기 위해서는 DFS/BFS 알고리즘을 사용한다.
    ◼️ 모든 정점을 방문하며 간선을 검사하기 때문에 시간 복잡도는 O(V+E)로 그래프 탐색 알고리즘과 같다.
    ◼️ 판별 과정
        ◻️ 1. 정점을 방문할 때마다 두 가지 색 중 한 색으로 칠한다.
        ◻️ 2. 자신과 인접한 정점은 자신과 다른 색으로 칠한다.
        ◻️ 3. 탐색을 진행하는 과정에서 자신과 인접한 정접의 색이 자신과 동일하면 이분 그래프가 아니다.
        ◻️ 4. 모든 정점을 방문했는데 위와 같은 경우가 없다면 이분그래프이다. 
        
💡 이분그래프란 판별 JAVA 코드 : [백준 1707번](https://www.acmicpc.net/problem/1707)
    
    
    import java.util.*;

    public class BaekJoon_1707 {
	  static ArrayList<ArrayList<Integer>> graph;
	  static int v,e;
	  static int[] colors; // 각 노드의 색을 저장하는 배역(0은 아직 아무색도 칠해지지 않은 경우, 1/-1로 색을 칠한다.)
	  static boolean check; // 이분그래프인지 아닌지 확인하는 변수
	    
    public static void main(String[] args) {
		  Scanner sc=new Scanner(System.in);
		  int testcase=sc.nextInt();
		
		  while(testcase-->0) {
			graph=new ArrayList<>();
			v=sc.nextInt();
			e=sc.nextInt();
			colors=new int[v+1];
			check=true; // 초기에는 이분그래프가 맞다고 생각
			
			// 노드 추가
			for(int i=0;i<=v;i++) {
				graph.add(new ArrayList<>());
				colors[i]=0; // 아직 방문하지 않은 정점의 색은 0으로 초기화
			}
			
			// 간선 정보 입력
			for(int i=0;i<e;i++) {
				int a=sc.nextInt();
				int b=sc.nextInt();
				
				// 양방향
				graph.get(a).add(b);
				graph.get(b).add(a);
			}
			
			// 모든 노드 탐색
			for(int i=1;i<=v;i++) {
				// check 변수가 false면 이분그래프가 아니기 때문에 탐색 중지
				if(!check)
					break;
				// 아직 어떤 그룹에도 속해있지 않다면 dfs 수행
				if(colors[i]==0)
					dfs(i,1); // 첫 번째 정점을 1로 색칠하고 시작
			}
			
			System.out.println(check?"YES":"NO");
		}
	}
	  static void dfs(int start, int color) {
		colors[start]=color; // 시작 노드는 1로 색칠한다.
		
		// 시작노드와 연결된 모든 노드 탐색
		for(int i=0;i<graph.get(start).size();i++) {
			int temp=graph.get(start).get(i); // 다음 노드
			
			// 자기 자신의 색과 다음 노드의 색이 같다면 이분그래프 X
			if(colors[start]==colors[temp]) {
				check=false;
				return;
			}
			
			// 아직 색이 칠해지지 않은 경우는 자신과 다른 색을 칠한다. 
			if(colors[temp]==0)
				dfs(temp,-color);
		   }
	      }
    }
