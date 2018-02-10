# Quick Sort logic
```
using System;

public class program
{
	public static void Main()
	{
		//int[] a = {50,45,20,60,74,83,43,68,85,10,89,71};
		int[] a = {85,30,65,28,15,46,23,59,37};
		SortClass s = new SortClass();		
		s.Sort(a, a.Length);
		
		foreach(int i in a)
		{
			Console.Write(i + " ");
		}
		
	}
}

public class SortClass
{
	public void Sort(int[] a, int n)
	{
		Sort(a,0,n - 1);
	}
	public static void Sort(int[] a, int start, int end)
	{
		
		if(start >= end)
			return;
		
		int p = partition(a, start, end);
		
		Sort(a,start,p-1);
		
		Sort(a,p+1, end);
		
		
	}
	
	private static int partition(int[] a, int low, int up)
	{
		
		int i = low+1;
		int j = up;
		int pivot = a[low];
		
		while(i <= j)
		{
			while(a[i] < pivot && i < up)
			{				
				i++;
			}
			
			while(a[j] > pivot)
			{				
				j--;
			}
			if( i < j)
			{				
				int temp = a[i];
				a[i] = a[j];
				a[j] = temp;
				i++;
				j--;
			}
			else
				break;
			
		}
			a[low] = a[j];
			a[j] = pivot;
		
		
		
		return j;
	}
}
```
