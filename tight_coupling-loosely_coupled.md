## Tight Coupling là gì, loosely coupled là gì?

`Tight coupling ` ám chỉ việc thể hiện sự ràng buộc quá chặt chẽ giữa cách class.

`Loosely coupled` là một hướng tiếp cận làm sao cho sự ràng buộc quá chặt chẽ ở trên được dãn nở ra nhất có thể. 

Một số ví dụ bên dưới có thể giúp ta sẽ hiểu rõ hơn về bản chất của nó. 


`Normal approach`
```
// This class using for quicksort
class Quicksort{
    public void sort(int[] array){
    // TODO:  write code here
    }   
}
class ComposeClass{
    Quicksort quicksort = new Quicksort();
    public ComposeClass(){

    }
    public void complexBusiness(int[] array){
        quicksort.sort(array);
    }
}
```

`Better approach`
```
public interface sort(){
    public void sort(int[] array){}
}
class QuickSort implements sort(){

    @Override
    public void sort(int[] array){
        // TODO: write code here
    }
}
class ComposeClass{
    Sort sortAlg;
    public ComposeClass(){
        this.sortAlg = new QuickSort();
    }

    public void complexBusiness(int[] array){
        sortAlg.sort(array);
    }
}
```

`Popular approach`
```
public interface sort{
    public void sort(int[] array){}
}
class Quicksort implements sort{
    @Override
    public void sort(int [] array){
        // TODO
    }
}
class ComposeClass{
    Sort sortAlg;
    public ComposeClass(Sort sort){
        this.sortAlg = sort;
    }
    public void complexBusiness(int[] array){
        sortAlg.sort(array);
    }
}
```

 