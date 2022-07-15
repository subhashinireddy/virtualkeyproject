# virtualkeyproject
package javafundamental;

import java.util.*;
import java.io.*;



public class LockedMe{
static final String projectPath="C:\\Users\\User\\eclipse-workspace\\COREJAVA\\src\\project1";
public static void main(String[] args) {
		
	Scanner obj = new Scanner(System.in);
	int ch;
	do {
		
		mainMenu();
	System.out.println("Enter your choice:");
	ch=Integer.parseInt(obj.nextLine());
		
	switch(ch)
	{
	
	case 1 :getAllFiles();
	          break;
	case 2:createFiles();
	        break;
	case 3:deleteFiles();
	        break;
	case 4:searchFiles();
	         break;
	case 5:  System.exit(0);
	          break;
	default: System.out.println("Invalid option");
	
		       break;
	}		
}
	
	while(ch>0);	

	
}
	
		public static void mainMenu()
		{
			
			System.out.println("*********************************  ");
			System.out.println(" Welcome Screen ");
			System.out.println(" Developer name :  SUBHASHINI REDDY ");
			System.out.println("********************************** ");
			System.out.println("1.Display all the files :");
			System.out.println("2. Add Files to existing directory");
			System.out.println("3. Delete a file");
			System.out.println("4. search a file");
			System.out.println("5. Exist");
			System.out.println("----------------------------------------- ");
		}
	
		public static void getAllFiles()
		{
			
			File[] listOfFiles = new File(projectPath).listFiles();
		
		if(listOfFiles.length==0)
			System.out.println("no files exist in the directory");
		else
		{
			
			for(File l: listOfFiles)
			{
				System.out.println(l.getName());
			}
		}	
		}
						
		
			public static void createFiles()
			{
				
				try
				{
				
					Scanner obj = new Scanner (System.in);
					String filename;
					int LinesCount;
					System.out.println("enter file name:");
					filename=obj.nextLine();
	
				System.out.println("Enter how many lines you want to add in file:");
				LinesCount=Integer.parseInt(obj.nextLine());
				
				
				FileWriter fw= new FileWriter(projectPath+"\\"+filename);
				for (int i=1;i<=LinesCount;i++)
				{
					System.out.println("enter file content line:");
					fw.write(obj.nextLine()+"\n");
				}
				System.out.println("File created sucessfully");
				fw.close();
				}
				catch(Exception e)
				{
					System.out.println("some error occured.");
			}
							}
			public static void deleteFiles()
			{
				
					Scanner obj=new Scanner(System.in);
					try 
					{
						String filename;
						System.out.println("enter file name to be deleted");
						filename=obj.nextLine();
						File F1=new File (projectPath+"\\"+filename);
						if(F1.exists())
						{
							F1.delete();
							System.out.println("file deleted");
						}
							else {
								System.out.println("file do not exist");
							}
						
								}
			catch(Exception e)
			{
				System.out.println("some error occured"); 	
			
			}
			}
			
			
			public static void searchFiles()
			{
				Scanner obj=new Scanner(System.in);
						try {
					
				
			
				LinkedList<String>filenames= new LinkedList<String>();
							String filename;
				System.out.println("enter the file name to be searched:");
			filename=obj.nextLine();
			File[] listofFiles = new File(projectPath).listFiles();
			for(File l:listofFiles)
			{filenames.add(l.getName());
						}
						if(filenames.contains(filename))
							System.out.println("file available");
						else
							System.out.println("file is not available");
						}
		catch(Exception e)
				{
			System.out.println("some error");
				}
			}
		}
		
		
