## Collection



다수의 데이터를 쉽고 효과적으로 처리할 수 있는 표준화된 방법을 제공하는 클래스의 집합을 의미한다.



즉, 데이터를 저장하는 자료구조와 데이터를 처리하는 알고리즘을 구조화하여 클래스로 구현해놓은 것.



ex. List, Set, Map



## First-Class Collection



일급 컬렉션은 List<T> 같은 컬렉션을 노출시키지 않고 컬렉션을 감싼 클래스를 만드는 것


```
// 일급 컬렉션
public class Orders {

    private final List<Order> orders;

    public Orders(List<Order> orders) {
        validate(orders); // 검증 수행
        ...
    }


    public void add(Order order) {
        if (order == null) {
            throw new IllegalArgumentException("Order cannot be null");
        }

        orders.add(order);

    }

    public List<Order> getAll() {

        return Collections.unmodifiableList(orders);

    }

    public double getTotalAmount() {

        return orders.stream()

                     .mapToDouble(Order::getAmount)

                     .sum();

    }

}

```

