## equals 와 hashCode 를 같이 정의해야하는 이유

hash 값을 사용하는 자료구조(ex.hashSet)은 hashCode 로 버킷을 찾고 같은 버킷 내에서 equals true/false가 나뉘는데

equals 를 override하여 비교 조건을 변경하였으면

hashCode도 같이 조건을 변경하여야 함

----

>예를 들어, equals 오버라이드로 email && category == true하도록 했으면 ?
hashcode도 동일하게 email && category 비교하도록 변경해야함.
```
public override int GetHashCode()
{
    return HashCode.Combine(Email, Category);
}

```

변경하지 않으면

hashCode가 오버라이드하지 않으면 기본(참조 기반) 해시가 반환되어, 값이 같아도 해시가 달라 다른 버킷에 들어가 equals 비교까지 가지 못할 수 있음.

따라서 중복일 경우 1개로 인식하는 hash인데, hashcode가 다르므로 2개로 인식

그래서 equals로 설정해서 hashcode 같게함


----
hash Set 은 컬렉션 클래스

HashSet은 해시 기반 자료구조로 원소를 중복 없이 저장 (내부적으로 해시 버킷/테이블 구조 사용)

---