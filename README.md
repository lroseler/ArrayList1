# ArrayList1

The purpose of this program is to build an ArrayList, that is it will create a structure that can accept an Object and store it in a way that will make it possible to add, remove, or find the added objects. The solution is to initially use a basic array and fill the array with generic objects, type casting them as they are added. 


public class ArrayList<T> {
	int size =52;						
	Object[] objArray = new Object[size];   
	int length = objArray.length -1;  	    
	int items =0;  					
	T genericObject; 						
	
	public ArrayList()  //an empty constructor with the size set to 10 
	{
		this.size = 10;
		
	}
	public ArrayList(Object o) //a constructor that accepts the type of object 
	{
		
		o = (T) genericObject; //casting the input object to generic
	}
	public ArrayList(int n) //a constructor that accepts a variable to set the initial size
	{
		this.size = n;
	}
	public void add(Object x)   //this method will add the inserted object to the end of the array
	{							//the expected output is the object will be added
		x = (T) genericObject;
		objArray[length-1] = x; //if the size is smaller than needed it will increase the array by 10
		if(objArray.length -1 > size)
		{
			size = size + 10;
		}
		items++; //this increases the item count by one
	}
	public void add(int index, Object x) //this method should insert the object at a specified index
	{
		x = (T) genericObject;
		objArray[index] =x;
		if(objArray.length -1 > size) //if the array size is too small it will increase the size by 10
		{
			size = size + 10;
			objArray[index] = x;
		}
		items++; //this increases the item count by one
	}
	public Object get(int index) //this method should return the object at the given array
	{
		return objArray[index];
	}
	public int size() //this method is for the current number of items in the array
	{
		return items;
	}
	public boolean isEmpty() //this method should report if there are no items in the array
	{
		if(items == 0)
		{
			return true; //if the item count is zero it will return true
		}
		else
		{
			return false; //otherwise, there are items in the array and the array is not empty and should return false
		}
	}
	public boolean isIn(Object ob) //this will find if an object is in the array
	{
		boolean result = false;
		for(int i = 0; i < objArray.length; i++) //it loops through the entire array
		{
			if(ob == objArray[i])
			{
				result = true; //if the object i present it should return true
			}
		
			else
			{
				result = false ; //otherwise the item is not present and should return false
			}
		}
		return result;
	}
	public int find(Object ob) //this will find a specified object and return the index it is at
	{
		int result = 0;
		for(int i = 0; i < objArray.length; i++) //looping through the entire array
		{
			if(ob == objArray[i])
			{
				result = i;
			}
			else
			{
				result = -1; //if the object is not present it returns -1
			}
		}
		return result;
	}
	
	public void remove(Object n) //removes a specified object
	{
		for(int i = 0; i < objArray.length-1; i++)
		{
			if(n == objArray[i]) //if the object is found
			{
				objArray[i] = objArray[i+1]; //it will replace the previous index with the next one
				length--; //then decrease the total array size
			}
		
			else if(n != objArray[i])
			{
				System.out.println("Object does not exist"); //unless the object is not found at all
			}
		}
	}
	public void shuffle() //a shuffle method that loops through the array 20 times replacing 
	{					  //every 3rd index with the previous
		int count = 20;
		while(count != 0)
		{
		for(int i = 0; i < objArray.length -1; i++)
		{
			for(int j = (i+3); j <objArray.length -2; j++ )
			{
				Object temp;
				temp = objArray[i];
				objArray[i] = objArray[j];
				objArray[j] = temp;
				
			}
		}
		count--;
		}
	}
	
	}


