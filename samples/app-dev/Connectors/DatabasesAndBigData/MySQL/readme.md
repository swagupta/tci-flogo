# MySQL CRUD Example


## Description

This example demonstrates how we can create and use MySQL CRUD activities.
MySQL CRUD app bascially contain 4 activities. The main purpose of these activities are:
a) To fetch data using Query activity.
b) To insert data using Insert activity.
c) Update the data using Update activity.
d) Delete the data using Delete activity from MySQL database.

## Prerequisites

1. Ensure that MySQL database must be install either on local computer or on AWS EC2 instance.
2. You need to make sure that your public ip is whitelisted (If you are using database hosted on AWS EC2 instance).
3. In order to use on-prem database server in TCI, you will have to attach Access Key to use Hybrid Connectivity.
   For more details on how to use Hybrid Connectivity/tibtunnel/Proxy Agent, please refer this TCI documentation - [Link](https://integration.cloud.tibco.com/docs/#tci/using/hybrid-agent/installing-configuring-running-agent.html%3FTocPath%3DUsing%2520TIBCO%2520Cloud%25E2%2584%25A2%2520Integration%7CUsing%2520the%2520TIBCO%2520Cloud%25E2%2584%25A2%2520Integration%2520-%2520Hybrid%2520Agent%7C_____4)

## Import the sample

1. Download the sample json file i.e., MySQLSSLCRUD.json.

2. Create a new empty app

![Create an app](../../../import-screenshots/mysql_docs_screenshot/1.png)

3. On the app details page, select import app option.

![Select import](../../../import-screenshots/mysql_docs_screenshot/2.png)

4. Now click on ‘browse to upload’ button and select the app.json from your machine that you want to import.

![Import your sample](../../../import-screenshots/mysql_docs_screenshot/3.png)

5. Click on Upload Button. The Import app dialog displays some generic errors and warnings as well as any specific errors or warnings pertaining to the app you are importing.

![The Import app dialog](../../../import-screenshots/mysql_docs_screenshot/4.png)

6. In Import App dialog, there are 2 options to import:

* Selective Import – If you are choosing this option then select trigger, flow and connection and click Next.

* Import all – If you are choosing this option then it will import all flows from the source app.

7. After importing app is done, in connection tab make sure to re-enter the password and click on connect button to establish the connection.

## Understanding the configuration

### The Connection

When you import the app you need to re-enter the password and establish the connection.

![The connection](../../../import-screenshots/mysql_docs_screenshot/6.png)
![The connection](../../../import-screenshots/mysql_docs_screenshot/7.png)
![The connection](../../../import-screenshots/mysql_docs_screenshot/8.png)

In the connection, note that,
1. Host - In this field we give public ip/public DNS of EC2 instance on which database is hosted.
2. Maximum Connection Retry Attempts - Maximum number of attempts to reconnect with a database server in case connection failure. Default value is 3
3. Connection Retry Delay - Number of seconds to wait between connection retry attempts. Default value is 5 sec.
4. Secure Connection - Establishes the secure connection when set to True.

TLS: Select the TLS mode from the list.

The following certificates for each TLS mode:

CA Certificate: Certificate Authority (CA) certificate.

Client Certificate: Not required. Client Certificate file for connections requiring client authentication.

Client Key: Not required. Client key file used for connections requiring client authentication.
 

### The Flow

If you go inside the app, you can see in flow we have 4 activities (Query,Insert, Update and Delete) that perform some operations.
Also in flow we have Log Message and Return Activity for getting the output.

![Sample Response](../../../import-screenshots/mysql_docs_screenshot/9.png)

### Run the application
For running the application, first you have to push the app and then scale up the app.
Then after sometime you can see your app in running status.

![Sample Response](../../../import-screenshots/mysql_docs_screenshot/10.png)
![Sample Response](../../../import-screenshots/mysql_docs_screenshot/11.png)
![Sample Response](../../../import-screenshots/mysql_docs_screenshot/12.png)
Once your app reaches to Running state, go to Endpoints and for GET/tasks, select 'Try it Out’ option and then click on execute.

Another option, If you want to test the sample in the Flow tester then follow below instructions:
 
in flow, click on Test Button -> create Launch configuration -> click Next button -> click on Run

![sample Response](../../../import-screenshots/mysql_docs_screenshot/13.png)
![Sample Response](../../../import-screenshots/mysql_docs_screenshot/14.png)
![Sample Response](../../../import-screenshots/mysql_docs_screenshot/15.png)

## Outputs

1. Flow Tester

![Sample Response](../../../import-screenshots/mysql_docs_screenshot/16.png)

2. When hit endpoints

![Sample Response](../../../import-screenshots/mysql_docs_screenshot/17.png)


## Troubleshooting

* If you do not see the Endpoint enabled, make sure your apps is in Running status.
* If you see test connection failed in connection tab, then check your public ip if it is whitelisted or not.

## Contributing
If you want to build your own activities for Flogo please read the docs here.

If you want to showcase your project, check out [tci-awesome](https://github.com/TIBCOSoftware/tci-awesome)

You can also send an email to `tci@tibco.com`

## Feedback
If you have feedback, don't hesitate to talk to us!

* Submit feature requests on our [TCI Ideas](https://ideas.tibco.com/?project=TCI) or [FE Ideas](https://ideas.tibco.com/?project=FE) portal
* Ask questions on the [TIBCO Community](https://community.tibco.com/answers/product/344006)
* Send us a note at `tci@tibco.com`

## Help
Please visit our [TIBCO Cloud<sup>&trade;</sup> Integration documentation](https://integration.cloud.tibco.com/docs/) and TIBCO Flogo® Enterprise documentation on [docs.tibco.com](https://docs.tibco.com/) for additional information.

## License
This TCI Flogo SDK and Samples project is licensed under a BSD-type license. See [license.txt](license.txt).

