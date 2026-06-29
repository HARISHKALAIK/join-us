# Answers

## About You

### 1. Introduce yourself.

Hello,

My name is **Harish K**. I am a Java Full Stack Developer with over one year of professional experience in developing web applications. I have experience working with Java, Spring Boot, React.js, JavaScript, Node.js, MySQL, MongoDB, REST APIs, Git, and GitHub.

I enjoy solving problems, learning new technologies, and building scalable applications. I am always interested in contributing to open-source projects and improving my development skills.

---

### 2. Do you own a personal computer?

Yes, I own a personal computer.

---

### 3. Describe your development environment.

**Operating System**
- Windows 11

**IDE**
- IntelliJ IDEA
- Visual Studio Code

**Version Control**
- Git & GitHub

**Database Tools**
- MySQL Workbench
- MongoDB Compass
- pgAdmin

**API Testing**
- Postman

---

# Social Profile

### 1. StackOverflow Profile URL

Currently, I do not have a StackOverflow profile.

---

### 2. Personal Website / Blog

GitHub:
https://github.com/HARISHKALAIK

Portfolio:
https://harish-portfolio-beige.vercel.app/

---

# The Real Stuff

## 1. Which programming languages are installed on your system?

- Java
- JavaScript
- Python
- SQL
- HTML
- CSS

---

## 2. Write a function that takes a number and returns a list of its digits in an array.

```java
import java.util.*;

public class Digits {

    public static int[] getDigits(int number) {

        String str = Integer.toString(number);

        int[] digits = new int[str.length()];

        for(int i = 0; i < str.length(); i++) {
            digits[i] = str.charAt(i) - '0';
        }

        return digits;
    }

    public static void main(String[] args) {

        int[] result = getDigits(123456);

        System.out.println(Arrays.toString(result));
    }
}
```

Output

```
[1, 2, 3, 4, 5, 6]
```

---

## 3. Remove duplicates from an array and return unique elements.

```java
import java.util.*;

public class RemoveDuplicates {

    public static int[] unique(int[] arr) {

        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        for(int num : arr) {
            set.add(num);
        }

        int[] result = new int[set.size()];

        int i = 0;

        for(int num : set) {
            result[i++] = num;
        }

        return result;
    }

    public static void main(String[] args) {

        int[] arr = {1,2,2,3,4,4,5,6,6};

        System.out.println(Arrays.toString(unique(arr)));
    }
}
```

Output

```
[1, 2, 3, 4, 5, 6]
```

---

## 4. Translate a text to Pig Latin and back.

```java
public class PigLatin {

    public static String toPigLatin(String text) {

        String[] words = text.split(" ");

        StringBuilder sb = new StringBuilder();

        for(String word : words) {

            sb.append(word.substring(1))
              .append(word.charAt(0))
              .append("ay ");

        }

        return sb.toString().trim();
    }

    public static String fromPigLatin(String text) {

        String[] words = text.split(" ");

        StringBuilder sb = new StringBuilder();

        for(String word : words) {

            String temp = word.substring(0, word.length()-2);

            sb.append(temp.charAt(temp.length()-1))
              .append(temp.substring(0,temp.length()-1))
              .append(" ");
        }

        return sb.toString().trim();
    }

    public static void main(String[] args) {

        String sentence = "The quick brown fox";

        String pig = toPigLatin(sentence);

        System.out.println("Pig Latin : " + pig);

        System.out.println("English : " + fromPigLatin(pig));
    }
}
```

Output

```
Pig Latin : heTay uickqay rownbay oxfay
English : The quick brown fox
```

---

## 5. Rotate a list by `k` elements without creating another list.

```java
import java.util.*;

public class RotateArray {

    static void reverse(int[] arr, int left, int right) {

        while(left < right) {

            int temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;

            left++;
            right--;
        }
    }

    static void rotate(int[] arr, int k) {

        int n = arr.length;

        k = k % n;

        reverse(arr, 0, k - 1);
        reverse(arr, k, n - 1);
        reverse(arr, 0, n - 1);
    }

    public static void main(String[] args) {

        int[] arr = {1,2,3,4,5,6};

        rotate(arr, 2);

        System.out.println(Arrays.toString(arr));
    }
}
```

Output

```
[3, 4, 5, 6, 1, 2]
```

### Complexity

- Time Complexity: **O(n)**
- Space Complexity: **O(1)**

The rotation is performed **in-place** using the reversal algorithm. It requires approximately **n swaps** and does not create another copy of the array.

---

## Thank You

Thank you for reviewing my submission. I enjoyed solving these problems and appreciate the opportunity to participate in this hiring exercise.