# Java_assignment

# Assignment class (Assignment.java)
package com.atcs.java;

public class Assignment {
	public static void main(String[] args) {
		CountLettersInArray obj = new CountLettersInArray();
		char st[]= obj.creatArraay();
		obj.displayArray(st);
		char st2[] = obj.unique(st);
		int count[] = obj.countChar(st2,st);
		obj.displayCount(count,st2);
	}
}

# CountLettersInArray Class (CountLettersInArray.java)
package com.atcs.java;
import java.util.Scanner;

public class CountLettersInArray {

	//Creating array and taking user inputs.
	public char[] creatArraay(){
		System.out.println("Enter amounts of letters you want to add : ");
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		sc.nextLine();
		char st[] = new char[n];
		//Taking random characters from users.
		for(int i = 0; i<n;i++){
			System.out.println("Enter here : ");
			char c = sc.next().charAt(0);
			st[i]= c;
		}
		return st;
	}
	
	// To display to user entered array.
	void displayArray(char st[]){
		int count =0;
		System.out.println("Elements you have entered are :-");
		for(int i = 0; i< st.length; i++,count++){
			if(count == 20){
				System.out.println();
				count=0;
			}
			System.out.print(st[i]+ "  ");
		}
	}

	// Function to find unique characters from the array
	public char[] unique(char st[]){
		char st2[] = new char[st.length];
		int index =0;
		for(int i =0;i < st.length; i++){
			int flag =0;
			for(int j =0 ;j<i;j++){
				if(st[i]== st2[j]){
					flag =1;
					break;
				}
			}
			if(flag == 0){
				st2[index] = st[i];
				index++;
			}
		}
		return st2;
	}
	
	// Function to find count of all unique characters.
	public int[] countChar(char st2[], char st[]){
		int count[]= new int[st2.length];
		for(int k = 0;k < st2.length;k++){
			int count_char=0;
			for(int l = 0 ; l < st.length; l++){
				if(st[l] == st2[k]){
					count_char++;
				}
			}
			count[k] = count_char;
		}
		return count;
	}
	
	
	// Function to display to counts.
	void displayCount(int count[], char st2[]){
		System.out.println("\nCount of every elements are :-");
		for(int i = 0;i < st2.length; i++){
			if(count[i] == 0){
				break;
			}
			System.out.println(st2[i]+ " : "+ count[i]);
		}
	}
	
}
