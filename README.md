# loopy_planet_project
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace Loopy_Planets_Console
{
    class Program
    {
        static void Main(string[] args)
        {                                    // names of planets and gravity constent of every one of them
            double mercuryMultiplier = 0.37;
            double venusMultiplier = 0.88;
            double marsMultiplier = 0.38;
            double jupiterMultiplier = 2.64;
            double saturnMultiplier = 1.15;
            double uranusMultiplier = 1.15;
            double neptuneMultiplier = 1.12;
            double plutoMultiplier = 0.04;
            String planetSelection = "";
            String weightEarth = "";
         
            while (planetSelection != "9")
            {
                try   //printing out the list of planets  
                {
                    Console.WriteLine("\n          Menu of Planets\n          ==== == =======");
                    Console.WriteLine("1. Jupiter    2. Mars     3. Mercury\n4. Neptune    5. Pluto    6. Saturn\n7. Uranus     8. Venus    9. <Quit>\n");
                    Console.Write("Enter your menu choice: ");
                    planetSelection = Console.ReadLine();
                    int planetChoiceInt = Convert.ToInt32(planetSelection);
                    if (planetChoiceInt == 9)
                    {
                        Console.WriteLine("Have a great day! Goodbye!");  
                        break;
                    }
                    else if (1 > planetChoiceInt || 9 < planetChoiceInt)
                    {
                        Console.WriteLine("Please enter an integer from 1-9 to make your selection."); // //Asking the User to input the Menu Choice listed above
 
                    }
                    else
                    {
                        Console.Write("Enter your weight on earth: ");
                        weightEarth = Console.ReadLine();
                        double weightNew = Convert.ToDouble(weightEarth); //Declare the function name for the weight
                        switch (planetSelection)
                        {
                            case "1":
                                weightNew *= jupiterMultiplier;
                                break;
                            case "2":
                                weightNew *= marsMultiplier;
                                break;
                            case "3":
                                weightNew *= mercuryMultiplier;
                                break;
                            case "4":
                                weightNew *= neptuneMultiplier;
                                break;
                            case "5":
                                weightNew *= plutoMultiplier;
                                break;
                            case "6":
                                weightNew *= saturnMultiplier;
                                break;
                            case "7":
                                weightNew *= uranusMultiplier;
                                break;
                            case "8":
                                weightNew *= venusMultiplier;
                                break;
                        }
                        String planet = "";
                        switch (planetSelection)
                        {
                            case "1":
                                planet = "Jupiter";
                                break;
                            case "2":
                                planet = "Mars";
                                break;
                            case "3":
                                planet = "Mercury";
                                break;
                            case "4":
                                planet = "Neptune";
                                break;
                            case "5":
                                planet = "Pluto";
                                break;
                            case "6":
                                planet = "Saturn";
                                break;
                            case "7":
                                planet = "Uranus";
                                break;
                            case "8":
                                planet = "Venus";
                                break;
                        }
                        Console.WriteLine("\nYour weight of " + weightEarth + " pounds on Earth would be " + weightNew.ToString("{0:0.#}") + " pounds on " + planet + ".");      //Print the result
                        }
                }
               
                catch (System.FormatException e)
                {
                    Console.WriteLine("Please enter an integer between 1-9 for menu choice or a float for your weight on Earth.");
                }
            }
        }
    }
}
