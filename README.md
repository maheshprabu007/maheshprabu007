import java.io.*;
import java.net.*;

class Pingserver 
{
  public static void main(String args[])
  {
    try 
    {
      String str;
      System.out.println("enter the ip address to ping");
      BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
      String ip = br.readLine();
      Runtime H = Runtime.getRuntime();
      Process p = H.exec("ping" + ip);
      InputStream in = p.getInputStream();
      BufferedReader br2 = new BufferedReader(new InputStreamReader(in));
      while((str = br2.readLine())!=null)
      {
        System.out.println(str);
      }
     }
     catch(Exception e)
     {
        System.out.println(e.getMessage());
     }
  }
}
