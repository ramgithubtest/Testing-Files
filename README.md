import java.io.File;
import java.io.IOException;
import org.apache.commons.io.FileUtils;

import org.testng.annotations.Test;
public class TC_01 {
@Test
	public  void Google() throws InterruptedException, IOException  {
		System.setProperty("webdriver.chrome.driver", "C:\\chromedriver.exe");
		WebDriver driver=new ChromeDriver();
		driver.manage().window().maximize();
		driver.navigate().to("http://google.com");
		Thread.sleep(3000);
		File scrFile = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
		FileUtils.copyFile(scrFile, new File("D:\\Selenium Work Space\\Screenshots\\Screenshot1.jpg"));
		driver.quit();

	}

}
