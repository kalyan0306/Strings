# Strings
class Launch
{
	public static void main(String[]args)
	{
		//[RULE--1]if a String is created directly using the string literal constant and without using the 'new'keyword then the memory for the string object is allocated in the 'String constant pool(scp)' region.

		String str=new String("GQT");
		System.out.println(str);

		//[RULE--2] If a string is created using the 'new'keyword, then the memory for the string object is allocated in the main heap area also, for every string literal in the program the JVM would create a string  object in the scp region and would maintain implicit references to the scp objects. 

		String st=new String("GQT");
		System.out.println(st);

		//[RULE--3] Duplicates are not permitted in the scp region.

		//example--1: 

		String str1="GQT";
		String str2="GQT";
		if(str1==str2)
		{
			System.out.println("string references are equal");
		}
		else
		{
			System.out.println("string references are not equal");
		}

		//example--2:

		String str3="GQT";
		String str4="GQT";
		if(str3.equals(str4))
		{
			System.out.println("string values are equal");
		}
		else
		{
			System.out.println("string values are not equal");
		}

		//example 3:

		String str5="GQT";
		String str6="gqt";
		if(str5.equalsIgnoreCase(str6))
		{
			System.out.println("string values are equal");
		}
		else
		{
			System.out.println("string values are not equal");
		}

		//[RULE--4]: Duplicates are permitted in main heap area.

		String str7=new String("GQT");
		String str8=new String("GQT");
		System.out.println(str7==str8);
		System.out.println(str7.equals(str8));

		//[RULE--5]: Every time 'new'keyword is used,A new string object is created in the heap area.

		//example--1:

		String str9="GQT";
		String str10=new String("GQT");//OR String str10=new String(str9);
		System.out.println(str9==str10);
		System.out.println(str9.equals(str10));

		//example--2:

		String str11= new String("GQT");
		String str12= new String("GQT");
		String str13="GQT";
		String str14="GQT";
		System.out.println(str11==str12);
		System.out.println(str13==str14);

		//[RULE--6]:In an assignment statement involvig two string variabels , the address present in the reference variabeles on the RHS is assigned to the variableon the LHS.

		//Example:1

		String str15="GQT";
		String str16="GQT";
		String str17;
		str17=str16;
		System.out.println(str17);

		//Example:2

		String str18=new String("GQT");
		String str19=new String("GQT");
		String str20;
		str20=str19;
		System.out.println(str19==str20);

		//[RULEl--7]:The concat() of the String class is used to concatinate Strings.concat() method will not modify the original Strings. Since they are immutabe, Hence the concatinated String will be created as anew object in the heap area.

		//Example:1

		String str21="GQT";
		String str22="IND";
		String str23=str21.concat(str22);
		System.out.println(str21);
		System.out.println(str22);
		System.out.println(str23);

		//Example:2

		String str24=new String("GQT");
		str24.concat("IND");
		System.out.println(str24);
		str24=str24.concat("TECH");
		System.out.println(str24);

		//Example:3

		String str25=new String("QGT");
		str25.concat("IND");
		String str26=str25.concat("TECH");
		str25=str26.concat("JAVA");
		System.out.println(str25);
		System.out.println(str26);
		
		//Example:4

		String str27=new String("ABCDEF");
		String str28=new String("ABC");
		String str29=str28.concat("DEF");
		System.out.println(str2==str28);
		String str30="ABCDEF".concat("GHI");
		str30.concat("JKL");
		str28="MNO".concat(str28);
		System.out.println(str27);
		System.out.println(str28);

		//[RULE--8]:Strings are more commenly concatinated with the'+' operater.

		//Example:1

		String str31="GQTIND";
		String str32="GQT"+"IND";
		String str33="GQT"+"IND";
		String str34="GQT".concat("IND");
		System.out.println(str31==str32);
		System.out.println(str31==str33);
		System.out.println(str31==str34);

		//Example:2

		//if the '+' operator is applied between Two String variables (str31,str32...) then the concatination would be performed during runtime.

		String str35="GQT";
		String str36="IND";
		String str37=str35+str36;
		String str38=str35+str36;
		System.out.println(str37==str38);

		//Example:3	

		String str39="GQTIND";
		String str40="GQT";
		String str41=str40+"IND";
		System.out.println(str39==str41);
		
		//Example:4

		//Even if there is one String variable  involved during concatination, the resultant Srting will bbe resolved during runtime.Hence ,memory will be allocatred in heap area.

		String str42=new String("GQT");
		str42=str42+"IND";
		System.out.println(str42);

		//Example:5

		String str43="ABC";
		String str44="XYZ"+"MNO"+str43+"ABC"+"DEF";
		System.out.println("HELLOWORLD");
		System.out.println(str44);

		//[RULE--9]:If any one of the operends is a String then all other operands are converted/casted toString before concatination.

		//Example:1

		String str45="GQT";
		String str46=str45+99;
		String str47=99+str45;
		//String str48=99+999;//int cannot be converted into String
		String str49=str45+99+999;
		String str50=99+999+str45;
		System.out.println(str45);
		System.out.println(str46);
		System.out.println(str47);
		//System.out.println(str48);
		System.out.println(str49);
		System.out.println(str50);

		//[RULE--10]: When final string variables are used as operends then the resultant String will be evaluating during the compile time itself.

		//Example:1

		final String str51="GQT";
		//str51="IND";
		String str52=str51+"TECH";
		System.out.println(str52);

		//Example:2
		String str53="GQT";
		str53="IND";
		String str54=str53+"TECH";
		System.out.println(str54);

	}
}
