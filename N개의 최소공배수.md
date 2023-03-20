# N개의 최소공배수

```javascript
import java.util.Arrays;
import java.util.Collections;
import java.util.Comparator;

class Solution {
    public int solution(int[] arr) {
        int lcm = arr[0];
        
        if(arr.length >= 2) {
        	int gcd = gcd(Math.max(arr[0], arr[1]), Math.min(arr[0], arr[1]));
        	lcm = (arr[0] * arr[1]) / gcd;
            
            for(int i=2; i<arr.length; i++) {
            	int temp = gcd(Math.max(lcm, arr[i]), Math.min(lcm, arr[i]));
            	lcm = (lcm * arr[i]) / temp;
            }
        }
        
        return lcm;
    }
    
    public static int gcd(int a, int b) {
    	
    	if(b == 0) {
    		return a;
    	}
    	
    	return gcd(b, a%b);
    }
    
    public static void main(String args[]) {
    	Solution a = new Solution();
    	a.solution(new int[] {2,6,8,14});
    }
}
```



GCD (최대공약수를 구하는 방식) => (b , a%b) => (a%b == 0 일때의 b를 return하면 된다.)

LCM (최소공배수를 구하는 방식) => GCD / a * b


여러 수의 최소 공배수를 구한다는 것은 (a,b,c,d) => ab의 lcm / 이 lcm과 c 의 lcm 연쇄적인 lcm 도출을 구현하면 된다.