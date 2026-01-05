## Checked Exception과 Unchecked Exception
>public void readFile() throws IOException {
    FileInputStream fis = new FileInputStream("a.txt");
}

Java에서는 try-catch 또는 throws를 “강제”당하는 예외 = Checked Exception 이 있음.

C#에서는 모두 Unchecked Exception. 강제당하는 예외는 없음.

### Checked Exception은 컴파일 예외
### Unchecked Exception은 런타임 예외

즉, Java에서 Checked Exception을 유발하는 메서드를 호출하는 경우, 메서드 시그니처에 throws를 사용하여 호출자에게 예외를 위임하거나 메서드 내에서 try-catch를 사용하여 해당 예외를 반드시 처리해야한다.


Checked Exception은 외부 환경과의 상호작용에서 발생할 가능성이 높은 예외에 적합함.

예를 들어, 파일 입출력, 네트워크 통신 등에서 발생할 수 있는 예외는 Checked Exception으로 모두 처리하는 것이 좋음.

! 예외 처리 팁 
예외를 발생하는 경우 null, -1, 빈 문자열 등 특수값을 예외로 처리하지 말고 예외 Exception 처리해야 좋음. 
-> 오류 추적도 가능하고 어떤 문제인지 확인 가능.

문자열을 그냥 throw 로 던지는 것도 안 좋음. 
exception 객체로  
> throw new Error('유저 정보를 받아오는데 실패했습니다.'); 

던져야 예외인지 알 수 잇음. stack trace 자동 생성됨.
