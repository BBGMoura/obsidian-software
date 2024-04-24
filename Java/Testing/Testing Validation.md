``` java
public class InvoiceUnitTest {

    private static Validator validator;

    @BeforeClass
    public static void setupValidatorInstance() {
        validator = Validation.buildDefaultValidatorFactory().getValidator();
    }

    @Test
    public void whenMoreThanThreeIntegerDigits_thenShouldGiveConstraintViolations() {
        Invoice invoice = new Invoice(new BigDecimal("1021.21"), "Book purchased");
        Set<ConstraintViolation<Invoice>> violations = validator.validate(invoice);
        assertThat(violations).hasSize(1);
        assertThat(violations)
            .extracting("message")
            .containsOnly("numeric value out of bounds (<3 digits>.<2 digits> expected)");
    }
}
```