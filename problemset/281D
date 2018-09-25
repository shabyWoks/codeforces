import java.util.*;
import java.io.*;
import java.math.*;

public class Solution{
    static class Reader
    {
        final private int BUFFER_SIZE = 1 << 25;
        private DataInputStream din;
        private byte[] buffer;
        private int bufferPointer, bytesRead;
 
        public Reader()
        {
            din = new DataInputStream(System.in);
            buffer = new byte[BUFFER_SIZE];
            bufferPointer = bytesRead = 0;
        }
        private void fillBuffer() throws IOException
        {
            bytesRead = din.read(buffer, bufferPointer = 0, BUFFER_SIZE);
            if (bytesRead == -1)
                buffer[0] = -1;
        }
        public String readLine() throws IOException 
        { 
            byte[] buf = new byte[1280000]; // line length 
            int cnt = 0, c; 
            while ((c = read()) != -1) 
            { 
                if (c == '\n') 
                    break; 
                buf[cnt++] = (byte) c; 
            } 
            return new String(buf, 0, cnt); 
        } 
        private byte read() throws IOException
        {
            if (bufferPointer == bytesRead)
                fillBuffer();
            return buffer[bufferPointer++];
        }
        public int nextInt() throws IOException
        {
            int ret = 0;
            byte c = read();
            while (c <= ' ')
                c = read();
            boolean neg = (c == '-');
            if (neg)
                c = read();
            do
            {
                ret = ret * 10 + c - '0';
            }  while ((c = read()) >= '0' && c <= '9');
 
            if (neg)
                return -ret;
            return ret;
        }
    }
    
    public static void main(String[] argh) throws Exception{
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        // Reader br= new Reader();
        int n= Integer.parseInt(br.readLine().trim());
        int[] arr= new int[n];
        Stack<Integer> stack= new Stack<>();
        int max= 0;
        String[] li= br.readLine().trim().split(" ");
        for(int i=0; i<n; i++){
            arr[i]= Integer.parseInt(li[i]);
            if(i == 0) stack.push(arr[i]);
            else{
                while(true){
                    if(stack.size() == 0) {break;}
                    if(stack.peek() < arr[i]){
                        // do pairing
                        int elem1= stack.peek();
                        int elem2= arr[i];
                        int luckyNum = (elem1 ^ elem2);
                        if(luckyNum > max) {max= luckyNum;}
                        stack.pop();
                        
                    }
                    else{
                        // do pairing
                        int elem1= stack.peek();
                        int elem2= arr[i];
                        int luckyNum = (elem1 ^ elem2);
                        if(luckyNum > max) {max= luckyNum;}
                        break;
                    }
                }
                stack.push(arr[i]);
            }
        }
        System.out.println(max);
    }
}
