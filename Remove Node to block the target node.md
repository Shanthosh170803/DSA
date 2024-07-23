### Minimum Neighbors to Block to ensure Unreachability

This problem asks you to print neighbors (of dest) to block to ensure
unreachability from src to the given node dest , optimally.
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
2 7
``` java
import java.util.*;
public class juspay7 {
    static HashMap<Integer, List<Integer> > hp=new HashMap<>();
    public static void main(String args[]){
        Scanner sc=new Scanner (System.in);
        int n=sc.nextInt();
        List<Integer> nodes=new ArrayList<>();
        for(int i=0;i<n;i++){
            nodes.add(sc.nextInt());
        }
        int n1=sc.nextInt();
        for(int i=0;i<n;i++){
            hp.put(nodes.get(i),new ArrayList<>());
        }
        for(int i=0;i<n1;i++){
            int follow=sc.nextInt();
            int follower=sc.nextInt();
            hp.get(follow).add(follower);
        }
        int follow=sc.nextInt();
        int follower=sc.nextInt();
        List<Integer> vis=new ArrayList<>();
        funcall(follow,follower,vis);
    }
    public static void funcall(int follow,int follower,List<Integer> vis){
        for(int x:hp.get(follow)){
            if(x==follower && !vis.contains(follow)){
                vis.add(follow);
                System.out.print(follow+" ");
                return;
            }
            funcall(x,follower,vis);
        }
    }
}

```
