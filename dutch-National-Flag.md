
# Dutch National Flag Algorithm:

    This algorithm is used to segregate 0's, 1's and 2's together.


eg: Input  : [1,0,0,2,2,1,0,2,1,1]
    Output : [0,0,0,1,1,1,1,2,2,2]

*code*

```javascript
using System;
					
public class Program
{
	public static void Main()
	{
		int[] a = new int[]{2,2,2,0,1,2,0,1,2,1};
		DNF.segregate(a);
		DNF.display(a);
	}
}

public class DNF{	
	
	public static void segregate(int[] a)
	{
        if(a.Length > 2){
            int low = 0, mid = 0, high = a.Length-1;
            
            while(mid <= high){
                
                switch(a[mid])
                {
                case 0 : 
                    swap(a, low, mid);
                    low++;
                    mid++;
                    break;
                case 1 : 
                    mid++;
                    break;
                case 2: 
                    swap(a,mid,high);
                    high--;
                    break;
                }
            }

        }	
	}
	
	private static void swap(int[] a, int x, int y)
	{
		int temp = a[x];
		a[x] = a[y] ;
		a[y] = temp;
	}
	
	public static void display(int[] a)
	{
		
		foreach(int i in a)
			Console.Write(i + " ");
	}
}

```