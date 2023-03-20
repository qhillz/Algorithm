# H-Index

```java
import java.util.Arrays;

class Solution {
    public int solution(int[] citations) {

        Arrays.sort(citations);

        for(int i=0; i < citations.length ; i++) {

            int h_index = citations.length - i;

            if(citations[i] >= h_index) {
                return h_index;
            }
        }

        return 0;
    }
}
```



"결국 최대 인용 논문 개수 h의 최대값은 무엇일까?" 에서 부터 시작해보자. ==> citations.length

최대값을 구하는 것이므로 최대값부터 최소값으로 진행하면서 인덱스 0부터 citations.length-1까지 h편 이상 인용이 됬는지를 계속 확인하는 기법이다. 