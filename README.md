public class Calculator {
    private int result;

    public Calculator() {
        this.result = 0;
    }

    public int add(int a, int b) {
        result = a + b;
        return result;
    }

    public int subtract(int a, int b) {
        result = a - b;
        return result;
    }

    public int multiply(int a, int b) {
        result = a * b;
        return result;
    }

    public int divide(int a, int b) {
        if (b == 0) {
            throw new ArithmeticException("Cannot divide by zero!");
        }
        result = a / b;
        return result;
    }

    public int getResult() {
        return result;
    }

    public static void main(String[] args) {
        Calculator calc = new Calculator();

        System.out.println("Welcome to Simple Calculator!");
        System.out.println("Adding 5 + 3 = " + calc.add(5, 3));
        System.out.println("Subtracting 10 - 4 = " + calc.subtract(10, 4));
        System.out.println("Multiplying 6 * 2 = " + calc.multiply(6, 2));
        System.out.println("Dividing 15 / 3 = " + calc.divide(15, 3));
    }
}
import org.junit.Test;
import static org.junit.Assert.*;

public class CalculatorTest {
    private Calculator calculator = new Calculator();

    @Test
    public void testAdd() {
        assertEquals(8, calculator.add(5, 3));
    }

    @Test
    public void testSubtract() {
        assertEquals(6, calculator.subtract(10, 4));
    }

    @Test
    public void testMultiply() {
        assertEquals(12, calculator.multiply(6, 2));
    }

    @Test
    public void testDivide() {
        assertEquals(5, calculator.divide(15, 3));
    }

    @Test(expected = ArithmeticException.class)
    public void testDivideByZero() {
        calculator.divide(10, 0);
    }
}
class Calculator {
    constructor() {
        this.result = 0;
    }

    add(a, b) {
        this.result = a + b;
        return this.result;
    }

    subtract(a, b) {
        this.result = a - b;
        return this.result;
    }

    multiply(a, b) {
        this.result = a * b;
        return this.result;
    }

    divide(a, b) {
        if (b === 0) {
            throw new Error("Cannot divide by zero!");
        }
        this.result = a / b;
        return this.result;
    }

    getResult() {
        return this.result;
    }
}

// Demo the calculator
const calc = new Calculator();
console.log("Welcome to Simple Calculator!");
console.log("Adding 5 + 3 =", calc.add(5, 3));
console.log("Subtracting 10 - 4 =", calc.subtract(10, 4));
console.log("Multiplying 6 * 2 =", calc.multiply(6, 2));
console.log("Dividing 15 / 3 =", calc.divide(15, 3));

export default Calculator;
import Calculator from './calculator.js';

describe('Calculator', () => {
    let calculator;

    beforeEach(() => {
        calculator = new Calculator();
    });

    test('adds two numbers correctly', () => {
        expect(calculator.add(5, 3)).toBe(8);
    });

    test('subtracts two numbers correctly', () => {
        expect(calculator.subtract(10, 4)).toBe(6);
    });

    test('multiplies two numbers correctly', () => {
        expect(calculator.multiply(6, 2)).toBe(12);
    });

    test('divides two numbers correctly', () => {
        expect(calculator.divide(15, 3)).toBe(5);
    });

    test('throws error when dividing by zero', () => {
        expect(() => calculator.divide(10, 0)).toThrow('Cannot divide by zero!');
    });
});
