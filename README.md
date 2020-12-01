# DevOps Engineer Exercises

## Introduction
Thank you for your interest in the DevOps Engineer role here at Liferay, Inc. These exercises are intended to help evaluate a candidate’s critical thinking, writing skill, creativity, and empathy. Each exercise will require exercising a combination of those skills.

*Liferay Portal CE is an Open Source platform that is available for anyone to use under the LGPL license. All releases can be downloaded at https://sourceforge.net/projects/lportal/files/Liferay%20Portal/ . Documentation can be found at:
Liferay 7.2: https://help.liferay.com/hc/categories/360001749912
Liferay 7.3: https://learn.liferay.com/dxp/7.x/en/index.html*

## Exercise 1 - Upgrade Liferay Portal
A common task for the DevOps Engineer position is to help upgrade existing installations of Liferay Portal (or Liferay DXP) to the newest versions. This exercise simulates the process of running an older version of Liferay Portal and then upgrading to a newer version. Follow these steps:
1. Use Docker and Docker Compose to run an instance of Liferay Portal CE 7.2
	1. Download this Liferay Workspace, and run `docker-compose up` from the root folder to start up a container for Liferay Portal and a MySQL database.
2. Use the Liferay Portal to create a website
	1. Go to http://localhost:8080 and sign in using the email `test@liferay.com` and the password `test`.
	2. Add a new display page template for a basic document (Site Builder -> Pages -> Display Page Templates). Make sure to add at least one fragment to the page.
	3. Add a new document (Content & Data -> Documents and Media) and select the display page template you created in the above step as the Specific Display Page Template for this document.
	4. Create a new content page (Site Builder -> Pages) and add a Documents and Media widget to the page. Publish the page. Notice that when you view the page, you see a link for the document you added above. When you click on the link, it takes you to the display page template you created in the first step.
3. Deploy a custom module
	1. From the root of you Liferay Workspace, run `./gradlew deploy`.
	2. You should see in the logs your modules being deployed and registered.
	3. Add your newly deployed module to the home page. This is a replacement for the standard `Hello World` portlet that also shows the URL of your new favorite website, www.liferay.com. The new portlet is named `Hello World Test`.
4. Upgrade the site to Liferay Portal CE 7.3
	1. Shut down your docker containers and uncomment the line in the Docker Compose file which will point to the newer version of Liferay Portal.
	2. Run  `docker-compose up` again and ensure that the automatic database upgrade completes successfully.
	3. Ensure that no data or content has been lost in the upgrade process.
	4. Document any roadblock you find in the upgrade process and the approach you took to try to solve it.
	5. If you have time, research the status for any possible problems you found in the upgrade by searching on https://issues.liferay.com.

Make sure to submit your exercise with the document about roadblocks even if you don’t have the time to completely finish the upgrade process.

## Exercise 2 - Upgrade code
Inside of the Liferay Workspace there is a custom Liferay module that you deployed in the first exercise. This module was developed for 7.2 and needs to be upgraded to 7.3.
1. Describe the steps you would take to do the upgrade and ensure that it works properly.
2. If you have the time and knowledge necessary, attempt to upgrade the code and document the steps you took, the challenges you found and your approach you took to solve them.
	1. Please, submit this information even if you don’t finish the upgrade. The process you took is more important to us than the end result, since the time you have for the exercise is very limited.

