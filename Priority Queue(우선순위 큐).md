## ๐ Priority Queue(์ฐ์ ์์ ํ)
๐ก ์ฐ์ ์์ ํ(Priority Queue)๋?
    
    โป๏ธ ์ผ๋ฐ์ ์ธ ํ์ ๊ตฌ์กฐ FIFO(First In First Out)๋ฅผ ๊ฐ์ง์ง๋ง, ๋ฐ์ดํฐ๊ฐ ๋ค์ด์จ ์์๋๋ก ๋ฐ์ดํฐ๊ฐ ๊ฐ๋ ๊ฒ์ด ์๋
    ์ฐ์ ์์๋ฅผ ๋จผ์  ๊ฒฐ์ ํ๊ณ , ์ฐ์ ์์๊ฐ ๋์ ๋ฐ์ดํฐ๊ฐ ๋จผ์  ๋๊ฐ๋ ์๋ฃ๊ตฌ์กฐ์ด๋ค. 
</br>

๐ก ์ฐ์ ์์ ํ ํน์ง
     
     โป๏ธ ๋์ ์ฐ์ ์์์ ์ค์๋ฅผ ๋จผ์  ๊บผ๋ด์ ์ฒ๋ฆฌํ๋ ๊ตฌ์กฐ(ํ์ ๋ค์ด๊ฐ๋ ์์๋ฅผ ๋น๊ต๊ฐ ๊ฐ๋ฅํ ๊ธฐ์ค์ด ์์ด์ผ ํจ)
     โป๏ธ ๋ด๋ถ ์์๋ ํ์ผ๋ก ๊ตฌ์ฑ๋์ด ์ด์งํธ๋ฆฌ ๊ตฌ์กฐ๋ก ์ด๋ฃจ์ด์ ธ ์์ -> ์๊ฐ ๋ณต์ก๋ O(nLogn)
     โป๏ธ ์ฐ์ ์์๋ฅผ ์ค์์ํด์ผ ํ๋ ์ํฉ์์ ์ฌ์ฉ
</br>

๐ก ์ฐ์ ์์ ํ ์ ์ธ
      
      import java.util.PriorityQueue; // import

      // ์๋ฃํ์ด Vํ์ธ priorityQueue ์ ์ธ (๋ฎ์ ์ซ์๊ฐ ์ฐ์ ์์)
      PriorityQueue<V> priorityQueue = new PriorityQueue<>();

      // ์๋ฃํ์ด Vํ์ธ priorityQueue ์ ์ธ (๋์ ์ซ์๊ฐ ์ฐ์ ์์)
      PriorityQueue<V> priorityQueue = new PriorityQueue<>(Collections.reverseOrder());
</br>

๐ก ์ฐ์ ์์ ํ์ ๊ฐ ์ฝ์      
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136642835-e41a13c9-0fd3-4ee6-ab40-7b2d0178e7be.png" width="800" height="600"/></p>
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136642837-a3869e9b-f824-4860-b868-e834562758ec.png" width="800" height="600"/></p>     
     
     priorityQueue.add(1);     // ๊ฐ 1 ์ถ๊ฐ
     priorityQueue.offer(2);   // ๊ฐ 3 ์ถ๊ฐ
</br>

๐ก ์ฐ์ ์์ ํ์ ๊ฐ ์ญ์ 
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136642839-c1e790a0-cdea-4ec4-973a-8f6822bdfeb3.png" width="800" height="600"/></p>
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136642840-f714a1a3-016a-41d9-a7ea-f43984c36385.png" width="800" height="600"/></p>

     priorityQueue.poll();       // ์ฒซ๋ฒ์งธ ๊ฐ์ ๋ฐํํ๊ณ  ์ ๊ฑฐ, ํ๊ฐ ๋น์ด์๋ค๋ฉด null
     priorityQueue.remove();     // ์ฒซ๋ฒ์งธ ๊ฐ ์ ๊ฑฐ
     priorityQueue.clear();      // priorityQueue ์ด๊ธฐํ
</br>

๐ก ์ฐ์ ์์ ํ์ ๊ฐ ์ฐธ์กฐ

     priorityQueue.peek();       // priorityQueue์ ์ฒซ ๋ฒ์งธ ๊ฐ ์ฐธ์กฐ -> ์ฆ, ์ฐ์ ์์๊ฐ ๊ฐ์ฅ ๋์ ๊ฐ ์ฐธ์กฐ(์ญ์  X)
