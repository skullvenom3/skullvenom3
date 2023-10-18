using System;
using System.Collections.Generic;
using System.Linq;

namespace ConsoleApp8
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Dictionary<string, Tuple<long, double>> depot = new Dictionary<string, Tuple<long, double>>();

            string[] names = Console.ReadLine().Split();
            double[] prices = Console.ReadLine().Split().Select(double.Parse).ToArray();
            long[] quantity = Console.ReadLine().Split().Select(long.Parse).ToArray();

            string doneCheck = String.Empty;
            int elem = 0;

            while ((doneCheck = Console.ReadLine()) != "Done")
            {
                depot.Add(names[elem], new Tuple<long, double>(quantity[elem], prices[elem]));
                elem++;
            }

            foreach (KeyValuePair<string, Tuple<long, double>> item in depot)
            {
                Console.WriteLine($"{item.Key} costs {item.Value.Item2} available quantity: {item.Value.Item1}");
            }
        }
    }
}
