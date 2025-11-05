public class MyProgram
{
    public static void main(String[] args)
    {
        System.out.println(decimalToAnyBase(anyBaseToDecimal("765",8), 5));
        System.out.println(anyBaseToDecimal("3434adf",16));
    }
    public static int anyBaseToDecimal(String otherbase, int base){
        int result = 0;
        for (int i = 0; i < otherbase.length(); i++){
            String d = otherbase.substring(i, i+1);
            switch(d){
                case "a":
                    d = "10";
                    break;
                case "b":
                    d = "11";
                    break;
                case "c":
                    d = "12";
                    break;
                case "d":
                    d = "13";
                    break;
                case "e":
                    d = "14";
                    break;
                case "f":
                    d = "15";
                    break;
            }
            result+= Integer.parseInt(d)*Math.pow(base, otherbase.length() - 1 -i);
        }
        return result;
    }
    public static String decimalToAnyBase(int decimal, int base){
        String result = "";
        while (decimal!=0){
            result =decimal%base+ result;
            decimal=decimal/base;
        }
        return result;
    }
}
