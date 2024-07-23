### 
React Developer Community is a community of React developers. It allows developers to reach
out to others and discuss various topics around JS programming. This community has been
modelled as a directed social network graph.
Find Reachability
JS newbie A wants to check if he can reach out to a React expert B using his network.
### Input Format
total members in React Developer Community
memberId1
MemberId2..........................MemberIdN
Total possible edges
.............................
Follower
Following
### Output Format:
"0" OR "1"
### Sample Testcase #0
4
2
5
7
9
4
2 9
7 2
7 9
9 5
7
9
### Testcase Output
1

``` java
import java.util.*;
public class juspay5 {
    static Map<Integer, List<Integer> > hp=new HashMap<>();
    public static void main(String args[]){
        Scanner sc=new Scanner (System.in);
        int n=sc.nextInt();
        List<Integer> nodes=new ArrayList<>();
        for(int i=0;i<n;i++){
            int num=sc.nextInt();
            nodes.add(num);
        }
        
        for(int x: nodes){
            hp.put(x,new ArrayList<>());
        }
        int possibleEdges=sc.nextInt();
        for(int i=0;i<possibleEdges;i++){
            int follower=sc.nextInt();
            int following=sc.nextInt();
            hp.get(follower).add(following);
        }
        int foll=sc.nextInt();
        int follow=sc.nextInt();
        if(hp.containsKey(foll)){
            for(int x:hp.get(foll)){
                List<Integer> vis=new ArrayList<>();
                boolean b=funcall(x,follow,vis);
                if(b){
                    System.out.println(1);
                    break;
                }
                else{
                    System.out.println(0);
                    break;
                }
            }
        }
    }
    public static boolean funcall(int start,int follow,List<Integer> vis){
        if(start==follow){
            return true;
        }
        if(vis.contains(start)){
            return false;
        }
        else{
            vis.add(start);
        }
        boolean b=false;
        for(int x:hp.get(start)){
            b=funcall(x,follow,vis);
        }
        return b;
    }
}

```
