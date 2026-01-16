## annotation and attribute
C#에서는 annotation이 아니라 attribute 사용함.
>[Obsolete("이 메서드는 더 이상 사용하지 마세요")] 형태

reflection 기술을 이용하여 런타임 시에 attribute 설정한 걸 확인함.

프레임워크가 공통으로 처리하게 됨.

`ex. `[Required]`, `[MaxLength]` attribute를 사용해 maxlength를 제어하여 exception 발생`