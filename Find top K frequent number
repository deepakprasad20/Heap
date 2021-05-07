/**
 * Program to find top k frequent numbers.
 * */

import java.util.HashMap;
import java.util.Map;
import java.util.PriorityQueue;

public class HeapDemo {
    public static void main(String[] args){
        int[] arr = {1,1,2,2,2,2,2,2,1,3,3,1,3,4};
        int k = 2;
        findTopKFrequentNumber(arr,k);
    }

    private static void findTopKFrequentNumber(int[] arr, int k) {
        PriorityQueue<Entry> minheap = new PriorityQueue<>();
        Map<Integer,Integer> hm = new HashMap<>();
        for(int i = 0 ; i < arr.length ; i++){
            if(hm.containsKey(arr[i])){
                hm.put(arr[i],hm.get(arr[i])+1);
            } else{
                hm.put(arr[i],1);
            }
        }
        for(Map.Entry entry : hm.entrySet()){
            minheap.add(new Entry((int)entry.getValue(),(int)entry.getKey()));
            if(minheap.size() > k){
                minheap.poll();
            }
        }
        System.out.println("top "+ k + " frequent number are: ");
        while(minheap.size() > 0){
            System.out.print(minheap.peek().value + " ");
            minheap.poll();
        }
    }
}
class Entry implements Comparable<Entry>{
    int key;
    int value;

    public Entry(int key,int value){
        this.key = key;
        this.value = value;
    }

    public int getKey() {
        return key;
    }

    public void setKey(int key) {
        this.key = key;
    }

    public int getValue() {
        return value;
    }

    public void setValue(int value) {
        this.value = value;
    }

    @Override
    public int compareTo(Entry other) {
        return this.getKey() - other.getKey();
    }
}
