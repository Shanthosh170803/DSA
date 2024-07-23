### Nearest Meeting Cell
### Problem Description :
You are given a maze with N cells. Each cell may have multiple entry points but not more than one
exit (i.e. entry/exit points are unidirectional doors like valves). The cells are named with an integer
from 0 to N-1.
You have to find :
Nearest meeting cell : Given any two cells - C1, C2, find the closest cell Cm that can be reached
from both C1 and C2.
### INPUT FORMAT :
1. The first line contains the number of cells N.
2. The second line has a list of N values of the edge[ ] array, where edge[i] conatins the cell
number that can be reached from cell 'i' in one step. edge[i] is -1 if the ith doesn't have an
exit.
3. Third line for each testcase contains two cell numbers whose nearest meeting cell needs to
be found. (return -1 if there is no meeting cell from two given cells)
### OUTPUT FORMAT :
Output a single line that denotes the nearest meeting cell (NMC).
### Sample Input :
23
4 4 1 4 13 8 8 8 0 8 14 9 15 11 -1 10 15 22 22 22 22 22 21
9 2
### Sample Output :
4
``` java
import java.util.*;
public class juspay3 {
    static List<List<Integer>> list=new ArrayList<>();
    static ArrayList<Integer> cycle=new ArrayList<>();
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        for(int i=0;i<n;i++){
            List<Integer> li=new ArrayList<>();
            int num=sc.nextInt();
            li.add(num);
            list.add(li);
        }
        int n1=sc.nextInt();
        int n2=sc.nextInt();
        
        List<Integer> list1=new ArrayList<>();
        List<Integer> list2=new ArrayList<>();
        for(int i=0;i<n;i++){
            if(i==n1 || i==n2){
                for(int x: list.get(i)){
                    funcall(x);
                }
                if(list1.isEmpty()){
                    list1.add(i);
                    for(int a:cycle){
                        list1.add(a);
                    }
                }
                else{
                    list2.add(i);
                    for(int a:cycle){
                        list2.add(a);
                    }
                }
                cycle.clear();
            }
        }
        boolean meet=false;
        System.out.println(list1);
        System.out.println(list2);
        for(int i=0;i<list1.size();i++){
            for(int j=0;j<list2.size();j++){
                if(list1.get(i)==list2.get(j)){
                    System.out.println(list1.get(i));
                    i=list1.size();
                    meet=true;
                    break;
                    
                }
            }
        }
        if(meet==false){
            System.out.println("No meeting cell");
        }
    }
    public static void funcall(int node){
        if(node==-1){
            return;
        }
        if(cycle.contains(node)){
            return;
        }
        else{
            cycle.add(node);
            
        }
        funcall(list.get(node).get(0));
    }
}

```
