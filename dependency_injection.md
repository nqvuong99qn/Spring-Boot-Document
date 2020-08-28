`Description`
Một cô gái đi chơi biển và hiển `bikini` là trang phục rất chủ đạo ki đi dạo biển. Bên cạnh đấy, cô ấy còn chuẩn bị thêm một số bộ `outfit` khác. 
 ## Hãy dùng class để biểu diễn minh hoạt cho ví dụ trên `!!!`

```java
class Girl{
    private Bikini outfit;
    public Girl(){
        outfit = new Bikini();
    }
}
``` 
>Cô gái chỉ có thể mặc bikini trong suốt chuyến đi chơi biển, mà không có sự lựa chọn nào khác. Với cách biểu diễn này cho thấy sự quá phụ thuộc rằng đi chơi biển phải mặc định rằng mặc bikini. Trong khi đó, một số cái khác, cá tính có phần khép nép hơn sẽ chọn những loại outfit kín đáo hơn. Vì vậy, cách biểu diễn này không được đánh giá cao lắm. 
```java
public interface Outfit{
    public void wear(String outfit){}
}

public Bikini implements Outfit{
    public void wear(String bikini){
        // TODO: wearing bikini

    }
}
class Girl{
    private Outfit outfit;
    public Girl(Outfit outfit){
        this.outfit = outfit;
    }
}

public class Main(){
    public static void main(String[] args){
        Outfit bikini = new Outfit();
        Girl girlxinh = new Girl(bikini);

    }
}
```
> Có thể thấy, lúc này, việc mô tả class như trên đã đáp ứng việc cô ấy là một bad girl hay là một traditional girl. 

`Ahihi quá thú vị đúng không nào !!! `
