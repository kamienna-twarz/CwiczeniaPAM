# Ćwiczenia 27 -- Android studio -- Testy

Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie MyTest na podstawie Empty Activity, dobierz
    odpowiednie API ( 28 -- Android 9).

1. Otwórz dokumentację:

    <https://developer.android.com/codelabs/advanced-android-kotlin-training-testing-basics#0>

    <https://developer.android.com/codelabs/advanced-android-kotlin-training-welcome#1>

    <https://developer.android.com/courses/kotlin-android-fundamentals/overview>

    <https://developer.android.com/codelabs/kotlin-android-training-internet-data?index=..%2F..android-kotlin-fundamentals#0>

1. Dodaj zależności dla JUnit 5

   Local Unit Tests. Testy jednostkowe uruchamiane na JVM
   – szybkie, nie wymagają emulatora.

   app/src/test/java  

   Instrumented Tests. Testy instrumentacyjne uruchamiane na urządzeniu/emulatorze,
   – np. testy UI Espresso

   app/src/androidTest/java

1. Użyj Ctrl+Shift+T będąc na nazwie klasy, aby wygenero

1. Utwórz klasę:

   ```java
   public class RegistrationValidator {
       /**
        * Waliduje hasło: min 8 znaków, zawiera cyfrę.
        */
       public boolean isValidPassword(String password) {
           if (password == null) return false;
           return password.length() >= 8 && password.matches(".*\\d.*");
       }
   }
   ```

1. Utwórz klasę RegistrationValidatorTest.java :

   ```java
    import static org.junit.Assert.*;
    import org.junit.Before;
    import org.junit.Test;

    public class RegistrationValidatorTest {
        private RegistrationValidator validator;

        @Before
        public void setUp() {
            validator = new RegistrationValidator();
        }

        @Test
        public void isValidPassword_shortPassword_returnsFalse() {
            // Arrange (Przygotowanie)
            String pass = "1abc";
            
            // Act (Działanie)
            boolean result = validator.isValidPassword(pass);
            
            // Assert (Weryfikacja)
            assertFalse("Hasło zbyt krótkie powinno zostać odrzucone", result);
        }

        @Test
        public void isValidPassword_noDigit_returnsFalse() {
            assertFalse(validator.isValidPassword("abcdefghij"));
        }

        @Test
        public void isValidPassword_correctPassword_returnsTrue() {
            assertTrue(validator.isValidPassword("TajneHaslo123"));
        }
    }
   ```

1. Utwórz klasę LoginUiTest.java.
   Testujemy scenariusz:
   użytkownik wpisuje błędne hasło -> klika przycisk -> widzi komunikat o błędzie.

   ```java
    @RunWith(AndroidJUnit4.class)
    public class LoginUiTest {
        @Rule
        public ActivityScenarioRule<MainActivity> activityRule =
                new ActivityScenarioRule<>(MainActivity.class);

        @Test
        public void loginError_isDisplayed_whenPasswordInvalid() {
            // Wpisz tekst
            onView(withId(R.id.password_field)).perform(typeText("123"), closeSoftKeyboard());
            
            // Kliknij przycisk
            onView(withId(R.id.login_button)).perform(click());

            // Sprawdź czy TextView wyświetla odpowiedni błąd
            onView(withId(R.id.error_message))
                    .check(matches(withText("Hasło jest zbyt krótkie")));
        }
    }
   ```

1. Dodatkowe zadania

    - dopisz testy krawędziowe (null, puste stringi, znaki specjalne).
    - zaimplementuj RegistrationValidator z obsługą adresów e-mail (Regex)
    - dodaj nową aktywność
    - dodaj testy
  
1. KONIEC.
