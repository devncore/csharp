<div align=center>
  <h2>Csharp</h2>
  <br/>
 
  이 레포지토리는 DevNcore팀이 관리하고 있습니다.
  <br />
  <a href="https://github.com/devncore/devncore"><strong>더 알아보기 »</strong></a>
 
  <br />
  <br />
 
  <p align="center">
   <a href="https://github.com/devncore/csharp/stargazers"><img src="https://img.shields.io/github/stars/devncore/csharp" alt="Github Stars"></a>
   <img src="https://img.shields.io/github/license/devncore/csharp" alt="License">
   <a href="https://github.com/devncore/csharp/pulse"><img src="https://img.shields.io/github/commit-activity/m/devncore/csharp" alt="Commits-per-month"></a>
 </p>
</div>

## _Csharp_
C# 문법, 메서드, WPF, Unity, Blazor, Entity등 다양한 내용을 정리할 레포지토리 입니다.    
정해진 주제, 순서, 두서없이 작성. 지속적으로 업데이트할 것입니다.

## Generic
데이터 형식을 일반화한 메서드입니다.    
일반 메서드 선언과 비슷하지만 일반화할 형식이 들어갈 자리에 형식 매개 변수가 들어갑니다.    

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

![image](https://user-images.githubusercontent.com/68521148/135847378-f6808a89-a0e0-4680-9932-d0fcd720a9a4.PNG)

> <T>는 타입 매개 변수입니다.    
> 메서드를 호출할 때는 T 대신 타입을 넣으면 컴파일러는 메서드의 나머지 부분에 대해서도 T를 타입 매개 변수값으로 치환합니다.    
