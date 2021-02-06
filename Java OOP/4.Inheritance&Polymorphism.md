## 1. Inheritance

Trong `Java` các `attributes` và `methods` có thể kế thừa từ `class` khác.

Ở đây,chúng tôi gọi đó là `Inheritance`,  gồm 2 loại : 

- `subclass` (con) : *là `class` được kế thừa từ `class` khác*
- `superclass` (cha) : là `class` thừa kế

Ta sử dụng từ khoá `extends` để kế thừa từ một `class` : 

```java
class Animals(){
    protected String name = "mèo"; //thuộc tính
    public run(){ //phương thước
        System.out.println("Con vật đang chạy");
    }
}
class Dog extends Aminals{
    private String spec = "chó"; //thuộc tính
    public static void main(String[] args){
        Dog myDog = new Dog(); //tạo một object từ class Dog kế thừa từ Animals
        myDog.run(); //gọi phương thức run() từ class Dog kế thừa từ Animals
        System.out.println(myDog.name + " " + myDog.spec);
    }
}
/* Con vật đang chạy 
   mèo chó  */
```

> ⚠️ Hãy để ý ở lớp `Animals` tôi đã sử dụng `protected` để khai báo ==> Vì nếu 
> 
> - Đặt `private` thì lớp `Dog` sẽ không truy cập được
> - Đặt `public` thì không bảo đảm tính **an toàn** và **đóng gói**

#### ![Language Learningpng](https://raw.githubusercontent.com/Zenfection/Image/master/2021/02/02-14-14-12-Language%20Learning.png) Ôi, tôi không muốn kế thừa của ai hết, tôi cần làm sao ?

<details>
<summary><b><img src="https://raw.githubusercontent.com/Zenfection/Image/master/2021/02/01-13-25-05-Questions%20And%20Answers.png"> Trả lời</summary>

<br>

Sử dụng từ khoá `final` quốc dân thôi !!!

```java
final class Animals{
    //...
}
class Dog extends Animals{ // Dòng này sẽ lỗi ngay lập tức
    //...
}
```

> 💡 Nếu bạn cố gắng kế thừa lớp `Animals` thì sẽ lỗi ngay !!!

</details>

---

## 2. Polymorphism
