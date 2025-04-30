### What is a HAR file?

A HAR file is a HTTP Archive format file. It captures all interactions that a web browser makes with a site. It is in JSON format and the extension is **.har**. It can be used for debugging performance and other web application issues that a user might be experiencing.


### How to generate a HAR file (Chrome / Edge )

1.     Right click on a web page and select **Inspect**

2.     Navigate to the **Network** tab on the Dev Tools pop out that appeared on either the bottom or the right-hand side of your screen. (Note: in Edge the network tab may be symbolized as a Wi-Fi icon)

3.     Check the **Preserve log** check box

4.     Uncheck the **Disable cache** check box if checked

5.     Click **Record network log** button on the top left of the Dev Tools pop out

6.     Refresh the web page or replicate the process that is causing issues

7.     After replicating the error while recording, stop the recording by clicking the same button that was pressed to start the recording

8.     Finally, click the download icon on the upper right-hand corner of the Dev Tools

### Security concerns with a HAR file

A concern with HAR files is it will all include requests your browser makes. This includes POST requests that will contain username and non-encrypted passwords. So be careful when sending a HAR file to someone.