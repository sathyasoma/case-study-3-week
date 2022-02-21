# case-study-3-week


Create Product details Application:
===================================

1.Create a (Encapsulated class)Product class 
  
  properties:  
  
  product int id;
  product String name;
  product int amount;
  product int  code;
  product String  addrs;
  product int pincode;
											 
2. As a End user enter the customer details.
3. Use Database as HashMap to store the values.

Requiremnts	:
=============
End user enter by seeing this detials.

1. AddProduct 
2. updateProduct
3. deleteProduct
4. getProduct
5. getAllProducts								 
										 
										 
4. To add the product
    Enter  details to add product
	id
	name 
	amount 
	code 
	address 
	pincode 
5. what ever the values enter by the enduser stored in HashMap.




product class:
==============

package casestudy;

public class Product {

	private String pname; //
	private int pamount;
	private int pcode;
	private String paddrs;
	private int ppincode;
	public String getPname() {
		return pname;
	}
	public void setPname(String pname) {
		this.pname = pname;
	}
	public int getPamount() {
		return pamount;
	}
	public void setPamount(int pamount) {
		this.pamount = pamount;
	}
	public int getPcode() {
		return pcode;
	}
	public void setPcode(int pcode) {
		this.pcode = pcode;
	}
	public String getPaddrs() {
		return paddrs;
	}
	public void setPaddrs(String paddrs) {
		this.paddrs = paddrs;
	}
	public int getPpincode() {
		return ppincode;
	}
	public void setPpincode(int ppincode) {
		this.ppincode = ppincode;
	}
	
	public Product() {
		// TODO Auto-generated constructor stub
	}
	public Product(String pname, int pamount, int pcode, String paddrs, int ppincode) {
		super();
		this.pname = pname;
		this.pamount = pamount;
		this.pcode = pcode;
		this.paddrs = paddrs;
		this.ppincode = ppincode;
	}
	@Override
	public String toString() {
		return "Product [pname=" + pname + ", pamount=" + pamount + ", pcode=" + pcode + ", paddrs=" + paddrs
				+ ", ppincode=" + ppincode + "]";
	}
	
	
	
}






client class:
==============

package casestudy;

import java.util.HashMap;
import java.util.Iterator;
import java.util.Map.Entry;
import java.util.Scanner;
import java.util.Set;

public class Client {

	public static void main(String[] args) {
		
		HashMap<Integer,Product> product=new HashMap<Integer,Product>();
		
		int pid=100;
		
		while(true) {
			
			System.out.println("Product managemant Application");
			System.out.println("1.Add Product");
			System.out.println("2.Update Product");
			System.out.println("3.get Product");
			System.out.println("4.get all products");
			System.out.println("5.Delete Product");
			
			Scanner sc= new Scanner(System.in);
			
			int option=sc.nextInt();
			
			switch(option) {
			
			case 1:
				System.out.println("Enter to add product details");
				System.out.println("Enter product name");
				       String pname=sc.next();
				System.out.println("Enter product amount");
				       int pamount=sc.nextInt();
				System.out.println("Enter product code");
				     int pcode=sc.nextInt();
				System.out.println("Enter product address");
				       String padd=sc.next();
				System.out.println("Enter product pincode");
				     int ppincode=sc.nextInt();
				  
				 Product pd= new Product(pname, pamount, pcode, padd, ppincode);
				 
				 product.put(++pid, pd);
				 
				 System.out.println("product addedd succsfully :"+pid);
				     
				break;
           case 2:
        	   
        	   System.out.println("Enter to Update the product details");
        	   
        	   System.out.println("ENTER ID TO UPDATE");
        	              int pid1=sc.nextInt();
        	     System.out.println("Enter product name");
 				       String pname1=sc.next();
 				System.out.println("Enter product amount");
 				       int pamount1=sc.nextInt();
 				System.out.println("Enter product code");
 				     int pcode1=sc.nextInt();
 				System.out.println("Enter product address");
 				       String padd1=sc.next();
 				System.out.println("Enter product pincode");
 				     int ppincode1=sc.nextInt();
        	   
 				     Product pd1= new Product(pname1, pamount1, pcode1, padd1, ppincode1);
				
 				    		product.put(pid1, pd1);
 				     
 				     System.out.println("product updated suscfully :"+pid1);
				break;
           case 3:
        	   System.out.println("Enter id to get the product details");
        	      int pid2=sc.nextInt();
     
        	      Product pobj=product.get(pid2);
        	      System.out.println(pobj);
        	      
				break;
           case 4:
        	   Set<Entry<Integer,Product>> result=product.entrySet();
        	   Iterator<Entry<Integer,Product>> itr=result.iterator();
        	   
        	   while(itr.hasNext()) {
        		   Entry<Integer,Product> finalResult=itr.next();
        		   
        		   System.out.println(finalResult.getKey()+"  "+finalResult.getValue());
        		   
        	   }
				break;
           case 5:
        	   
        	   System.out.println("Enter id to delete product");
        	   int pid3= sc.nextInt();
        	   
        	   Product pobj1=product.remove(pid3);
        	   System.out.println("product deleted :"+pid3);
				
				break;
			
			
			default:
				System.out.println("wrong selection.....");
				
			
			}
			
			
		}
		
	}
}









































