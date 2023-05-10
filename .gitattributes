import java.util.Scanner;

public class Calc {

    public static void main(String[] args) throws Exception {

        Scanner scanner = new Scanner(System.in);
        System.out.println("Введите выражение: ");
        String expression = scanner.nextLine();
        try {
        System.out.println("\"" + parse(expression) + "\"");
        } catch (NumberFormatException e) {
            System.err.println("Калькулятор работает только с целыми числами");
        }
    }
    public static String parse(String expression) throws Exception {

        String Str1;
        String Str2;
        String operation;
        String result;

        operation = detectOperation(expression);
        String[] data = expression.split("[+\\-*/]");

        if (operation == null) throw new Exception("строка не является математической операцией");
        if (data.length != 2) throw new Exception(" должно быть два операнда и один оператор (+, -, /, *)");

        int index = data[0].indexOf("\"");
        if (index == -1) throw new Exception ("Первым аргументом выражения, подаваемого на вход, должна быть строка");

        if (operation == "*" || operation == "/")
        {if (data[1].contains("\"")) throw new Exception("Строчку можно делить или умножать только на число");}

        Str1 = data[0];
        Str1 = Str1.replace("\"", "");
        Str2 = data[1];
        Str2 = Str2.replace("\"", "");

        result = calculator(Str1, Str2, operation);

        return result;
    }

    public static String detectOperation(String expression) {
        if (expression.contains("+")) return "+";
        else if (expression.contains("-")) return "-";
        else if (expression.contains("*")) return "*";
        else if (expression.contains("/")) return "/";
        else return null;
    }

    static String calculator(String Str1, String Str2, String operation) throws Exception {
        if (Str1.length()>10 || Str2.length()>10) throw new Exception("Калькулятор принимает на вход строки длиной 10 символов включительно");
        if (operation.equals("+")) return (Str1 + Str2);
        else if (operation.equals("*")) {
            int num2 = Integer.parseInt(Str2);
            String result = "";
            for (int x = 0; x < num2; x++) {
                result += Str1;
            }
            if (Integer.parseInt(Str2)<1 || Integer.parseInt(Str2)>10) throw new Exception("Калькулятор принимает на вход числа от 1 до 10 включительно");
            if (result.length()>40) return result+"...";
            return result;
        }
        else if (operation.equals("-")) {
        int index = Str1.indexOf(Str2);
        if (index == -1) return Str1;
        else {
            String result = Str1.substring(0, index);
            result += Str1.substring(index + Str2.length());
            return result;
        }
    }
        else {
            int newlength = Str1.length() / Integer.parseInt(Str2);
            String result = Str1.substring(0, newlength);
            return result;
        }

    }

}
