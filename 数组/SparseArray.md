# 稀疏数组
```java
public class SparseArray {
    public static void main(String[] args) {
        int chessArr[][] = new int[11][11];
        chessArr[1][2] = 1;
        chessArr[2][3] = 2;
        chessArr[3][4] = 2;
        for (int[] row :  chessArr){
            for (int data:row){
                System.out.print("\t" +data);
            }
            System.out.println();
        }

        int sum = 0;
        for (int i = 0; i < 11; i++){
            for (int j = 0; j < 11; j++){
                if(chessArr[i][j] != 0){
                    sum++;
                }
            }
        }

        int sparseArr[][] = new int[sum + 1][3];
        sparseArr[0][0] = 11;
        sparseArr[0][1] = 11;
        sparseArr[0][2] = sum;
        int count = 0;
        for (int i = 0; i < 11; i++){
            for (int j = 0; j < 11; j++){
                if(chessArr[i][j] != 0){
                    count++;
                    sparseArr[count][0] = i;
                    sparseArr[count][1] = j;
                    sparseArr[count][2] = chessArr[i][j];
                }
            }
        }

        System.out.println();
        System.out.println("得到的稀疏数组为:");
        for (int i = 0; i < sparseArr.length; i++){

            System.out.printf("%d\t%d\t%d\t\n",sparseArr[i][0],sparseArr[i][1],sparseArr[i][2]);

        }
        System.out.println();

        //稀疏数组----> 原始数组

        int chessArr2[][] = new int[sparseArr[0][0]][sparseArr[0][1]];
        for (int i = 1; i < sparseArr.length; i++){
            chessArr2[sparseArr[i][0]][sparseArr[i][1]] = sparseArr[i][2];
        }
        System.out.println();
        System.out.println("恢复后的数组");
        for (int[] row :  chessArr2){
            for (int data:row){
                System.out.print("\t" +data);
            }
            System.out.println();
        }
    }
}
```