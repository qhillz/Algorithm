# 모의고사 LEVEL - 1

```java
import java.util.List;
import java.util.ArrayList;

class Solution {
	public int[] solution(int[] answers) {
		int[] pattern1 = { 1, 2, 3, 4, 5 };
		int[] pattern2 = { 2, 1, 2, 3, 2, 4, 2, 5 };
		int[] pattern3 = { 3, 3, 1, 1, 2, 2, 4, 4, 5, 5 };
		int result[];
		int amongst[] = new int[3];
		
		for (int i = 0; i < answers.length; i++) {
			if (answers[i] == pattern1[i % pattern1.length])
				amongst[0] += 1;

			if (answers[i] == pattern2[i % pattern2.length])
				amongst[1] += 1;

			if (answers[i] == pattern3[i % pattern3.length])
				amongst[2] += 1;
		}
		
		int max = amongst[0];
		for(int i=1; i<amongst.length; i++)
		{
			if(max < amongst[i])
				max = amongst[i];
		}
		
		List <Integer>fin = new <Integer>ArrayList();
		
		for(int i=0; i<amongst.length; i++) 
		{
			if(amongst[i] == max)
				fin.add(i+1);
		}
		
		result = new int[fin.size()];
		
		for(int i=0; i<result.length; i++)
		{
			result[i] = fin.get(i);
		}
		
		return result;
	}
}
```

