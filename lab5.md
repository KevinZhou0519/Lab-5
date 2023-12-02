**Code Before**
*Sort.java*
````
import java.util.Arrays;
public class Sort {
    public static void sortA(int[] arr) {
        for(int i = 0; i < arr.length; i += 1) {
            //System.out.print(Arrays.toString(arr) + " -> ");
            int minIndex = i;
            for(int j = i; j < arr.length; j += 1) {
                if(arr[minIndex] < arr[j]) { minIndex = j; }
            }
            int temp = arr[i];
            arr[i] = arr[minIndex];
            arr[minIndex] = temp;
            //System.out.println(Arrays.toString(arr));
        }
    }
}
````
*SortTest.java*
````
import static org.junit.Assert.assertEquals;
import org.junit.Test;

public class SortTest {
    
    @Test
    public void sortTest(){
        int[] numArr = {0,0};
        int[] expArr = {0,0};
        Sort sortc = new Sort();
        sortc.sortA(numArr);
        assertEquals(expArr[0],numArr[0]);
    }

    @Test
    public void sortTest1(){
        int[] numArr = {1,0};
        int[] expArr = {0,1};
        Sort sortc = new Sort();
        sortc.sortA(numArr);
        assertEquals(expArr[0],numArr[0]);
    }

    @Test
    public void sortTest2(){
        int[] numArr = {4,6,9,2,6,2,3,6,9,1,0,4,6};
        int[] expArr = {0,1,2,2,3,4,4,6,6,6,6,9,9};
        Sort sortc = new Sort();
        sortc.sortA(numArr);
        assertEquals(expArr[0],numArr[0]);
    }
}

````
*test.sh*
````
javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.12.jar" *.java
java -cp ".;lib/junit-4.12.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore SortTest.java
````
