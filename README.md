# jk1602_jys2
//This is the Java code from jys.

import java.util.Scanner;

public class Main {
	double x,y;
	Main(double x,double y)
	{
		this.x = x;
		this.y = y;
	}
	double jl(Main d)
	{
		return Math.sqrt(Math.pow(x-d.x, 2)+Math.pow(y-d.y, 2));
	}
	public static void main(String[] args) {
		Scanner reader = new Scanner(System.in);
		while(reader.hasNext())
		{
			int n = reader.nextInt();
			int r = reader.nextInt();
			double x = reader.nextDouble();
			double y = reader.nextDouble();
			Main t = new Main(x,y);
			Main t1 = t;
			double z = 0;
			for(int i = 2;i <= n;i++)
			{
				Main d = new Main(reader.nextDouble(),reader.nextDouble());
				z = z+t.jl(d);
				t = d;
			}
			z = z+t1.jl(t);
			z = z+2*3.1415926*r;
			System.out.println(String.format("%.2f", z));
		}
        reader.close();
	}

}

