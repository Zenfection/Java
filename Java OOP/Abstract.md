## 

## 1. Abstract

`Data Abstact` (*trừu tượng dữ liệu*) có nghĩa là ẩn một số chi tiết nhất định và hiển thị những thứ cần thiết cho người dùng.

> 💡 Hiểu đơn giản thì bạn gọi một món ăn thì bạn không cần phải biết quy trình nấu ăn, công thức nấu... chỉ cần ăn thôi. 

Từ khoá `abstract` là một `non-access modifier` bạn đã học trong bài [Phạm vi truy cập](https://github.com/Zenfection/Java/blob/master/Java%20OOP/2.Modifier.md) , sử dụng cho `classes` và `methods` : 

- `Abstract class` : đây là một `class` không được sử dụng để tạo `Object` (*nó chỉ dùng để kế thừa*).
- `Abstact method` : có thể sử dụng trong `Abstract class` và không có phần `body` (*phần `body` được cung cấp bởi `subclass` hoặc kế thừa từ nó*).

```java
abstract class Animal {
    public abstract void animalSound();
    public void sleep() {
        System.out.println("Zzz");
    }
}
```

> ⚠️ Không thể tạo `Object` từ một lớp `Abstract` như sau : 
> 
> ```java
> Animal myObj = new Animal(); // sẽ lỗi
> ```

### ![Language Learningpng](https://raw.githubusercontent.com/Zenfection/Image/master/2021/02/02-14-14-12-Language%20Learning.png) Để truy cập vào `abstract class`, thì ta phải làm sao ?

<details>
<summary><b><img src="https://raw.githubusercontent.com/Zenfection/Image/master/2021/02/01-13-25-05-Questions%20And%20Answers.png"> Trả lời</summary>

<br>

Nó phải được kế thừa từ `class` khác. Hãy đổi lớp `Animal` mà ta sử udng5 

```java
//khai báo lớp abstract
abstract class Animal{
    public abstract void animalSound();
    public void sleep(){
        System.out.println("Zzz");
    }
}
//khai báo subclass (kế thừa từ lớp Animal)
class Cat extends Animal{
    public void animalSound(){
        System.out.println("Con mèo kêu : mèo méo meo");
    }
}

class Main{
    public static void main(String[] args){
        Cat myCat = new Cat();
        myCat.animalSound();
        myCat.sleep();
    }
}
/* Con mèo kêu : mèo méo meo
   Zzz  */
```

> 💡 Như bạn đã thấy, `abstract class` chỉ cho phép kế thừa nó, và ta sử dụng thôi, dễ mà !!!

</details>

> 🚀 Ta sử dụng tính `Abstract` (*trừu tượng*) để : 
> - Bảo đảm tính **bảo mật** (*ẩn các chi tiết quan trọng và chỉ hiển thị thứ cần thiết*) 
> - 