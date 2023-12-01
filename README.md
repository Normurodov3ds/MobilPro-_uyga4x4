# MobilPro-_uyga4x4
import java.util.Arrays;
import java.util.Random;
import java.util.Scanner;

public class letkode {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int a = in.nextInt(); // (a > n katta aks holda keksiz sikil paydo bo'adi!)
        int[] myarray = arrayRands(n, a);

        System.out.println(Arrays.toString(myarray));
        arrayMinMax(myarray);
        System.out.println("Juftlar => "+even_numbers(myarray));
        arraSum(myarray);
    }

    public static int[] arrayRands(int n, int a) {
        Random rand = new Random();
        int[] arr = new int[n];
        // 1 va a oraliqda sonlarni takrorlanish
        for (int i = 0; i < n; i++) {      // siz geniratsiya qiladi
            arr[i] = rand.nextInt(a) + 1;
            for (int j = 0; j < i; j++) {
                if (arr[i] == arr[j]) {
                    i--;
                    break;
                }
            }
        }
        return arr;
    }

    public static void arrayMinMax(int[] myArray) {  // min max qiymatni ekranga chiqaradi
        int max = myArray[0];
        int min = max;
        for (int i = 1; i < myArray.length; i++) {
            if (myArray[i] > max) {
                max = myArray[i];
            }
            if (myArray[i] < min) {
                min = myArray[i];
            }
        }
        System.out.println("MIN = " + min);
        System.out.println("MAX = " + max);

    }

    public static int even_numbers(int[] myarray) { // juft sonlar sonini qaytaradi
        short count = 0;
        for (int i = 0; i < myarray.length; i++) {
            if (myarray[i] % 2 == 0 && myarray[i] != 0) {
                count++;
            }
        }
        return count;
    }

    public static void arraSum(int[] myarray) {
        int sum = 0;        // myarray sum elementlar yig'indisi
        for (int i : myarray) {
            sum += i;
        }
        System.out.println("sum => " + sum);
    }
}

