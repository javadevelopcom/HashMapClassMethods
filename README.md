# HashMapClassMethods
HashMap in Java with Example / Использование Map в Java
import java.util.HashMap;
import java.util.Map;

public class Main {

    public static void main(String[] args) {

        Map<String, Integer> map = new HashMap<>();

        map.put("key1", 100);
        map.put("key2", 100);
        map.put("key3", 100);
        map.put("key2", 200);
        map.put("key3", 300);
        print(map);
        mapStatus(map);
        println("Result of getting value (key3): " + map.get("key3"));
        println("Result of contains key (key2): " + map.containsValue("key2"));
        println("Result of contains value (300): " + map.containsValue(300));

        println("\n" + "KEYSET: ");
        map.keySet().forEach(System.out::println);

        println("\n" + "VALUES: ");
        map.values().forEach(System.out::println);

        println("\n" + "Result of REPLACE: ");
        map.replace("key1", 100, 1000);
        map.replace("key2", 100, 1000);
        map.replace("key3", 100, 1000);
        print(map);
        mapStatus(map);
        println("Result of getting value (key1): " + map.get("key1"));

        println("\n" + "Result of REPLACEALL: ");
        map.forEach((k, v) -> System.out.println(k + " " + v));
        map.replaceAll((k, v) -> 90);
        print(map);
        mapStatus(map);
        println("Result of getting value (key1): " + map.get("key1"));


        println("\n" + "Result of REMOVE (key1): ");
        println("Result of REMOVE (key2, 90): ");
        println("Result of REMOVE (key3, 100): ");
        map.remove("key1");
        map.remove("key2", 90);
        map.remove("key3", 100);
        print(map);
        mapStatus(map);
        println("Result of getting value (key1): " + map.get("key1"));


        println("\n" + "Result of CLEAR: ");
        map.clear();
        print(map);
        mapStatus(map);
        map.forEach((s, integer) -> System.out.println(s + " " + integer));
        println("Result of getting value (key1): " + map.get("key1"));


    }

    private static void println(String x) {
        System.out.println(x);
    }


    private static void print(Map<String, Integer> map) {
        System.out.println(map);
    }

    private static void mapStatus(Map<String, Integer> map) {
        println("Status of Map isEmpty: " + map.isEmpty());
    }
}
