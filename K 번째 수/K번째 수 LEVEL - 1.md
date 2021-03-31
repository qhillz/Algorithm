# K번째 수 LEVEL - 1

``` java
class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer;
        int[] copy = array;
        int[] temp = new int[2];
        int[] temp2;
        answer = new int[commands.length];
        
        for(int i=0; i < commands.length; i++) {
        	
        	temp[0] = commands[i][0]-1;
        	temp[1] = commands[i][1]-1;
        	
        	temp2 = new int[temp[1]-temp[0]+1];
        	
        	for(int k = temp[0]; k<=temp[1]; k++)
        	{
        		temp2[k-temp[0]] = array[k];
        	}
        	
        	for(int p = 1; p<temp2.length; p++) 
        	{
        		int pv = temp2[p];
        		int aux = p-1;
        		
        		while(aux>=0 && pv<temp2[aux])
        		{
        			temp2[aux+1] = temp2[aux];
        			aux--;
        		}
        		temp2[aux+1] = pv;
        	}
        	
        	answer[i] = temp2[commands[i][2]-1];
        }       
        return answer;
    }
}
```

