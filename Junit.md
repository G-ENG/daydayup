## 1. 参数化测试
> - @RunWith(Parameterized.class)
> - 
~~~ java
@RunWith(Parameterized.class)
public class EvenNumberCheckerTest {
 
    // Step 2: variables to be used in test method of Step 5
    private int inputNumber;
    private boolean isEven;
 
    // Step 3: parameterized constructor
    public EvenNumberCheckerTest(int inputNumber, boolean isEven) {
        super();
        this.inputNumber = inputNumber;
        this.isEven = isEven;
    }
 
    // Step 4: data set of variable values
    @Parameters
    public static Collection<Object[]> data() {
        Object[][] data = new Object[][] {
                { 2, true },
                { 5, false },
                { 10, false }
        };
        return Arrays.asList(data);
    }
 
    @Test
    public void test() {
        System.out.println("inputNumber: " + inputNumber + "; isEven: " + isEven);
        EvenNumberChecker evenNumberChecker = new EvenNumberChecker();
        // Step 5: use variables in test code
        boolean actualResult = evenNumberChecker.isEven(inputNumber);
        assertEquals(isEven, actualResult);
    }

~~~
Junit - 测试框架介绍
Junit - Eclipse 教程
Junit - 基础注解（@BeforeClass、@Before、@Test、@After、@AfterClass）
Junit - 断言方法（Assert Methods）
Junit - 参数化测试（Parameterized Test）
Junit - 套件测试（Suite Test）
Junit - 忽略测试（Ignore Test）
Junit - 超时测试（Timeout Test）
Junit - 期望异常测试（Expected Test）
Junit - 优先级测试（FixMethodOrder Test）
