Email id:vedantbhure2050@gmail.com
import java.util.*;
public class Life
{
	 public static void main(String args[])
	{
	int m,n;
	Scanner s=new Scanner(System.in);
	m=s.nextInt();
	n=s.nextInt();
	System.out.println(""+m);
	System.out.println( ""+n);
	int[][] grid;
	int i,j;
	grid=new int[m][n];
	for(i=0;i<m;i++)
	{
		for(j=0;j<n;j++)
		{
		System.out.println("Enter the grid elements");
		grid[i][j]=s.nextInt();	
		}
	}
	for(i=0;i<m;i++)
	{
		for(j=0;j<n;j++)
		{
	if(grid[i][j]==0)
	{
	System.out.println(" . ");
	}
	else
	{
	System.out.println(" * ");
	}
		}
System.out.println( );
	}
System.out.println( );
nextGeneration(grid, m, n);
}
		static void nextGeneration(int grid[][], int m, int n)
{
	int i,j;
	int[][]future=new int[m][n];
	for(int l=1;l<m-1;l++)
	{
		for(int k=1;k<n-1;k++)
		{
		int aliveNeighbours=0;
			for(i=-1;i<=1;i++)
			{
				for(j=-1;j<=1;j++)
				{
				aliveNeighbours +=grid[l+i][k+j];
				aliveNeighbours -=grid[l][k];
				}
			if((grid[l][k]==1)&&(aliveNeighbours<2))
			{
			future[l][k]=0;
			}
			else if((grid[l][k]==1)&&(aliveNeighbours>3))
			{
			future[l][k]=0;
			}
			else if((grid[l][k]==1)&&(aliveNeighbours==3))
			{
			future[l][k]=1;
			}
			else
			{
			future[l][k]=grid[l][k];
			}
		}
	}
System.out.println("Next Generation");
for(i=0;i<m;i++)
{	for(j=0;j<n;j++)
	{
		if(future[i][j]==0)
		{
			System.out.println(" . ");
		}
		else{
			System.out.println(" * ");
		}
	}
}
System.out.println( );		
}
	}
}
