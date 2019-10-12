<!-- TITLE: Classe Swipe Java -->
<!-- SUBTITLE: Como Realizar um Swipe mobile no java -->

public class AppiumRobot extends BaseTest {
public static void swipeVertical(double startPercentage, double finalPercentage, int durantion) {

        try {
            TouchAction action = new TouchAction(driver);
            Dimension size = driver.manage().window().getSize();
            int width = (int) (size.width / 2);
            int startPoint = (int) (size.height * startPercentage);
            int endPoint = (int) (size.getHeight() * finalPercentage);
            action.press(width, startPoint).waitAction(Duration.ofSeconds(durantion)).moveTo(width, endPoint).release()
                    .perform();
        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    /**
     * move para baixo até o elemento aparecer
     *
     * @param xpath
     */
    public static void swipeDown(String xpath) {

        try {
            TouchAction action = new TouchAction(driver);
            Dimension size = driver.manage().window().getSize();
            int width = (int) (size.width / 2);
            int startPoint = (int) (size.height - 10);
            int endPoint = (int) (10);
            while (elementExists(xpath) == false) {
                action.press(width, startPoint).waitAction(Duration.ofSeconds(4)).moveTo(width, endPoint).release()
                        .perform();
            }
        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    public static void swipeUp(String xpath) {

        try {
            TouchAction action = new TouchAction(driver);
            Dimension size = driver.manage().window().getSize();
            int width = (int) (size.width / 2);
            int startPoint = (int) (230);
            int endPoint = (int) (size.height - 10);
            while (elementExists(xpath) == false) {
                action.press(width, startPoint).waitAction(Duration.ofSeconds(4)).moveTo(width, endPoint).release()
                        .perform();
            }
        } catch (Exception e) {
            e.printStackTrace();
        }

    }
		}