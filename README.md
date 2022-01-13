## Csharp

이 리포지토리는 Csharp에 대해 기술한 리포지토리입니다. <br />
이 리포지토리는 DevNcore팀이 관리하고 있습니다.  

<a href="https://github.com/devncore/devncore"><strong>더 알아보기 »</strong></a>
 
| Star | License | Activity |
|:----:|:-------:|:--------:|
| <a href="https://github.com/devncore/csharp/stargazers"><img src="https://img.shields.io/github/stars/devncore/csharp" alt="Github Stars"></a> | <img src="https://img.shields.io/github/license/devncore/csharp" alt="License"> | <a href="https://github.com/devncore/csharp/pulse"><img src="https://img.shields.io/github/commit-activity/m/devncore/csharp" alt="Commits-per-month"></a> |

<br />

## Contents
- [소개](#소개)
- [제네릭 (Generic)](#Generic)
- [WPF Template](#WPF Template)

<br />

## 소개
이 레포지토리는 **C#** 의 다양한 문법과 이를 다루는 방법에 대해 설명합니다.  

**C#은 닷넷을 포함한 다양한 환경에서 사용되는 언어입니다.**

- WPF
- Winform
- Xamarin
- .NET Core 
- MAUI
- WinUI 3
- Unity
- ASP.NET MVC
- Blazor
- Entity

<br />

## Generic
데이터 형식을 일반화한 메서드입니다. 일반 메서드 선언과 비슷하지만 일반화할 형식이 들어갈 자리에 형식 매개 변수가 들어갑니다.    

### GenericMethod 예제

```csharp
class Program
{
    static void Main(string[] args)
    {
        int a = 1;
        int b = 2;

        string c = "일";
        string d = "이";

        Swap<int>(ref a, ref b);
        Swap<string>(ref c, ref d);

        Console.WriteLine(a + " " + b);
        Console.WriteLine(c + " " + d);
    }

    static void Swap<T>(ref T lhs, ref T rhs)
    {
        T temp;
        // temp 변수에 a(1), c(일) 값을 담아둠
        temp = lhs;

        // a,c 변수에 b,d값 대입
        lhs = rhs;

        // b,d 변수에 a,c값 대입
        rhs = temp;
    }
}
```

![image](https://user-images.githubusercontent.com/68521148/135848199-851e71c8-7ebc-4991-9375-08f52c760f11.png)

> `T`는 타입 매개 변수입니다.    
> 메서드를 호출할 때는 T 대신 타입을 넣으면 컴파일러는 메서드의 나머지 부분에 대해서도 T를 타입 매개 변수값으로 치환합니다.

***

### GenericClass 예제

```csharp
class Program
{
    static void Main(string[] args)
    {
        MyStack<int> numberStack = new MyStack<int>();
        MyStack<string> nameStack = new MyStack<string>();

        numberStack.Push(100);
        nameStack.Push("백");
    }
}

class MyStack<T>
{
    T[] _elements;
    int pos = 0;

    public MyStack()
    {
        _elements = new T[10];
    }

    public void Push(T element)
    {
        _elements[++pos] = element;
        
        foreach(var item in _elements)
        {
            Console.WriteLine(item);
        }
    }

    public T Pop()
    {
        return _elements[pos--];
    }
}
```

![image](https://user-images.githubusercontent.com/68521148/135850480-96792a80-79a5-49ba-914a-94d2b0a820e1.png)

> 타입을 제외하면 소스코드는 동일하기 때문에  매개 변수를 이용해 제네릭 클래스로 구현할 수 있습니다.

<br />

## WPF Template
Template이란 이름에서도 알 수 있듯이 "틀"의 역할을 해줍니다. Template은 WPF Control의 껍데기 같은 개념입니다.

- **ControlTemplate**    
컨트롤의 컨텐츠가 아닌 컨트롤의 외관을 꾸밀 때 사용합니다
- **DataTemplate**    
컨트롤의 컨텐츠 부분을 스타일링합니다.
- **ItemsPanelTemplate**    
ComboBox, ListBox 등의 같은 OOOitems들을 여러 개 갖는 컨트롤의 레이아웃을 표현합니다.(아이템 )

