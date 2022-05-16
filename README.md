# Leecode125
Palindrome program
package LeecodeProblem;

/*Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
*/
/*
Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.*/


import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Palindrome125 {
public static  boolean isPalindrome(String s)
{
	if(s.length()<=1)
	{
	  return true;	
	}
	String k="";
	Pattern p=Pattern.compile("[a-z0-9A-Z]");
	Matcher m=p.matcher(s);
	int check=0;
	while(m.find())
	{
	 k+=m.group();
	}
	k=k.toLowerCase();

	String res="";
	for(int i=k.length()-1;i>=0;i--)
	{
		res+=k.charAt(i);	
	}
	
	for(int j=0;j<k.length();j++)
	{
		if(k.charAt(j)==res.charAt(j))
		{
			check=1;
			
		}
		else
		{
			check=0;
			break;
		}
	}
	if(check==1)
	{
		return true;
	}
	return false;
}
public static void main(String[] args) {
	
	boolean c=isPalindrome("A man, a plan, a canal: Panama");
	System.out.println(c);
	
}
}
