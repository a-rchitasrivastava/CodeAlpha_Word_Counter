# CodeAlpha_Word_Counter
Creating a simple word counter application using Swing in Java is a great project for beginners. This project will involve setting up a basic GUI with text input and output functionality. Here's a step-by-step guide to building this application:

Set up the project: Ensure you have a Java development environment set up with JDK and an IDE like IntelliJ IDEA or Eclipse.

Create the main application window: This involves creating a JFrame to hold all the components.

Add a text area for input: Users will enter their paragraphs here.

Add a button to trigger the word count: When clicked, this button will process the input text.

Add a label to display the word count: This will show the number of words in the entered paragraph.

Implement the word counting logic: This will count the words in the input text and update the label.

Here’s the complete code for this simple Swing application:

java
Copy code
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class WordCounter extends JFrame implements ActionListener {
    // Declare the components
    private JTextArea textArea;
    private JButton countButton;
    private JLabel resultLabel;

    // Constructor to set up the GUI components and event handling
    public WordCounter() {
        // Set the title of the window
        setTitle("Word Counter");
      // Set the layout of the window
        setLayout(new BorderLayout());

        // Initialize the text area
        textArea = new JTextArea(10, 30);
        JScrollPane scrollPane = new JScrollPane(textArea);

        // Initialize the button and add action listener
        countButton = new JButton("Count Words");
        countButton.addActionListener(this);

        // Initialize the label
        resultLabel = new JLabel("Word Count: 0");

        // Add the components to the window
        add(scrollPane, BorderLayout.CENTER);
        add(countButton, BorderLayout.SOUTH);
        add(resultLabel, BorderLayout.NORTH);

        // Set the default close operation and window size
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setSize(400, 300);
    }

    // Event handling for the button click
    @Override
    public void actionPerformed(ActionEvent e) {
        if (e.getSource() == countButton) {
            // Get the text from the text area
            String text = textArea.getText();

            // Count the words in the text
            int wordCount = countWords(text);

            // Update the label with the word count
            resultLabel.setText("Word Count: " + wordCount):
            }
          }
            // Method to count the words in a given text
    private int countWords(String text) {
        if (text == null || text.isEmpty()) {
            return 0;
        }

        // Split the text by spaces and count the parts
        String[] words = text.trim().split("\\s+");
        return words.length;
    }

    // Main method to run the application
    public static void main(String[] args) {
        // Create an instance of the application and make it visible
        WordCounter wordCounter = new WordCounter();
        wordCounter.setVisible(true);
    }
}
Explanation
Components:

JTextArea for the input paragraph.
JButton to trigger the word count.
JLabel to display the word count result.
Layout:

BorderLayout is used to place the text area at the center, the button at the bottom, and the label at the top.
Event Handling:

The ActionListener interface is implemented to handle button click events.
When the button is clicked, the actionPerformed method is called, which retrieves the text, counts the words, and updates the label.
Word Counting Logic:

The countWords method splits the input text by spaces to count the number of words.
Run the code in your IDE, and you will have a simple word counter application using Java Swing. This project helps in understanding the basics of GUI programing,event handling,and simple string manipulation in
java.
