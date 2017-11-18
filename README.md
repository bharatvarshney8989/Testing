# Testing
Appium practices scripts:
#Google chrome #open whatspp in mobile using appium


package testing;
import java.net.MalformedURLException;
import java.net.URL;

import org.openqa.selenium.WebDriver;
//import org.openqa.selenium.remote.CapabilityType;
import org.openqa.selenium.remote.DesiredCapabilities;
import org.openqa.selenium.remote.RemoteWebDriver;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;
import io.appium.java_client.remote.MobileCapabilityType;
public class GoogleChrometest {
	
	WebDriver driver;
	@BeforeTest
		public void setUp() throws MalformedURLException{
		//Set up desired capabilities and pass the Android app-activity and app-package to Appium
		DesiredCapabilities capabilities = new DesiredCapabilities();
		capabilities.setCapability(MobileCapabilityType.BROWSER_NAME, "chrome");
		//capabilities.setCapability("BROWSER_NAME", "chrome");
		capabilities.setCapability("VERSION", "5.1.1"); 
		capabilities.setCapability(MobileCapabilityType.DEVICE_NAME,"9628c41e");
		//capabilities.setCapability("deviceName","9628c41e");
		capabilities.setCapability("platformName","Android");
	 	capabilities.setCapability("appPackage", "com.android.chrome");
	// This package name of your app (you can get it from apk info app)
		//capabilities.setCapability("appActivity","org.chromium.chrome.browser.document.ChromeLauncherActivity"); // This is Launcher activity of your app (you can get it from apk info app)
		capabilities.setCapability("appActivity","com.google.android.apps.chrome.Main");
	//Create RemoteWebDriver instance and connect to the Appium server
	 //It will launch the Calculator App in Android Device using the configurations specified in Desired Capabilities
	   driver = new RemoteWebDriver(new URL("http://127.0.0.1:4723/wd/hub"), capabilities);
	}
	@Test
	public void Login(){
		//driver.findElement(By.xpath("//android.widget.EditText[contains(@resource-id,'com.android.chrome:id/search_box_text')]")).click();// click on search button
		driver.get("http://www.whatsapp.com/");
	}
	
	@AfterTest
	public void end()
	{
	driver.quit(); //Close application
	}
	}
	






