# 크레인 인형뽑기 게임 LEVEL - 1

``` java
import java.util.Stack;

class Solution {
	public int solution(int[][] board, int[] moves) {
		int answer = 0;
		
		Stack<Integer> element = new <Integer>Stack();
		int i2 = 0;
		for (int i : moves) // 뽑기 시작
		{
			// 알고리즘 시작
			i2 = 0;
			while (i2 != (board.length)) {
				
				if (board[i2][i-1] == 0) {i2++; continue;}
				else {
					if (element.isEmpty() == false) 
					{
						if (element.peek() == board[i2][i-1])
						{
							answer+=2;
							element.pop();
						}
						else
							element.push(board[i2][i-1]);
					}
					else 
						element.push(board[i2][i-1]);                   
					board[i2][i-1] = 0;
					break;
				}
			}
		}
		return answer;
	}
}
```

