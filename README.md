# my-project-repo
import java.util.ArrayList;
import java.util.Scanner;

public class ToDoListApp {
    public static void main(String[] args) {
        ArrayList<String> toDoList = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("\nTo-Do List Application");
            System.out.println("1. Add Task");
            System.out.println("2. View Tasks");
            System.out.println("3. Remove Task");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");

            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume the newline character

            switch (choice) {
                case 1:
                    System.out.print("Enter a new task: ");
                    String task = scanner.nextLine();
                    toDoList.add(task);
                    System.out.println("Task added successfully!");
                    break;
                case 2:
                    System.out.println("\nYour Tasks:");
                    if (toDoList.isEmpty()) {
                        System.out.println("No tasks to display.");
                    } else {
                        for (int i = 0; i < toDoList.size(); i++) {
                            System.out.println((i + 1) + ". " + toDoList.get(i));
                        }
                    }
                    break;
                case 3:
                    System.out.println("\nYour Tasks:");
                    if (toDoList.isEmpty()) {
                        System.out.println("No tasks to remove.");
                    } else {
                        for (int i = 0; i < toDoList.size(); i++) {
                            System.out.println((i + 1) + ". " + toDoList.get(i));
                        }
                        System.out.print("Enter the task number to remove: ");
                        int taskNumber = scanner.nextInt();
                        if (taskNumber > 0 && taskNumber <= toDoList.size()) {
                            toDoList.remove(taskNumber - 1);
                            System.out.println("Task removed successfully!");
                        } else {
                            System.out.println("Invalid task number!");
                        }
                    }
                    break;
                case 4:
                    System.out.println("Exiting the application. Goodbye!");
                    scanner.close();
                    return;
                default:
                    System.out.println("Invalid choice! Please try again.");
            }
        }
    }
}
