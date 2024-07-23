### Shortest Path in DAG 
Given a weighted graph and a source vertex in the graph, find the shortest paths from the source to all the other vertices in the given graph.

Note: The given graph does not contain any negative edge.
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
2 9 2
7 2 3
7 9 7
9 5 1
### Testcase Output
5
``` java
import java.util.*;
public class juspay6 {
    static Map<Integer,List<List<Integer>>> hp=new HashMap<>();
    public static void main(String args[]){
        Scanner sc=new Scanner (System.in);
        int n=sc.nextInt();
        List<Integer> list=new ArrayList<>();
        for(int i=0;i<n;i++){
            int a=sc.nextInt();
            list.add(a);
        }
        int n2=sc.nextInt();
        
        for(int i=0;i<n;i++){
            hp.put(list.get(i),new ArrayList<>());
        }
        for(int i=0;i<n2;i++){
            int n1=sc.nextInt();
            int con=sc.nextInt();
            int weight=sc.nextInt();
            List<Integer> li=new ArrayList<>();
            li.add(con);
            li.add(weight);
            hp.get(n1).add(li);
        }
        int start=sc.nextInt();
        int end=sc.nextInt();
        Stack<Integer> stack=new Stack<>();
        List<Integer> vis=new ArrayList<>();
        for(Map.Entry<Integer,List<List<Integer>>> map:hp.entrySet()){
            int k=map.getKey();
            if(!vis.contains(k)){
                vis.add(k);
                dfs(k,vis,stack);
                stack.push(k);
            }
        }
        HashMap<Integer,Integer> path=new HashMap<>();
        for(int i=0;i<n;i++){
            path.put(list.get(i),0);
        }
        while(!stack.isEmpty()){
            int nod=stack.pop();
                findpath(nod,path);
        }
        System.out.println("ShortesPath: "+path.get(end));
    }
    public static void findpath(int nod1,HashMap<Integer,Integer> path){
        for(List<Integer> li:hp.get(nod1)){
            int nod2=li.get(0);
            int weight2=li.get(1);
            int weight1=path.get(nod1);
            int weight=weight1+weight2;
            if(weight< path.get(nod2)){
                path.put(nod2,weight);
            }
            else if(weight1==0 || path.get(nod2)==0){
                path.put(nod2,weight);
            }
        }
    }
    public static void dfs(int k,List<Integer> vis,Stack<Integer> stack){

        for(List<Integer> li:hp.get(k)){
            if(li.isEmpty()){
                stack.push(k);
                return;
            }
            else if(!vis.contains(li.get(0))){
                vis.add(li.get(0));
                dfs(li.get(0),vis,stack);
                stack.push(li.get(0));
            }
        }
    } 
}
```
