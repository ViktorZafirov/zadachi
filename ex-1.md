ex-1.md
zadacha 1

public class ArraySumExample {
    public static void main(String[] args) {
        int[] array = {3, 5, 6, 2, 11};

        int sum = Sum(array);
        int evenSum = EvenSum(array);
        int oddSum = OddSum(array);

        System.out.println("Сума: " + sum);
        System.out.println("Четни: " + evenSum);
        System.out.println("Нечетни: " + oddSum);
    }

    public static int Sum(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            sum += num;
        }
        return sum;
    }

    public static int EvenSum(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            if (num % 2 == 0) {
                sum += num;
            }
        }
        return sum;
    }

    public static int OddSum(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            if (num % 2 != 0) {
                sum += num;
            }
        }
        return sum;
    }
}

zadacha 2
public class ReverseArrayExample {
    public static void main(String[] args) {
        int[] originalArray = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

        int[] reversedArray = reverseArray(originalArray);

        System.out.print("Изход: [");
        for (int i = 0; i < reversedArray.length; i++) {
            System.out.print(reversedArray[i]);
            if (i < reversedArray.length - 1) {
                System.out.print(", ");
            }
        }
        System.out.println("]");
    }

    public static int[] reverseArray(int[] arr) {
        int[] reversedArray = new int[arr.length];
        for (int i = 0; i < arr.length; i++) {
            reversedArray[i] = arr[arr.length - 1 - i];
        }
        return reversedArray;
    }
}


zadacha 3
public class MinMaxArray {
    public static void main(String[] args) {
        int[] array = {3, 1, 7, 5, 12};

        MinMax(array);
    }

    public static void MinMax(int[] arr) {
        if (arr.length == 0) {
            System.out.println("Масивът е празен.");
            return;
        }

        int min = arr[0];
        int max = arr[0];

        for (int i = 1; i < arr.length; i++) {
            if (arr[i] < min) {
                min = arr[i];
            }
            if (arr[i] > max) {
                max = arr[i];
            }
        }

        System.out.println("Макс: " + max);
        System.out.println("Мин: " + min);
    }
}

zadacha 4
public class PrimeNumberCheck {
    public static void main(String[] args) {
        int number = 7;
        boolean isPrime = isPrimeNumber(number);
        System.out.println("Изход: " + isPrime);
    }

    public static boolean isPrimeNumber(int num) {
        if (num <= 1) {
            return false;
        }

        
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false; 
            }
        }

        return true;
    }
}

zadacha 5
public class MatricaDiagonalSum {
    public static void main(String[] args) {
        int[][] matrica = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        int sumSusPovtarqne = sumSusPovtarqne(matrica);
        int sumBezPovtarqne = sumBezPovtarqne(matrica);

        System.out.println("Сума с повторение: " + sumSusPovtarqne);
        System.out.println("Сума без повторение: " + sumBezPovtarqne);
    }

    public static int sumSusPovtarqne(int[][] matrica) {
        int sum = 0;
        for (int i = 0; i < matrica.length; i++) {
            sum += matrica[i][i]; 
            sum += matrica[i][matrica.length - 1 - i]; 
        }
        return sum;
    }

    public static int sumBezPovtarqne(int[][] matrica) {
        int sum = 0;
        for (int i = 0; i < matrica.length; i++) {
            sum += matrica[i][i];
            if (i != matrica.length - 1 - i) {
                sum += matrica[i][matrica.length - 1 - i];
            }
        }
        return sum;
    }
}

zadacha 6

import java.util.Scanner;

public class Triangle {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Въведете височина на триъгълника: ");
        int n = scanner.nextInt();
        scanner.close();

        printTriangle(n);
    }

    public static void printTriangle(int height) {
        for (int i = 1; i <= height; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}

zadacha 7

import java.util.Arrays;
import java.util.Scanner;

public class KombiniranaPrograma {
    public static void main(String[] args) {
        int[] array = {3, 5, 6, 2, 11};
        int[] originalArray = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        int[] minMaxArray = {3, 1, 7, 5, 12};
        int number = 7;
        int[][] matrica = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        int sum = Sum(array);
        int evenSum = EvenSum(array);
        int oddSum = OddSum(array);
        int[] reversedArray = reverseArray(originalArray);
        int max = findMax(minMaxArray);
        int min = findMin(minMaxArray);
        boolean isPrime = isPrimeNumber(number);
        int diagonalSum = sumSusPovtorenie(matrica);

        System.out.println("Сума: " + sum);
        System.out.println("Четни: " + evenSum);
        System.out.println("Нечетни: " + oddSum);
        System.out.println("Обърнат: " + Arrays.toString(reversedArray));
        System.out.println("Макс: " + max);
        System.out.println("Мин: " + min);
        System.out.println("Просто: " + isPrime);
        System.out.println("Сума диагонали: " + diagonalSum);

        Scanner scanner = new Scanner(System.in);
        System.out.print("Въведете височина на триъгълника: ");
        int n = scanner.nextInt();
        scanner.close();

        printTriangle(n);
    }

    public static int Sum(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            sum += num;
        }
        return sum;
    }

    public static int EvenSum(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            if (num % 2 == 0) {
                sum += num;
            }
        }
        return sum;
    }

    public static int OddSum(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            if (num % 2 != 0) {
                sum += num;
            }
        }
        return sum;
    }

    public static int[] reverseArray(int[] arr) {
        int[] reversedArray = new int[arr.length];
        for (int i = 0; i < arr.length; i++) {
            reversedArray[i] = arr[arr.length - 1 - i];
        }
        return reversedArray;
    }

    public static int Max(int[] arr) {
        int max = arr[0];
        for (int num : arr) {
            if (num > max) {
                max = num;
            }
        }
        return max;
    }

    public static int Min(int[] arr) {
        int min = arr[0];
        for (int num : arr) {
            if (num < min) {
                min = num;
            }
        }
        return min;
    }

    public static boolean isPrimeNumber(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }

    public static int sumSusPovtorenie(int[][] matrica) {
        int sum = 0;
        for (int i = 0; i < matrica.length; i++) {
            sum += matrica[i][i];
            sum += matrica[i][matrica.length - 1 - i];
        }
        return sum;
    }

    public static void Triangle(int height) {
        for (int i = 1; i <= height; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}

Резултат от конзолата:
Сума: 27
Четни: 8
Нечетни: 19
Обърнат: [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
Макс: 12
Мин: 1
Просто: true
Сума диагонали: 30
Въведете височина на триъгълника: 5
* 
* * 
* * * 
* * * * 
* * * * * 
