import java.util.Scanner;
class calc2 {
    private static int value(char r) {
        if (r == 'I')
            return 1;
        if (r == 'V')
            return 5;
        if (r == 'X')
            return 10;
        if (r == 'L')
            return 50;
        if (r == 'C')
            return 100;
        if (r == 'D')
            return 500;
        if (r == 'M')
            return 1000;
        return -1;
    }

    private static int romanToDecimal(String str) {
        // Initialize result
        int res = 0;

        for (int i = 0; i < str.length(); i++) {
            // Getting value of symbol s[i]
            int s1 = value(str.charAt(i));
            if(s1 == -1) {
            	throw new IllegalArgumentException("Неверный формат данных");
            }

            // Getting value of symbol s[i+1]
            if (i + 1 < str.length()) {
                int s2 = value(str.charAt(i + 1));
                if(s2 == -1) {
                	throw new IllegalArgumentException("Неверный формат данных");
                }
                
                // Comparing both values
                if (s1 >= s2) {
                    // Value of current symbol is greater
                    // or equalto the next symbol
                    res = res + s1;
                } else {
                    res = res + s2 - s1;
                    i++; // Value of current symbol is
                    // less than the next symbol
                }
            } else {
                res = res + s1;
                i++;
            }
        }

        return res;
    }

    private static String intToRoman(int num)
    {
        // storing roman values of digits from 0-9
        // when placed at different places
        String m[] = {"", "M", "MM", "MMM"};
        String c[] = {"", "C", "CC", "CCC", "CD", "D",
                "DC", "DCC", "DCCC", "CM"};
        String x[] = {"", "X", "XX", "XXX", "XL", "L",
                "LX", "LXX", "LXXX", "XC"};
        String i[] = {"", "I", "II", "III", "IV", "V",
                "VI", "VII", "VIII", "IX"};

        // Converting to roman
        String thousands = m[num/1000];
        String hundereds = c[(num%1000)/100];
        String tens = x[(num%100)/10];
        String ones = i[num%10];

        String ans = thousands + hundereds + tens + ones;

        return ans;
    }

    private static int calculate(int number1, int number2, char operation){
        int result = 0;
        switch (operation){
            case '+': result = number1 + number2; break;
            case '-': result = number1 - number2; break;
            case '*': result = number1 * number2; break;
            case '/': result = number1 / number2; break;
            default: throw  new IllegalArgumentException("Неверный формат данных");
        }
        return result;
    }

    public static void main(String[] args) {

        String[] roman = {"X", "IX", "VIII", "VII", "VI", "V", "IV", "III", "II", "I"};
        Scanner scanner = new Scanner(System.in);
        String[] blocks = scanner.nextLine().split(" ");
        char operation = blocks[1].charAt(0);
        int number1 = 0, number2 = 0;
        boolean flag1 = false, flaq2 = false;
        
        if(blocks.length != 3) {
        	throw new IllegalArgumentException("Неверный формат данных");
        }
        try {
            for (int i = 0; i < roman.length; i++) {
                if (roman[i].equals(blocks[0])) {
                    flag1 = true;
                }
                if (roman[i].equals(blocks[2])) {
                    flaq2 = true;
                }
            }
            if (flag1 && flaq2) {
                number1 = romanToDecimal(blocks[0]);
                number2 = romanToDecimal(blocks[2]);
                if ((number1 > 10 || number1 < 1) || (number2 > 10 || number2 < 1)) {
                    throw new IllegalArgumentException("Неверный формат данных");
                }
                System.out.println(intToRoman(calculate(number1, number2, operation)));

            } else if (!flag1  && !flaq2){
            	try{
            		number1 = Integer.parseInt(blocks[0]);
                number2 = Integer.parseInt(blocks[2]);
            	} catch(IllegalArgumentException e) {
            		throw new IllegalArgumentException("Неверный формат данных");
            	}
                if ((number1 > 10 || number1 < 1) || (number2 > 10 || number2 < 1)) {
                    throw new IllegalArgumentException("Неверный формат данных");
                }
                System.out.println(calculate(number1, number2, operation));
            } else {
            	throw new IllegalArgumentException("Неверный формат данных");
            }
            
        } catch (RuntimeException e) {
            throw new IllegalArgumentException("Неверный формат данных");
        }

    }
}
