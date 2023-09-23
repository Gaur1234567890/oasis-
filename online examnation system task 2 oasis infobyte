// ONLINE EXAMINATION
// THE ONLINE EXAMINATION CODE IS DONE BY VISHAL KUMAR PATEL.
// THE CODE HAS SOME PROPERTIES LIKE LOGIN ID I.E USERNAME IS "VishalKumar" and Password is "VKPatel123"
// THE ONLINE EXAMINATION HAS FIXED TIMER OF 30 SECONDS YOU HAVE TO ANSWER FOUR QUESTIONS IN 30 SECONDS OR ELSE IT WILL CLOSE


import java.util.Scanner;
import java.util.Timer;
import java.util.TimerTask;

class User {
    private String username;
    private String password;
    private String profile;

    public User(String username, String password) {
        this.username = username;
        this.password = password;
    }

    public String getUsername() {
        return username;
    }

    public String getPassword() {
        return password;
    }

    public String getProfile() {
        return profile;
    }

    public void setProfile(String profile) {
        this.profile = profile;
    }

    public void setPassword(String password) {
        this.password = password;
    }
}

class Exam {
    private String[] questions;
    private String[] options;
    private int[] answers;
    private Timer timer;
    private boolean isExamCompleted;

    public Exam() {
        questions = new String[] {
                "Question 1: Who is India's First Prime Minister?",
                "Question 2: Who is the author of 'India that is Bharat'?",
                "Question 3: How many States in India have Legislative Council",
                "Question 4: The Palk Strait separates india from ?"
        };

        options = new String[] {
                "a) Narendra Modi\nb) Jawaharlal Nehru\nc) Sardar Vallabhai Patel\nd) Rajiv Gandhi",
                "a) J. Sai Deepak\nb) Anand Ranganathan \nc) Shashi Tharoor \nd) Chetan Bhagat",
                "a) 6\nb) 8\nc) 11\nd) 12",
                "a) UAE\nb) Maldives\nc) Sri Lanka\nd) China"
        };

        answers = new int[] { 1, 0, 0,2 };
        isExamCompleted = false;
    }

    public void startExam() {
        int score = 0;
        Scanner scanner = new Scanner(System.in);
        System.out.println("\n\n!! Attention !!\n\n");
        System.out.println("\n!! You Will get 30 seconds to answer all the questions !!\n");
        System.out.println("Exam will start Soon. Good luck!");

        timer = new Timer();
        timer.schedule(new TimerTask() {
            @Override
            public void run() {
                System.out.println("\n !! Time's up !!");
                isExamCompleted = true;
                timer.cancel();
            }
        }, 30000); // Timer of 30 seconds

        for (int i = 0; i < questions.length; i++) {
            if (isExamCompleted) {
                break;
            }

            System.out.println("\n" + questions[i]);
            System.out.println(options[i]);

            System.out.print("Enter your answer (a, b, c, or d): ");
            String answer = scanner.nextLine();

            if (answer.equalsIgnoreCase("a") ||
                    answer.equalsIgnoreCase("b") ||
                    answer.equalsIgnoreCase("c") ||
                    answer.equalsIgnoreCase("d")) {
                if (answer.equalsIgnoreCase(String.valueOf((char) ('a' + answers[i])))) {
                    score++;
                }
            } else {
                System.out.println("Invalid answer. Skipping the question.");
            }
        }

        if (!isExamCompleted) {
            System.out.println("\nExam completed!");
            System.out.println("Your score: " + score + "/" + questions.length);
        }
    }
}

public class OnlineExamination1 {
    private static User currentUser;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("\n--- Online Examination System ---");
            System.out.println("1. Login");
            System.out.println("2. Update Profile and Password");
            System.out.println("3. Start Exam");
            System.out.println("4. Logout");
            System.out.print("Enter your choice (1-4): ");

            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline character

            switch (choice) {
                case 1:
                    login();
                    break;
                case 2:
                    updateProfileAndPassword();
                    break;
                case 3:
                    startExam();
                    break;
                case 4:
                    logout();
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    private static void login() {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter username: ");
        String username = scanner.nextLine();

        System.out.print("Enter password: ");
        String password = scanner.nextLine();

        // Simulating login with a hardcoded user
        if (username.equals("VishalKumar") && password.equals("VKPatel123")) {
            currentUser = new User(username, password);
            System.out.println("Login successful!");
        } else {
            System.out.println("Invalid username or password. Please try again.");
        }
    }

    private static void updateProfileAndPassword() {
        if (currentUser == null) {
            System.out.println("Please login first.");
            return;
        }

        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter new profile information: ");
        String profile = scanner.nextLine();
        currentUser.setProfile(profile);

        System.out.print("Enter new password: ");
        String password = scanner.nextLine();
        currentUser.setPassword(password);

        System.out.println("Profile and password updated successfully!");
    }

    private static void startExam() {
        if (currentUser == null) {
            System.out.println("Please login first.");
            return;
        }

        Exam exam = new Exam();
        exam.startExam();
    }

    private static void logout() {
        if (currentUser == null) {
            System.out.println("Please login first.");
            return;
        }

        currentUser = null;
        System.out.println("Logged out successfully!");
    }
}
