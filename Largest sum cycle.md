### Largest Sum Cycle
Given a maze with N cells. Each cell may have multiple entry points but not more than one
exit(i.e entry/exit points are unidirectional doors like valves).
You are given an array Edge[] of N integers, where Edge[i] contains the cell number that can be
reached from of cell i in one step. Edge[i] is -1 if the ith cell doesn’t have an exit.
The task is to find :- the sum of the largest sum cycle in the maze(Sum of a cycle is the sum of node
number of all nodes in that cycle).
Note:- The cells are named with an integer value from 0 to N-1. If there is no node pointing to the ith
node then weight of the ith node is zero.
### INPUT FORMAT :-
1. The first line contains the number of cells N.
2. The second line has a list of N values of the edge[ ] array, where edge[i] conatins the cell
number that can be reached from cell 'i' in one step. edge[i] is -1 if the ith doesn't have ans
exit.
### OUTPUT FORMAT :
1. First line denotes length of the largest cycle..
Sample Input :
23
4 4 1 4 13 8 8 8 0 8 14 9 15 11 -1 10 15 22 22 22 22 22 21
Sample Output :
6
``` java
import java.util.*;
public class juspay {
    static HashSet<Integer> hp=new HashSet<>();
    static List<List<Integer>> list=new ArrayList<>();
    public static void main(String args[]){
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        boolean[] tf=new boolean[n];
        for(int i=0;i<n;i++){
            List<Integer> node=new ArrayList<>();
            int num=sc.nextInt();
            node.add(num);
            list.add(node);
        }
        for(int i=0;i<n;i++){
            if(tf[i]==false){
                hp.add(i);
                for(int x:list.get(i)){
                    boolean ans=funcall(i,x);
                    if(ans){
                        for(int y:hp){
                            tf[y]=true;
                        }
                        System.out.println("Size:"+hp.size());
                    }
                }
                hp.clear(); 
            }           
        }
    }
    public static boolean funcall(int start,int end){
        if(start==end){
            return true;
        }
        if(end==-1){
            return false;
        }
        if(hp.contains(end)){
            return false;
        }
        else{
            hp.add(end);
        }
        return funcall(start,list.get(end).get(0));
    }
}

```
