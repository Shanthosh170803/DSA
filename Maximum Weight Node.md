### Maximum Weight Node
Problem Description : You are given a maze with N cells. Each cell may have multiple entry points
but not more than one exit (i.e. entry/exit points are unidirectional doors like valves).
The cells are named with an integer from 0 to N-1.
You have to find : Find the node number of maximum weight node (Weight of a node is the sum of all
nodes pointing to that node).
### INPUT FORMAT :
1. The first line contains the number of cells N.
2. The second line has a list of N values of the edge[ ] array, where edge[i] conatins the cell
number that can be reached from cell 'i' in one step. edge[i] is -1 if the ith doesn't have ans
exit.
### OUTPUT FORMAT :
1. First line denotes the node number with maximum weight node.
### Sample Input :
23
4 4 1 4 13 8 8 8 0 8 14 9 15 11 -1 10 15 22 22 22 22 22 21
### Sample Output :
22
``` java
import java.util.*;
public class juspay2 {
    static List<List<Integer>> list=new ArrayList<>();
    public static void main(String args[]){
        Scanner sc=new Scanner (System.in);
        int n=sc.nextInt();
        int[] array=new int[n];
        for(int i=0;i<n;i++){
            List<Integer> li=new ArrayList<>();
            int num=sc.nextInt();
            li.add(num);
            list.add(li);
        }
        for(int i=0;i<n;i++){
            for(int x:list.get(i)){
                if(x!=-1)
                array[x]=array[x]+i;
            }
        }
        int index=0;
        int max=0;
        for(int i=0;i<array.length;i++){
            if(max<array[i]){
                max=array[i];
                index=i;
            }
        }
        System.out.println(index);
    }
}

``` 
