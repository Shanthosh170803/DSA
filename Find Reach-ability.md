### Find Reach-ability
This problem asks you to check for a given static graph if a node dest is
reachable from a given node src .
### Input format:
first line contains the number of elements/nodes
node1 node2 ... node n
array size
element 1 , element2 , ... element n
### Output format:
A List of List ArrayList having the reach-ability from the nodes.
``` java
import java.util.*;
public class juspay4 {
    static List<List<Integer>> list=new ArrayList<>();
    static List<List<Integer>> ans=new ArrayList<>();
    public static void main(String args[]){
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        for(int i=0;i<n;i++){
            List<Integer> li=new ArrayList<>();
            int num=sc.nextInt();
            li.add(num);
            list.add(li);
        }
        int ele=sc.nextInt();
        int[] nodes=new int[ele];
        for(int i=0;i<ele;i++){
            nodes[i]=sc.nextInt();
        }
        for(int i=0;i<ele;i++){
            ArrayList<Integer> cycle=new ArrayList<>();
            for(int x:list.get(nodes[i])){
                funcall(x,cycle);
            }
            ans.add(cycle);
        }
        System.out.println(ans);
    }
    public static void funcall(int n,ArrayList<Integer> cycle){
        if(n==-1){
            return;
        }
        if(cycle.contains(n)){
            return;
        }
        else{
            cycle.add(n);
        }
        funcall(list.get(n).get(0),cycle);
    }
}

```
