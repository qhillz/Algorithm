# 같은 숫자는 싫어 LEVEL - 1

``` java
import java.util.*;

public class Solution {
    public int[] solution(int []arr) {
        int[] answer = {};
        int temp = 0;
        ArrayList <Integer>fin = new ArrayList();
        
        temp = arr[0];
        for(int k : arr)
        {
        		if(temp == k)
        			continue;
        		else 
        		{
        			fin.add(temp);
        			temp = k;
        		}
        }
        fin.add(temp);
        answer = new int[fin.size()];
        
        for(int i = 0; i<fin.size(); i++)
        {
        	answer[i] = fin.get(i);
        }
        
        return answer;
    }
}
```

