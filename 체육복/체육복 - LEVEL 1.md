# 체육복 - LEVEL 1

``` java
class Solution {
    public int solution(int n, int[] lost, int[] reserve) {
        ArrayList <Integer>losted = new <Integer>ArrayList();
        ArrayList <Integer>reserved = new <Integer>ArrayList();
        ArrayList <Integer>where = new <Integer>ArrayList();
        
        int answer = 0;
        int cnt = 0;
        int sw = 0;
        
    	for(int k : lost)
    		losted.add(k);
    	for(int k : reserve)
    		reserved.add(k);
        
    	for(int j=0; j<reserved.size(); j++) {
        	for(int i=0; i<losted.size(); i++)
        	{
        		if((reserved.get(j)==losted.get(i)))
        		{
        			++cnt;
        			where.add(reserved.get(j));
        			break;
        		}
        	}	
        }
    	
    	losted.removeAll(where);
	reserved.removeAll(where);
    	
        for(int j=0; j<reserved.size(); ) {
        	sw=0;
        	for(int i=0; i<losted.size(); i++)
        	{
        		if((Math.abs(reserved.get(j)-losted.get(i)))<=1)
        		{
        			++cnt;
        			sw = 1;
        			reserved.remove(j);
        			losted.remove(i);
        			break;
        		}
        	}
        	if(sw != 1) 
        		reserved.remove(j);	
        }
        return n-(lost.length-cnt);
    }
}
```

* ArrayList를 3개나 사용하기 때문에 공간적으로 비효율적이다. 
  * 그러나, 빌려준 후에도 도난 당한 남은 인원이 누구인지를 알 수 있는 장점이 있다.
1. By using remove() methods :
ArrayList provides two overloaded remove() method.
a. remove(int index) : Accept index of object to be removed.
b. remove(Obejct obj) : Accept object to be removed.

