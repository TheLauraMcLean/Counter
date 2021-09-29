public class Counter {

    private int currentCount;

    private int stepSize;

    public Counter(int startValue){
        this.currentCount = startValue;
        this.stepSize = 1;
        System.out.println("Creating Counter object with a starting value of "+
                this.currentCount);
    }

    public Counter(int startValue,int step){
        this.currentCount = startValue;
        this.stepSize = step;
        System.out.println("Creating Counter object with a starting value of "+
                this.currentCount+" and a step size of "+this.stepSize);
    }

    public void countUp(int n,char operation){
        System.out.println("*** Counting up "+n+"");
        for(int step=1; step<=n;step++){

            if(currentCount <= 0){
                break;
            }
            System.out.println("counter = "+currentCount );
            if(operation =='+'){
                currentCount = currentCount +stepSize;
            }else if(operation =='-'){
                currentCount = currentCount - stepSize;
            }else if(operation == '*'){
                currentCount = currentCount * stepSize;
            }else{
                System.out.println("Invalid operation: "+operation);
                break;
            }
        }
    }
}

public class Number {
    public static void main(String[] args){
        System.out.println("Starting Application...");

        Counter c = new Counter(1,3);

        c.countUp(2);
        c.countUp(3);
        c.countDown(4);
        c.countUp(2);
        c.countDown(6);
        c.countUp(2);

        c.countUp(5,'*');

        Counter c1 = new Counter(5);

        Counter c2 = new Counter(5);

        c1.countUp(2,'-');

        c1.countUp(2,'?');

        c2.countUp(2);
    }
}
