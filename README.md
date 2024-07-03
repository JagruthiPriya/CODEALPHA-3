# CODEALPHA-3
import java.util.HashMap;
import java.util.Scanner;

public class Chatbot {

    // Predefined responses
    private static final HashMap<String, String> predefinedResponses = new HashMap<>();

    static {
        predefinedResponses.put("hello", "Hi there! How can I help you today?");
        predefinedResponses.put("how are you", "I'm just a bot, but I'm here to help you!");
        predefinedResponses.put("what is your name", "I'm a chatbot created to assist you.");
        predefinedResponses.put("bye", "Goodbye! Have a great day!");
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input;

        System.out.println("Chatbot: Hello! I am your assistant. Type 'exit' to end the conversation.");

        while (true) {
            System.out.print("You: ");
            input = scanner.nextLine().toLowerCase();

            if (input.equals("exit")) {
                System.out.println("Chatbot: Goodbye! Have a great day!");
                break;
            }

            String response = getResponse(input);
            System.out.println("Chatbot: " + response);
        }

        scanner.close();
    }

    // Method to get response from predefined responses
    private static String getResponse(String input) {
        for (String key : predefinedResponses.keySet()) {
            if (input.contains(key)) {
                return predefinedResponses.get(key);
            }
        }
        return "I'm sorry, I don't understand that.";
    }
}
