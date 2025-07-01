import javax.imageio.IIOException;
import java.io.*;

// Write a java program which read numbers from number.txt file and store
//even number to even.txt and odd number into odd.txt file
class pb320 {
    public static void main(String[] args) throws IOException {
        BufferedWriter b=new BufferedWriter(new FileWriter("num.txt"));
        BufferedReader r=new BufferedReader(new FileReader("num.txt"));
        BufferedWriter even=new BufferedWriter(new FileWriter("even.txt"));
        BufferedWriter odd=new BufferedWriter(new FileWriter("odd.txt"));
        b.write("1 2 3");
        b.newLine();
        b.write("4 5 6");
        b.flush();
        b.close();
        String line=r.readLine();
        while (line!=null){
            String[] s=line.split(" ");
            for (String s1: s){
                int num=Integer.parseInt(s1);
                if (num%2==0){
                    even.write(String.valueOf(num));
                }else {
                    odd.write(String.valueOf(num));
                }
            }
            line= r.readLine();
        }
        even.close();
        odd.close();
        r.close();
    }
}
