# codsoft_task-4

TASK 4
(QUIZ APPLICATION WITH TIMER)
1.	Quiz Questions and Options: Store quiz questions along with multiple-choice options and correct answers.
2.	Timer: Implement a timer for each question to limit the time to answer.
3.	Question Display: Present one question at a time with multiple-choice options.
4.	Answer Submission: Allow users to select an option and submit their answer within the given time.
5.	Score Calculation: Keep track of the user's score based on correct answers.
6.	Result Screen: Display the final score and a summary of correct/incorrect answers.

# ans:

	import java.util.*;
	class Quizquestion {
    String question;
    List<String> options;
    int Rightoption;
    public Quizquestion(String question, List<String> options, int Rightoption) {
        this.question = question;
        this.options = options;
        this.Rightoption = Rightoption;
    }
    public String getquestion() {
        return question;
    }
    public List<String> getoptions() {
        return options;
    }
    public int getcorrectoption() {
        return Rightoption;
    }
	}
	class application {
    static List<Quizquestion> questions = new ArrayList<>();
    static int score = 0;
    public static void main(String[] args) {
        questions();
        quiz();
    }
    static void questions() {
        List<String> options1 = Arrays.asList("1: Dynamic", "2: Architecture Neutral", "3: Use of pointers", "4: Object-oriented");
        Quizquestion question1 = new Quizquestion("Question 1: Which of the following is not a Java features?", options1, 3);
        List<String> options2 = Arrays.asList("1: Unicode escape sequence", "2: Octal escape", "3: Hexadecimal", "4: Line feed");
        Quizquestion question2 = new Quizquestion("Question 2: The \u0021 article referred to as a", options2, 1);
        List<String> options3 = Arrays.asList("1: JRE", "2: JDB", "3: JDK", "4: JVM");
        Quizquestion question3 = new Quizquestion("Question 3: _____ is used to find and fix bugs in the Java programs.", options3, 2);
        List<String> options4 = Arrays.asList("1: Object", "2: int", "3: long", "4: void");
        Quizquestion question4 = new Quizquestion("Question 4: What is the return type of the hashCode() method in the Object class?", options4, 2);
        List<String> options5 = Arrays.asList("1: ABH8097", "2: L990023", "3: 904423", "4: 0xnf029L");
        Quizquestion question5 = new Quizquestion("Question 5: Which of the following is a valid long literal?", options5, 4);


        questions.add(question1);
        questions.add(question2);
        questions.add(question3);
        questions.add(question4);
        questions.add(question5);
    }
    static void quiz() {
        Scanner scanner = new Scanner(System.in);
        for (Quizquestion question : questions) {
            System.out.println(question.getquestion());
            for (String option : question.getoptions()) {
                System.out.println(option);
            }
            Timer timer = new Timer();
            TimerTask task = new TimerTask() {
                @Override
                public void run() {
                    System.out.println("Time's up!");
                    timer.cancel();
                    System.exit(0);
                }
            };
            timer.schedule(task, 20000);
            int selectoption = scanner.nextInt();
            timer.cancel(); 
            if (selectoption == question.getcorrectoption()) {
                System.out.println("Correct answer.");
                score++;
            } else if (selectoption != 1 ) {
                System.out.println("Invalid answer.");
            } else if (selectoption != 2 ) {
                System.out.println("Invalid answer.");
            } else if ( selectoption != 3 ) {
                System.out.println("Invalid answer.");
            } else if (selectoption != 4  ) {
                System.out.println("Invalid answer.");
            }
            else {
                System.out.println("Incorrect answer.");
            }
        }
        scanner.close();
        System.out.println("\nResult : ");
        System.out.println("---------------------------------------------------");
        System.out.println("Your score is: " + score + "/" + questions.size());
    }
	}

# instruction:

	1. copy full code.
	2. save the code: QuizGame.java
	3. combine the code: javac QuizGame.java
	4. run the code: java application
