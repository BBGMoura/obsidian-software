The three A's of testing are useful memory device for the three steps required to successfully test a method.

### Arrange
Prepare object to be tested. If it requires specific data, provide it. If it requires specific internal objects, provide them.

### Act
Execute the method to be tested. With stateful objects, we many not capture the method's return value. Instead, we may execute the method and then confirm he object is in the correct state

### Assert
Confirm that the value returned or the state of the object matches what is expected.

```java
@Test
void shouldMakeSmallInvalidPowerTheMinimum() {

    // Arrange
    Cyclist cyclist = new Cyclist("Test Cyclist", 0.111);
    // Act
    double actual = cyclist.getPower();
    // Assert
    assertEquals(1.0, actual, 0.01);
}
```

## Stateful Testing
`@BeforeEach` can be used to define all arrangement code in a single method. It happens before each test as they do not always run in order.

```java
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.assertEquals;

class BicycleTest {

    // Make three bicycles available to all tests.
    Bicycle highPowerBike;
    Bicycle mediumPowerBike;
    Bicycle lowPowerBike;

    // @BeforeEach indicates that this method runs before each test.
    @BeforeEach
    void setupBeforeEachTest() {
        // The Arrangement step occurs in a dedicated setup method.
        Cyclist highPowerCyclist = new Cyclist("High Power Cyclist", 9.87);
        highPowerBike = new Bicycle(highPowerCyclist);

        Cyclist mediumPowerCyclist = new Cyclist("Medium Power Cyclist", 4.9);
        mediumPowerBike = new Bicycle(mediumPowerCyclist);

        Cyclist lowPowerCyclist = new Cyclist("Low Power Cyclist", 1.54);
        lowPowerBike = new Bicycle(lowPowerCyclist);
    }

    @Test
    void shouldAccelerate() {
        highPowerBike.accelerate();
        assertEquals(8.55, highPowerBike.getVelocity(), 0.01);

        mediumPowerBike.accelerate();
        assertEquals(6.56, mediumPowerBike.getVelocity(), 0.01);

        lowPowerBike.accelerate();
        assertEquals(5.22, lowPowerBike.getVelocity(), 0.01);
    }
}
```

## Conclusion
Unit tests are not guaranteed to run in order. Never create dependencies between tests. Keep tests independent. If one test needs the output of another, don't link the two test methods. Take the time to explicitly arrange objects into a testable state per test.