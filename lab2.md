## Lab Report 2: Servers and Bugs

---

* # Part 1

> **Web Server: String Server**

Code:

![Image](Serverfilescreenshot1.png)
![Image](Serverfilescreenshot2.png)
![Image](StringServerfilescreenshot.png)


add-message requests:

![Image](request1.png)
![Image](request2.png)


The code starts in the StringServer class in the main method from where it creates an instance of the Server class from the Server.java file. An instance of the Handler class is sent to the server so that the Handler class we wrote in the StringServer.java file is used to handle requests such as "/add-message?s=xxx". The class returns the string text variable which is what is shown on the site
When the /add-message request is sent, the text variable is updated and sent back to display on the site updated with the addition of the parameter of the query.

---

* # Part 2

> **Bugs**

**Buggy Code**
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
**Failure-Inducing input in the form of JUnit test**
```
  @Test
  public void testReversedWithNonEmptyArray() {
    int[] input = {1,2,3,4};
    assertArrayEquals(new int[]{4,3,2,1}, ArrayExamples.reversed(input));
  }
```
**Input that doesn't induce a failure**
```
@Test
public void testReversedWithZeroArray() {
  int[] input = {0, 0, 0};
  assertArrayEquals(new int[]{0, 0, 0}, ArrayExamples.reversed(input));
}
```
**Symptom(result of JUnit tests)**
![Image](JUnittest.png)

**Bug(before-and-after)**
Before: 
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
After:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
This fix assigns the reversed values of the array passed as the argument to the new array created instead of doing the opposite like it was before

---

* # Part 3

> **Interesting topics or things I learned from lab in week 2 & 3**

Learning about secureshell and how to remotely access another computer from our own was definitely very fascinating and one of the more exciting things I've learned about. Learning how to launch a web server was also something that I enjoyed very much. 
Practing these topics in lab was very fun and taught me a lot of stuff I never knew before. 
