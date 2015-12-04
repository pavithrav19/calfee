import java.util.Scanner;

public class CalculateFee 
{

	static int examFees, applicationFees;
	
	private static int getApplicationFees(String nationality, String course)
	{
		if (nationality.equalsIgnoreCase("NRI") || nationality.equalsIgnoreCase("SAARC"))
		{
			return 0;
		}
		else if (nationality.equalsIgnoreCase("foreign"))
		{
			if (course.equalsIgnoreCase("UG") || course.equalsIgnoreCase("UG-DIPLOMA"))
			{
				return 400;
			}
			else
			{
				return 700;
			}
		}
		else
		{
			if (course.equalsIgnoreCase("UG"))
			{
				return 200;
			}
			else if (course.equalsIgnoreCase("UG-DIPLOMA"))
			{
				return 300;
			}
			else
			{
				return 500;
			}
		}
	}
	
	private static void calculateTotalFee(String nationality)
	{
		String course;
		String level;
		Scanner s = new Scanner(System.in);
		System.out.println("Select Course");
		System.out.println("1. Medical\n2. Dental\n3. Ayurveda");
		course = s.next();
		if (course.equalsIgnoreCase("Medical") || course.equalsIgnoreCase("Dental") || course.equalsIgnoreCase("Ayurveda"))
		{
			System.out.println("Select Level");
			System.out.println("1. UG\n2. UG-DIPLOMA\n3. PG");
			level = s.next();
			if (level.equalsIgnoreCase("UG"))
			{
				applicationFees = getApplicationFees(nationality, course);
			}
			else if (level.equalsIgnoreCase("UG-DIPLOMA"))
			{
				applicationFees = getApplicationFees(nationality, course);
			}
			else if (level.equalsIgnoreCase("PG"))
			{
				applicationFees = getApplicationFees(nationality, course);
			}
			else
			{
				System.out.println("Invalid course selected");
				System.exit(1);
			}
			System.out.println("Total fees = " + (applicationFees + examFees));
			System.out.println("(Exam fee = " + examFees + ", Application fee = " + applicationFees + ")");
		}
		else
		{
			System.out.println("Invalid course selected");
			System.exit(1);
		}
	}
	
	public static void main(String[] args) 
	{
		System.out.println("Enter Fees");
		System.out.println("1. 100\n2. 400\n3. 600");
		Scanner s = new Scanner(System.in);
		examFees = s.nextInt();
		String nationality;
		applicationFees = 0;
		if (examFees == 100)
		{
			System.out.println("Select Nationality");
			System.out.println("1. Foreign");
			nationality = s.next();
			if (nationality.equalsIgnoreCase("Foreign"))
			{
				calculateTotalFee(nationality);
			}
			else
			{
				System.out.println("Invalid nationality selected");
				System.exit(1);
			}			
		}
		else if (examFees == 400)
		{
			System.out.println("Select Nationality");
			System.out.println("1. Indian");
			nationality = s.next();
			if (nationality.equalsIgnoreCase("Indian"))
			{
				calculateTotalFee(nationality);
			}
			else
			{
				System.out.println("Invalid nationality selected");
				System.exit(1);
			}		
		}
		else if (examFees == 600)
		{
			System.out.println("Select Nationality");
			System.out.println("1. NRI\n2. SAARC");
			nationality = s.next();
			if (nationality.equalsIgnoreCase("NRI") || nationality.equalsIgnoreCase("SAARC"))
			{
				calculateTotalFee(nationality);
			}
			else
			{
				System.out.println("Invalid nationality selected");
				System.exit(1);
			}		
		}
		else
		{
			System.out.println("Invalid fee selected");
			System.exit(1);
		}
	}

}
