## ๐ Minimum Spanning Tree(์ต์ ๋น์ฉ ์ ์ฅ ํธ๋ฆฌ)
๐ก ์ ์ฅ ํธ๋ฆฌ(Spannint Tree)๋?
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/142800028-6a9e7d1a-5ff5-4ac1-a410-90acd0f9c3ae.png" width="400" height="250"/></p>

    ๊ทธ๋ํ ๋ด์ ๋ชจ๋  ์ ์ ์ด ๊ฐ์ ์ผ๋ก ์ฐ๊ฒฐ๋์ด ์๊ณ , ๊ฐ์ ๋ค ์ฌ์ด์ ์ฌ์ดํด์ด ์๋ ๊ทธ๋ํ
 </br>   

๐ก ์ ์ฅ ํธ๋ฆฌ(Spannint Tree)๋?    
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/142800200-45dc7212-26bd-4143-b668-5f8fd16fbf2d.png" width="550" height="230"/></p>
    
    โผ๏ธ  Sapnnint Tree ์ค์์ ์ฌ์ฉ๋ ๊ฐ์ ๋ค์ ๊ฐ์ค์น ํฉ์ด ์ต์์ธ ํธ๋ฆฌ -> ์ต์ ๋น์ฉ์ ์ ์ฅํธ๋ฆฌ๋ฅผ ์ ํํ๋ ๊ฒ
    โผ๏ธ  ์ฌ์ดํด์ด ํฌํจ๋์ด์  ์๋
    โผ๏ธ  ๊ตฌํ ๋ฐฉ๋ฒ : ํฌ๋ฃจ์ค์นผ ์๊ณ ๋ฆฌ์ฆ, ํ๋ฆผ ์๊ณ ๋ฆฌ์ฆ
    โผ๏ธ  ๊ฐ์ ์ ๊ฐ์๊ฐ ์ ์ผ๋ฉด ํฌ๋ฃจ์ค์นผ ์๊ณ ๋ฆฌ์ฆ์, ๊ฐ์ ์ ๊ฐ์๊ฐ ๋ง์ผ๋ฉด ํ๋ฆผ ์๊ณ ๋ฆฌ์ฆ์ ์ ํํ๋ค.
    
</br>   
๐ก Kruscal vs Prim?

    โป๏ธ Kruscal ์๊ณ ๋ฆฌ์ฆ 
      1. ๊ฐ์ ๋ค์ ๊ฐ์ค์น๋ฅผ ๊ธฐ์ค์ผ๋ก ์ค๋ฆ์ฐจ์ ์ ๋ ฌํ๋ค.
      2. ์ ๋ ฌ๋ ๊ฐ์  ๋ฆฌ์คํธ์์ ์์๋๋ก ์ฌ์ดํด์ ํ์ฑํ์ง ์๋ ๊ฐ์ ์ ์ ํํ๋ค.
        - ๊ฐ์ฅ ๋ฎ์ ๊ฐ์ค์น๋ฅผ ๋จผ์  ์ ํํ๋ค.
        - ์ฌ์ดํด์ ํ์ฑํ๋ ๊ฐ์ ๋ฆฌ์๋ฉด ๋ค์ ๊ฐ์ ์ ์ ํํ๋ค.
      3. ํด๋น ๊ฐ์ ์ ํ์ฌ์ MST(์ต์ ๋น์ฉ ์ ์ฅ ํธ๋ฆฌ)์ ์งํฉ์ ์ถ๊ฐ, (n-1)๊ฐ์ ๊ฐ์ ์ด ์ ํ๋  ๋๊น์ง ๋ฐ๋ณตํ๋ค.
      
    โป๏ธ Prim ์๊ณ ๋ฆฌ์ฆ
      1. ์์ ๋จ๊ณ์์๋ ์์ ์ ์ ๋ง์ด MST(์ต์ ๋น์ฉ ์ ์ฅ ํธ๋ฆฌ) ์งํฉ์ ํฌํจ๋๋ค.
      2. ์ ๋จ๊ณ์์ ๋ง๋ค์ด์ง MST ์งํฉ์ ์ธ์ ํ ์ ์ ๋ค ์ค์์ ์ต์ ๊ฐ์ ์ผ๋ก ์ฐ๊ฒฐ๋ ์ ์ ์ ์ ํํ์ฌ ํธ๋ฆฌ๋ฅผ ํ์ฅํ๋ค.
         ์ฆ, ๊ฐ์ฅ ๋ฎ์ ๊ฐ์ค์น๋ฅผ ๋จผ์  ์ ํํ๋ค.
      3. ์์ ๊ณผ์ ์ ํธ๋ฆฌ๊ฐ (N-1)๊ฐ์ ๊ฐ์ ์ ๊ฐ์ง ๋๊น์ง ๋ฐ๋ณตํ๋ค.
      
</br>   
๐ก MST๋ฅผ Prim ์๊ณ ๋ฆฌ์ฆ์ผ๋ก ๊ตฌํ : [๋ฐฑ์ค 1197๋ฒ](https://www.acmicpc.net/problem/1197) 
 
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
	    * Prim ๋ฐฉ์
	    * - ์ธ์  ํ๋ ฌ ๋ฐฉ์
	    * - ์ฐ์ ์์ ํ์ ์์ ์ ์  1์ ์ฝ์ํ๊ณ  ์์
	    * - ์ฐ๊ฒฐ๊ดธ ์ ์ ์ ๋ชจ๋  ๊ฐ์ ๋ค ์ค ๋ฐฉ๋ฌธํ์ง ์์ ๋ธ๋ ํ์, ์ฐ์ ์์ ํ์ ์ฝ์
	    * - ๋ชจ๋  ๋ธ๋๋ฅผ ๋ฐฉ๋ฌผ ํ ๋๊น์ง ๋ฐ๋ณต 
	    */
	    static int prim() {
		    PriorityQueue<Node_1197> pq=new PriorityQueue<>();
		    pq.add(new Node_1197(1,0));
		    visited=new boolean[v+1];
		
		    int result=0;
		    int count=0;
		
		    while(!pq.isEmpty()) {
			    Node_1197 now=pq.poll();
			
			    if(visited[now.node]) // ์ด๋ฏธ ๋ฐฉ๋ฌธํ ๋ธ๋๋ผ๋ฉด ๋์ด๊ฐ๋ค.
				    continue;
			
			    result+=now.weight; // ๊ฐ์ค์น ํฉ  
			    count++; // ๋ฐฉ๋ฌธ ๋ธ๋ ๊ฐ์
			    visited[now.node]=true;
			
			    // ๋ชจ๋  ๋ธ๋๋ฅผ ๋ฐฉ๋ฌธํ๋ค๋ฉด ์ข๋ฃ
			    if(count==v)
				    return result;
			
			    // now์ ์ธ์ ํ ๋ธ๋ ํ์
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
