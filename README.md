# GauravSharma_Lab2Algorithms
//contains solutions of the lab 2 assignment
// Question1
import java.util.Scanner;


public class SquareTransaction {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int N = in.nextInt();
        in.nextLine();
        long[] arr = new long[N];
        long[] runninSum = new long[N];
        for (int i = 0; i < N; i++) {
            arr[i] = in.nextLong();
            if (i == 0)
                runninSum[i] = arr[i];
            else
                runninSum[i] = runninSum[i - 1] + arr[i];
        }
        in.nextLine();
        long test = in.nextLong();
        for (long i = 0; i < test; i++) {
            long sum = in.nextLong();
            long index = squareTransaction(runninSum, sum);
            System.out.println(index);
//          in.nextLine();
        }
        in.close();
    }


    // linear search for get index
    private static long squareTransaction(long[] runninSum, long sum) {
        int index = 0;
        for (long i : runninSum) {
            index++;
            if (i >= sum)
                return index;


        }
        return -1;
    }
}

//Question 2
import java.util.*;
import java.io.*;

public class Main {
  public static void main(String args[]) throws IOException {
    Scanner sc = new Scanner(System.in);
    int t = sc.nextInt();
    while(t!=0)
    {
      int n = sc.nextInt();
      int arr[] = {1,2,5,10,20,50,100,500,1000};
      int note_count=0;
      for(int i=8;i>=0;i--)
      {
        if(arr[i]<=n)
        {
          note_count += n/arr[i];
          n %= arr[i];
        }
      }
      System.out.println(note_count);
      t--;
    }

  }
}
