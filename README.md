# Matrix
import java.util.Scanner;

public class FilltheMatrix01 {


    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String[] input = scanner.nextLine().split(", ");
        int n = Integer.parseInt(input[0]);
        String patern = input[1];
        int counter = 1;

        int[][] matrix = new int[n][n];
        if (patern.equals("A")) {
            fillMatrixPaternA(n, matrix, counter);

        } else {
            fillMatrixPaternB(n, matrix, counter);
        }



            printMatrix(n, matrix);


        }

        private static void fillMatrixPaternB ( int n, int[][] matrix, int counter){
            for (int col = 0; col < n; col++) {
                if (col % 2 == 0) { // even
                    for (int row = 0; row < n; row++) {
                        matrix[row][col] = counter;
                        counter++;
                    }
                } else {

                    for (int row = n - 1; row >= 0; row--) {
                        matrix[row][col] = counter;
                        counter++;
                    }
                }
            }
        }

        private static void fillMatrixPaternA ( int n, int[][] matrix, int counter){
            for (int col = 0; col < n; col++) {
                for (int row = 0; row < n; row++) {
                    matrix[row][col] = counter;
                    counter++;
                }
            }
        }

        private static void printMatrix ( int n, int[][] matrix){
            for (int row = 0; row < n; row++) {
                for (int col = 0; col < n; col++) {
                    System.out.print(matrix[row][col] + " ");
                }
                System.out.println();
            }
        }
    }


