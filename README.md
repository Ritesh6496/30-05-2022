







using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace EmployeeData

{
    public class Menu
    {
        public string EmpName { get; set; }
        public string EmpNo { get; set; }
        public string EmpMoNo { get; set; }
        public string EmpCity { get; set; }
        public string EmpExp { get; set; }
        public void menu()
        {
            Console.WriteLine("1.Add new Employee");
            Console.WriteLine("2.Display All Employee");
            Console.WriteLine("3.Search Employee");
            Console.WriteLine("4.Remove Employee");
            Console.WriteLine("5.Exit");
        }
    }
    class Program
    {
        static void Main(string[] args)
        {

            List<Menu> EmpData = new List<Menu>();
            startconsole:
            Menu obj = new Menu();
            obj.menu();
            Console.Write("Enter Your Choice:");
            int Choice = Convert.ToInt32(Console.ReadLine());
            switch(Choice)
            {
                case 1:
                    Console.Write("Enter Employee Name:");
                    String Name = Console.ReadLine();
                    Console.Write("Enter Employee Number:");
                    string Number = Console.ReadLine();
                    Console.Write("Enter Employee City:");
                    string City = Console.ReadLine();
                    Console.Write("Enter Employee Phone No:");
                    string MoNo = Console.ReadLine();
                    Console.Write("Enter Employee Experiance in Year:");
                    string Exp = Console.ReadLine();
                    Console.WriteLine("Employee details added successfully");
                    EmpData.Add(new Menu
                    {
                       EmpName = Name,
                       EmpNo = Number,
                       EmpCity = City,
                       EmpExp  = Exp,
                       EmpMoNo = MoNo,
                    });
                    break;
                case 2:
                    if (EmpData.Count == 0)
                    {
                        Console.WriteLine("There is not any data in Employee List");
                    }
                    else
                    {
                        Console.WriteLine("Employee No \t  Name \t City \t Experiance \t Contact No");
                        Console.WriteLine("======================================================================");
                        foreach (Menu emp in EmpData)
                        {
                            
                            Console.WriteLine("  " + emp.EmpNo + "\t\t" + emp.EmpName + "\t  " + emp.EmpCity + "\t" + emp.EmpExp + "\t  " + emp.EmpMoNo);
                        }
                    }
                    break;
                case 3:
                    if (EmpData.Count == 0)
                    {
                        Console.WriteLine("There is no data for search");
                    }
                    else
                    {
                        Console.Write("Enter Employee Number For Search: ");
                        String SearchEmp = Console.ReadLine();
                        for (int i = 0; i < EmpData.(i); i++)
                        {
                            if (EmpData.get(i).name.equals(SearchEmp))
                            {
                                EmpData.remove(i);
                            }

                        }
                    }
                    break;

                case 4:
                    Console.Write("Enter employee name for Remove");
                    string RemoveEmp = Console.ReadLine();
                    if (EmpData.Contains(RemoveEmp))
                    {
                        EmpData.Remove(RemoveEmp);
                    }
                    break;

                case 5:
                    Environment.Exit(0);
                    break;
                default:
                    Console.WriteLine("Enter valid Choice:");
                    break;

            }
            Console.Write("Do You Want to Do any Other Operation(Y/N):");
            string userchoice = Console.ReadLine();
            if (userchoice == "y"||userchoice == "Y")
            {
                goto startconsole;
            }
            else
            {
                Environment.Exit(0);
            }

        }
    }
}
