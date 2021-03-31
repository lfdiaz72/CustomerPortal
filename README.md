# LDiazPlatform
 Platform Demo - Customer Center Experience

 Setup your Box custom application

* In your Box demo account, open developer console and create a JWT application 
* Ensure that you:  
* Set the scope to enterprise if you want to login with managed users - although this is a platform demo, managed users are easier to 'manage' :-) 
* 		The demo can work with app users - please contact pchristensen@box.com if you prefer this 
* Set the 'Generate tokens for users' Advanced Feature 
* Set the CORS: http://0.0.0.0:8000,  https://box-java-sandpit.herokuapp.com 
* Also add https://your github user name.github.io if you chose to use GitHub for your platform demo 
* Save changes 
* Approve the app in the admin console(!!!) 

* Click the 'Generate a Public/Private Keypair' button to generate the JWT Config file with a private key. This might force you to setup 2FA for your demo account if you haven't already. Follow the steps to setup 2FA and go back to the JWT Application and click the button again. This time it should download a file that looks like the below and is named similar to this '47767585_dvu8fau9_config.json' 

Make a note of the 'clientId' as you will need it in the next section
(You can now turn off 2FA again if you don't want it on)

Configure your demo application

* Go to this URL https://box-java-sandpit.herokuapp.com/register.html to register your JWT application with the platform demo token generator.  
* PLEASE ONLY STORE DEMO AND DEVELOPER ACCOUNTS HERE, NO CUSTOMER ACCOUNTS 
* Fields explained: 
* Display name: Only used by me to identify your registration so enter 'My platform demo' but substitute 'My' for your own name or chosen identifier. 
* Email: Your box email address (again, only for me to be able to see who registered a specific app, not for logging into the app itself) 
* Password: This will be the password you use to login to the platform application. Remember, this is using JWT to login so we cannot use your managed user password. The password you enter here will be used for all users logging into the application. It is mainly to have a password and mimic an identity management system when demoing. Please don't use '&' or '#' characters! 
* File: Your JWT config file INCLUDING private key etc. that you downloaded  in a previous step 
* Successful registration will result in an email being send to your registered email with the registration details 
* The JWT file is stored in a database under my AWS account. Let me know if you have any questions regarding this 

Let the magic happen
* Using a text editor (I recommend https://atom.io or https://code.visualstudio.com/ but you can use the built-in TextEdit as well), open the config.json file in the template2.0 directory  
* If you setup using GitHub the file is located in 
* /Users/your mac user name/Documents/GitHub/your github user name.github.io/template2.0 
* If you setup without GitHub the file is located in
* cd /Users/your mac user name/Documents/Platform demo/template2.0 
* Add your clientId from the JWT config file you registered above replacing the existing value. 

* 		
￼
*  
* 		 
* Open a terminal window 

* Change directory to the directory that contains the platform demo (where you setup GitHub or where you unzipped the template folder).  
* If you setup using GitHub: 
* cd /Users/your mac user name/Documents/GitHub/your github user name.github.io 
* If you setup without GitHub 
* cd "/Users/your mac user name/Documents/Platform demo" 
* for me it would look like this:  
* cd /Users/pchristensen/Documents/GitHub/pchristensenb.github.io 
* 		or 
* cd "/Users/pchristensen/Documents/Platform Demo" 

* 		
￼
*  
* Run a local web server. Here I use python as it is pre-installed on your mac. By default python uses 0.0.0.0:8000 for the local web server which is why we added this address to the CORS settings earlier. If you want to use a different web server or address/port please update the CORS entries accordingly. 

* To run the local web server simply copy the command from here and paste into your terminal window (either one of these should work on any mac, if you are on Windows you can check with scrisp@box.com, our resident Windows man) 
* python -m SimpleHTTPServer 
* python3 -m http.server 

* 		
￼
*  
* 		(if you see an 'Operation not permitted' error when trying to run the python command please contact Peter, El or Sam as there is a simple workaround for this) 
* 		 
* If you see a Mac popup asking you to Allow or Deny incoming traffic choose Deny 

* Open a browser to http://0.0.0.0:8000/template2.0/login.html - login with the email of a user account from your demo account and the password you registered earlier and you should see the below, Click folder1 and you should see the root folder of the user you are logged in as. (If you get an error during login or when you try to open the folder please let me know and I can help) 

* 		
￼
*  

What next...time to configure and brand your demo for the customer use case. (If you are doing the skills lab in SE Summit you will not need to do this as this will be the subject of the actual session so you are good to go - well done)
