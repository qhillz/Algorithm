# 두 개 뽑아서 더하기 LEVEL - 1

``` java
import java.util.Arrays;
import java.util.HashSet;

class Solution {

	static public int[] solution(int[] numbers) {
		int answer[] = {};
		HashSet<Integer> inter = new HashSet<Integer>();
		int temp = 0;

		for (int i = 0; i < numbers.length; i++) {
			for (int j = 1 + temp; j < numbers.length; j++) {
				int putin = numbers[i] + numbers[j];
				inter.add(putin);
			}
			++temp;
		} // 최종본 output
		
		answer = new int[inter.size()];
		temp = 0;
		for(int temp2 : inter)
		{
			answer[temp] = temp2;
			++temp;
		}
		Arrays.sort(answer);		
		return answer;
	}
}
```

