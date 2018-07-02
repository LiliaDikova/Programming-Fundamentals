using System;
using System.Text;
using System.Text.RegularExpressions;

namespace _04_CubicMessagess
{
    class Program
    {
        static void Main(string[] args)
        {
            string findMessage = @"^([0-9]+)(?<message>[a-zA-Z]+)([^a-zA-Z]*)$";
            string digits = @"\d";

            while (true)
            {
                string message = Console.ReadLine();

                if (message == "Over!")
                {
                    break;
                }

                int toEncrypt = int.Parse(Console.ReadLine());

                if (Regex.IsMatch(message, findMessage))
                {
                    string symbols = Regex.Match(message, findMessage).Groups["message"].Value;


                    if (symbols.Length == toEncrypt)
                    {
                        StringBuilder encrypted = EncryptMessage(digits, message, symbols);

                        Console.WriteLine($"{symbols} == {encrypted}");
                    }
                }
            }
        }

        private static StringBuilder EncryptMessage(string digits, string message, string symbols)
        {
            var encrypted = new StringBuilder();


            foreach (Match item in Regex.Matches(message, digits))
            {

                if (int.Parse(item.Value) >= 0 && int.Parse(item.Value) < symbols.Length)
                {
                    encrypted.Append(symbols[int.Parse(item.Value)]);
                }

                else
                {
                    encrypted.Append(' ');
                }

            }

            return encrypted;
        }
    }
}
