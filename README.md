using System;
using System.Text;

public class Sign
{
    private string message;
    private int width;

    // Constructor
    public Sign(string message, int width)
    {
        this.message = message;
        this.width = width;
    }

    // Returns the number of lines required to display the message
    public int NumberOfLines()
    {
        if (string.IsNullOrEmpty(message))
            return 0; // Empty message case

        return (message.Length + width - 1) / width; // Round up
    }

    // Returns the formatted message, with lines separated by semicolons
    public string GetLines()
    {
        if (string.IsNullOrEmpty(message))
            return null; // Empty message case

        StringBuilder sb = new StringBuilder();
        int len = message.Length;

        for (int i = 0; i < len; i += width)
        {
            int end = Math.Min(i + width, len);
            sb.Append(message.Substring(i, end - i));
            if (end < len)
                sb.Append(";");
        }

        return sb.ToString();
    }
}
