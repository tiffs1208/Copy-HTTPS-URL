
using System;

namespace StudentGroupModule
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a group with 3 members
            StudentGroup group = new StudentGroup("Team Alpha", 3);

            // Add students
            group.AddMember(0, "Alice");
            group.AddMember(1, "Bob");
            group.AddMember(2, "Charlie");

            // Retrieve a student using GetMember
            Console.WriteLine("Student at position 1 (GetMember): " + group.GetMember(1));

            // Retrieve a student using GetStudent (alias)
            Console.WriteLine("Student at position 2 (GetStudent): " + group.GetStudent(2));

            // Test invalid index
            Console.WriteLine("Testing invalid index: " + group.GetMember(5));

            // Display full group
            group.DisplayGroup();

            Console.ReadLine(); // Pause to view results
        }
    }
}
