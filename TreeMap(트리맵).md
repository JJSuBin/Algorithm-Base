## ๐ TreeMap(ํธ๋ฆฌ๋งต)
๐ก ํธ๋ฆฌ๋งต(TreeMap)์ด๋?
<p align="center"><img src="https://user-images.githubusercontent.com/45066381/136732237-297e174d-0a77-4bc9-bf41-855ff8e0f876.png" width="600" height="300"/></p>
    
    โป๏ธ TreeMap ํด๋์ค๋ ํค์ ๊ฐ์ ํ ์์ผ๋ก ํ๋ ๋ฐ์ดํฐ๋ฅผ ์ด์ง ๊ฒ์ ํธ๋ฆฌ(binary search tree)์ ํํ๋ก ์ ์ฅํ๋ค.
    โป๏ธ TreeMap์ ๊ฐ์ฒด๋ฅผ ์ ์ฅํ๋ฉด ์๋์ผ๋ก ์ ๋ ฌ๋๋๋ฐ ์ซ์ ํ์์ผ ๊ฒฝ์ฐ ์ค๋ฆ์ฐจ์์ผ๋ก ์ ๋ ฌ๋๊ณ , ๋ฌธ์์ด ํ์์ผ ๊ฒฝ์ฐ ์ ๋์ฝ๋ ์์ผ๋ก ์ ๋ ฌ๋๋ค.
    โป๏ธ ์ ๋ ฌ๋ ์ํ๋ก Map์ ์ ์งํด์ผ ํ๊ฑฐ๋ ์ ๋ ฌ๋ ๋ฐ์ดํฐ๋ฅผ ์กฐํํด์ผ ํ๋ ๊ฒฝ์ฐ ์ฌ์ฉ๋๋ค.
    โป๏ธ TreeMap์ ๊ฐ์ฅ ํฐ ์ฅ์ ์ ๊ฐ์ฒด๋ฅผ ์ ์ฅํ๋ฉด ์๋์ผ๋ก ์ ๋ ฌ๋๋ค๋ ์ ๊ณผ, ๋ด์ฅ ํจ์๋ฅผ ์ฌ์ฉํ์ฌ ์ต์ ๊ฐ๊ณผ ์ต๋๊ฐ์ ์ ๊ทผ์ด ๊ฐ๋ฅํ๋ค๋ ์ ์ด๋ค.
<br/>

๐ก ํธ๋ฆฌ๋งต(TreeMap) ์ ์ธ

      TreeMap<V,T> map = new TreeMap<Integer,String>(); // key ๊ฐ์ ์๋ฃํ์ V, value ๊ฐ์ ์๋ฃํ์ T์ธ TreeMap ์์ฑ
<br/>

๐ก ํธ๋ฆฌ๋งต(TreeMap)์ ๊ฐ ์ฝ์
      
      map.put(1, "์ฌ๊ณผ"); // ๊ฐ ์ฝ์
<br/>

๐ก ํธ๋ฆฌ๋งต(TreeMap)์ ๊ฐ ์ญ์ 

      map.remove(1); // key ๊ฐ 1 ์ ๊ฑฐ -> ๊ฐ๋ ํจ๊ป ์ ๊ฑฐ
      map.clear(); // TreeMap ์ด๊ธฐํ
<br/>

๐ก ํธ๋ฆฌ๋งต(TreeMap) ๊ฐ ์ฐธ์กฐ

      System.out.println(map); // ๋งต์ ์ ์ฅ๋ ๊ฐ ์ ์ฒด ์ถ๋ ฅ
      System.out.println(map.get(1)); // key๊ฐ 1์ value์ป๊ธฐ
      System.out.println(map.firstEntry());// ์ต์ key ๊ฐ์ value ์ถ๋ ฅ
      System.out.println(map.firstKey()); // ์ต์ Key๊ฐ ์ถ๋ ฅ
      System.out.println(map.lastEntry()); // ์ต๋ key๊ฐ์ value ์ถ๋ ฅ
      System.out.println(map.lastKey()); // ์ต๋ Key๊ฐ ์ถ๋ ฅ
<br/>

๐ก Itertor ์ฌ์ฉ

      Iterator<Entry<Integer, String>> entries = map.entrySet().iterator();
      while(entries.hasNext()){
          Map.Entry<Integer, String> entry = entries.next();
          System.out.println("[Key]:" + entry.getKey() + " [Value]:" +  entry.getValue());
      }
<br/>
