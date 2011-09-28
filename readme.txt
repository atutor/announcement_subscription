This module installs the following into the file /editor/add_news.php:

	/***** 
	* Added by announcement_subscription: Send mail to announcement subscribers 
	*/

	 $subscriberMod =& $moduleFactory->getModule('announcement_subscription'); 
	 if ($subscriberMod->isEnabled() && !$subscriberMod->isMissing()) { 
		 include_once(AT_MODULE_PATH . 'announcement_subscription/sendmail.php'); 
	 } 

	/***** 
	* End announcement_subscription 
	*/ 
	
These lines are added immediately after the line 

  if (!$msg->containsErrors() && (!isset($_POST['setvisual']) || isset($_POST['submit']))) {

which should be around line 70 of the file. add_news.php needs to be writable for this module
to install properly - if the file is unwritable you will need to change the file permissions
before installing the mod. There are different ways to do this depending on the web server software,
please see the web server documentation for details. 

In some case the code change may not be possible, and will require you to edit the add_news.php file manually. Check the file
to see if the code update occurred after the line above, and if not code into the file yourself.


To learn more about file permissions, see http://en.wikipedia.org/wiki/Permissions
