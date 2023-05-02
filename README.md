Download Link: https://assignmentchef.com/product/solved-coen174-lab-8
<br>
<strong>Part 1 </strong>




<strong>Testing with Junit Framework</strong>

JUnit is a unit testing framework for Java programming language and plays an important role in test-driven development. Using Junit, you will test the methods in a class to make sure that they work as expected.

In the exercises below, you will define a class with a few methods (<strong>C</strong>lass <strong>U</strong>nder <strong>T</strong>esting) and generate a Test class for the class under testing. In the Test class, a test method is generated for each of the methods to be tested in CUT. You will write the testing logic (in each of the testing methods) by calling assert methods. <strong>Assert</strong> is a method useful in determining Pass or Fail status of a test case. The <strong>assert</strong> methods are provided by the class <strong>org. junit</strong>. <strong>Assert</strong> which extends java. Object class.

For example, the method, <strong>Assertions. assertEquals()</strong> is used to assert that <strong>expected value from a method and actual value are equal</strong>. The method, <strong>assertEquals()</strong> has many overloaded methods for different data types e.g. int, long, float, String etc. It also supports passing error message to be printed in case test fails. e.g.

public static void <strong>assertEquals</strong>(int expected, int actual)

public static void <strong>assertEquals</strong>(int expected, int actual, String message)

public static void <strong>assertEquals</strong>(int expected, int actual, Supplier&lt;String&lt; messageSupplier)







<strong>Exercise 1 </strong>

<strong>Using JUnit with Eclipse</strong>

<strong>Step 1: </strong>

If you have not done it already, please download

<ul>

 <li><u>jar</u></li>

 <li>hamcrest-core.jar</li>

</ul>

from  <a href="https://github.com/junit-team/junit4/wiki/Download-and-Install">https://github.com/junit-team/junit4/wiki/Download-and-Install</a> and store them in a folder called junit.




<strong>Step 2: </strong>

Create a new Java project in Eclipse, called <strong>lab8testing</strong>.

<strong>Click on Project -&gt; Properties, select Java Build Path, Libraries, click Add</strong>

<ul>

 <li><strong>External JARs and browse to directory where you downloaded and saved the Junit jar file</strong><strong>s</strong>. Select <a href="https://search.maven.org/search?q=g:junit%20AND%20a:junit">jar</a> and <a href="https://search.maven.org/artifact/org.hamcrest/hamcrest-core/1.3/jar">hamcrest-core.jar</a></li>

</ul>

click Open. You will see both files will appear on your screen in the list of libraries. Click OK




Next, check to see what JRE System Library you are using (also viewable in the same libraries section). If it is not 1.8 then remove that library by clicking on it an clicking the “remove” button. Then click on “add library” -&gt; JRE System Library -&gt; Execution Environment  and select from the dropdown “JavaSE-1.8 (jre)” pictured below:

<strong> </strong>

<strong> </strong>

<strong> </strong>

You may need to remove the module declaration from module-info.java

<strong> </strong>

<strong>Step 3:</strong>

<strong>Create a package called lab8 under the project, lab8testing. Define a class, MyCalculator, to test:</strong>

public class <strong>MyCalculator</strong>  {

<strong>public</strong> <strong>int</strong> add(<strong>int</strong> i, <strong>int</strong> j) {

<strong>return</strong> i+j;

}




<strong>// You must write a subtract() and a multiply()</strong>

<strong>     // methods</strong>




<strong>public</strong> <strong>static</strong> <strong>void</strong> main(String[] args) {

// <strong>TODO</strong> Auto-generated method stub




}

}

Now, from your screen with MyCalculator class, click on <strong>FileNewJUnitTestCase</strong>.

You should see the screen below. Select New Junit 4 test (as shown) and click next.













Check the methods, add, subtract and multiply.

It may prompt you to choose to add Junit to Java build path. Choose ok.

Now, you should see a new class, called MyCalculatorTest generated. This class one test method for each of the methods in class MyCalculator.

For example, if you have a method called add in MyCalculator, you will have a method called testAdd() in MyCalculatorTest class.







