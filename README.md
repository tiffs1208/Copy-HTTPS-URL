using System;

namespace StudentGroupModule
{
    public class StudentGroup
    {
        private string groupName;
        private string[] members;

        // Constructor: create a group with a name and fixed size
        public StudentGroup(string name, int size)
        {
            groupName = name;
            members = new string[size];
        }

        // Add a student at a specific position
        public void AddMember(int position, string name)
        {
            if (position < 0 || position >= members.Length)
            {
                Console.WriteLine("Error: Invalid position.");
                return;
            }
            members[position] = name;
        }

        // Retrieve a student name by position
        public string GetMember(int position)
        {
            if (position < 0 || position >= members.Length)
            {
                return "Error: Invalid position.";
            }
            return members[position] ?? "No student assigned.";
        }

        // Display the group name and all members
        public void DisplayGroup()
        {
            Console.WriteLine($"Group: {groupName}");
            for (int i = 0; i < members.Length; i++)
            {
                Console.WriteLine(members[i] ?? "(empty)");
            }
        }
    }
}
