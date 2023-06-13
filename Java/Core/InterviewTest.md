# Interview Test

## How to Maintain Insertion Order of the Elements in Java HashMap?
When elements get from the HashMap due to hashing the order they inserted is not maintained while retrieval. We can achieve the given task using LinkedHashMap. The LinkedHashMap class implements a doubly-linked list so that it can traverse through all the elements.  
```java
public static void main(String[] args) {
    HashMap<String, String> hm = new HashMap<>()
    hm.put("01", "aaaaaaa");
    hm.put("04", "kkkkkkk");
    hm.put("02", "bbbbbbb");
    hm.put("03", "ccccccc")
    for (Map.Entry<String, String> entry : hm.entrySet()) {
        System.out.println(entry.getKey() + "=>" + ":" + entry.getValue());
    }
}
//      01=>:aaaaaaa
//      02=>:bbbbbbb
//      03=>:ccccccc
//      04=>:kkkkkkk

```
```java
public static void main(String[] args) {
    HashMap<String, String> hm = new LinkedHashMap<>()
    hm.put("01", "aaaaaaa");
    hm.put("04", "kkkkkkk");
    hm.put("02", "bbbbbbb");
    hm.put("03", "ccccccc")
    for (Map.Entry<String, String> entry : hm.entrySet()) {
        System.out.println(entry.getKey() + "=>" + ":" + entry.getValue());
    }
}
//01=>:aaaaaaa
//04=>:kkkkkkk
//02=>:bbbbbbb
//03=>:ccccccc
```

## 5 Ways of Interator Map in Java
```java
// 1. Map.keySet and iterator
    public static void main(String[] args) {

        Map<String, String> map = new HashMap<>();

        map.put("01", "aaaaaaa");
        map.put("04", "kkkkkkk");
        map.put("02", "bbbbbbb");
        map.put("03", "ccccccc");

        Iterator<String> interator = map.keySet().iterator();
        while (interator.hasNext()) {
            String key = interator.next();
            String value = map.get(key);
            System.out.println("key = " + key + ", value = " + value);
        }
    }
//    key = 01, value = aaaaaaa
//    key = 02, value = bbbbbbb
//    key = 03, value = ccccccc
//    key = 04, value = kkkkkkk

// 2. Map.entrySet and iterator
    public static void main(String[] args) {
        Map<String, String> map = new HashMap<>();

        map.put("01", "aaaaaaa");
        map.put("04", "kkkkkkk");
        map.put("02", "bbbbbbb");
        map.put("03", "ccccccc");

        Iterator<Map.Entry<String, String>> entries = map.entrySet().iterator();
        while (entries.hasNext()) {
            Map.Entry<String, String> entry = entries.next();
            System.out.println(entry);
        }
    }
//01=aaaaaaa
//02=bbbbbbb
//03=ccccccc
//04=kkkkkkk

// 3. Map.keySet
    public static void main(String[] args) {
        Map<String, String> map = new HashMap<>();

        map.put("01", "aaaaaaa");
        map.put("04", "kkkkkkk");
        map.put("02", "bbbbbbb");
        map.put("03", "ccccccc");

        for (String key : map.keySet()) {
            System.out.println("key = " + key + ", value = " + map.get(key));
        }
    }
//    key = 01, value = aaaaaaa
//    key = 02, value = bbbbbbb
//    key = 03, value = ccccccc
//    key = 04, value = kkkkkkk

// 4. For-Each + Map.entrySet
    public static void main(String[] args) {
        Map<String, String> map = new HashMap<>();

        map.put("01", "aaaaaaa");
        map.put("04", "kkkkkkk");
        map.put("02", "bbbbbbb");
        map.put("03", "ccccccc");

        for (Map.Entry<String, String> entry : map.entrySet()) {
            System.out.println("key = " + entry.getKey() + ", value = " + entry.getValue());
        }
    }
//    key = 01, value = aaaaaaa
//    key = 02, value = bbbbbbb
//    key = 03, value = ccccccc
//    key = 04, value = kkkkkkk

// 5. lambda + For - Each
    public static void main(String[] args) {
        Map<String, String> map = new HashMap<>();

        map.put("01", "aaaaaaa");
        map.put("04", "kkkkkkk");
        map.put("02", "bbbbbbb");
        map.put("03", "ccccccc");

        map.forEach((k, v) -> System.out.println("key = " + k + ", value = " + v));
    }
//    key = 01, value = aaaaaaa
//    key = 02, value = bbbbbbb
//    key = 03, value = ccccccc
//    key = 04, value = kkkkkkk
```

## Sort array of integer
```java
// Arrays.sort()
    public static void main(String[] args) {
        int[] arr = { 5, -2, 23, 7, 87, -42, 509 };
        Arrays.sort(arr);
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
// -42 -2 5 7 23 87 509

// Collections.sort(list)
```

## Difference between session and cookies
Cookies and Sessions are used to store information. **Cookies** are only stored on the client-side machine, while **sessions** get stored on the client as well as the server.  
### What is a Cookie?
Cookies are little text-based files that are kept on the user's computer and are accessible only by that user's browser.  
When a person signs into a website or application for the very first time, that website transmits a large amount of information to the user's computer in the form of cookies.  
Cookies are created with the help of an HTTP header and then transferred between the browser and the server. Cookies are saved in the Temporal Internet File Folder by Internet Explorer, but the location where they are saved is determined by the browser being used. 
**Why use cookies**--Since HTTP is a stateless protocol, it does not save any information about users on its servers. Cookies are a useful tool for accomplish this goal.
### What is a Session?
Sessions are used to temporarily store data on the server so that it can be utilized on a varienty of different websites. To put it more simply, a session is the amount of time that a user spends engaged in a particular activity. This period of time begins when the user accesses any website or program and continues until the user exits the application or shuts down the computer.  
The data that is stored by session variables is either encrypted or converted to a binary form on the server, which protects the data from being accessed by a third party.  
**Why use sessions**--
Sessions are used to store information such as User ID over the server more securely, where it cannot be altered. This prevents the information from being tampered with.  
In addition to this, sessions can transfer the information from one web page to another in the form of value.  
Sessions can be used as a substitute for cookies in web browsers that do not support cookies, allowing for the storage of variables in a manner that is more impenetrable.