<strong>import</strong> <strong>static</strong><strong> org.junit.Assert.*;</strong>

<strong>class</strong><strong> MyCalculatorTest {</strong>

<strong>     </strong><strong>@Test</strong>

<strong>     public </strong><strong>void</strong><strong> testAdd() {</strong>

<strong>          <em>fail</em>(</strong><strong>“Not yet implemented”</strong><strong>);</strong> <strong>// Remove this line</strong>

<strong>          // Add the following lines</strong>

<strong>          </strong><strong>MyCalculator </strong><strong>calculator</strong><strong> = </strong><strong>new</strong><strong> MyCalculator();</strong>

<strong> </strong>

<strong>          </strong><strong>int</strong> <strong>result</strong><strong> = </strong><strong>calculator</strong><strong>.add(100, 200);</strong>

<strong> </strong>

<strong>          </strong><strong>// compare the expected result with the actual </strong>

<strong> </strong>

<strong>          <em>assertEquals</em>(300,</strong><strong>result</strong><strong>);</strong>

<strong>     }</strong>

<strong>}</strong>










Now, while you are on MyCalculatorTest page, <strong>go to Run RunAs JUnitTest</strong>.

If there are no errors, you should see the screen below, where the green bar shows no errors.




Now change the number 300 in assertEquals(300,result) to 200. And Run RunAs JUnitTest.

What do you see?

The green bar turns red and indicates 1 failure. A failure trace is provided which shows that the assertion expected a value of 200, but the <em>result</em> was 300.

<strong>Exercise 2 :</strong>

Include the test code in testSubtract() and testMultiply as well and run them as Junit tests.

<strong>Exercise 3 </strong>

Now add two more methods, <strong>divide()</strong> and <strong>mod()</strong> in <strong>MyCalculator</strong>.  <strong>Note</strong>: Make sure that your code checks for division by 0. Generate test cases just like Exercises 1 and 2.

<strong> </strong>

<strong>Exercise 4 :</strong>

Create a package called <strong>lab8exer4</strong>. In this package, create a class called StringManager with the code below:

<strong>public</strong> <strong>class</strong> StringManager {




// checks if the given parameter is a palindrome (reads same when

// read in reverse




<strong>public</strong> <strong>boolean</strong> palindrome(String original) {




String lineInLowerCase = original.replaceAll(“\s+”, “”).toLowerCase();

StringBuffer line = <strong>new</strong> StringBuffer(lineInLowerCase);

StringBuffer reverse = line.reverse();

<strong>return</strong> (reverse.toString()).equals(lineInLowerCase);

}

// returns no. of words in a line of text




<strong>public</strong> <strong>int</strong> getNoOfWords(String lineOfText) {




String[] words = lineOfText.split(“\s+”) ;

<strong>return</strong> words.length;

}







<strong>public</strong> <strong>static</strong> <strong>void</strong> main(String[] args) {







}




}

Generate Testcases as you have done in the previous exercises.




References

<a href="https://www.javatpoint.com/junit-tutorial">Junit: A basic tutorial</a>










<strong>Part 2 </strong>

<strong> </strong>

In this part, you will create an executable jar file from the given code. The code shows a public MVCDemo class with several non-public classes in the same file (for convenience).

Create a package called lab8part2 and create class called MVCDemo in the package. Copy and paste the code given in <strong>MVCDemo.java</strong>.

Go to File -&gt; Java -&gt; runnable JAR file













Click Finish. You may see that the jar file is created with some warnings. Make sure you know the location of where the jar file is saved.




Now open the command window and cd to the folder where you saved the jar file.

From the command prompt, type

java -jar <em>name_of_jarfile</em>.jar

You should be able to see the following window.







Click on the buttons, IncreasePrice and ReducePrice and see the changes.




This is an example of an application showing the MVC architectural style. The GUI window has two areas where the price of the item is shown as text and with colors. The price of the item is increased or reduced using the buttons. The changes are shown in the two views.

What is the controller part in this window?

The controller part in this window is the “Increase Price” and “Reduce Price” buttons because they contain the control logic of the program