# AWS-S3-Static-hosting-with-reactapp-project-01
PROJECT on hosting a static website in aws cloud
AWS SERVICES USED :
1. AWS S3
2. AWS ROUTE 53
3. AWS CERTIFICATE MANAGER

## Useful commands

 * `npm run build`   compile typescript to js
 * `npm run watch`   watch for changes and compile
 * `npm run test`    perform the jest unit tests
 * `cdk deploy`      deploy this stack to your default AWS account/region
 * `cdk diff`        compare deployed stack with current state
 * `cdk synth`       emits the synthesized CloudFormation template

static website


A static website delivers content in the same format in which it is stored. No server-side
code execution is required. For example, if a static website consists of HTML
documents displaying images, it delivers the HTML and images as-is to the browser,
without altering the contents of the files.

Static websites can be delivered to web browsers on desktops, tablets, or mobile
devices. They usually consist of a mix of HTML documents, images, videos, CSS style
sheets, and JavaScript files. Static doesn’t have to mean boring—static sites can
provide client-side interactivity as well. Using HTML5 and client-side JavaScript
technologies such as jQuery, AngularJS, React, and Backbone, you can deliver rich
user experiences that are engaging and interactive.

Some examples of static sites include:

• Marketing websites
• Product landing pages
• Microsites that display the same content to all users
• Team homepages


Use Amazon S3 Website Hosting to Host Without a Single Web Server

Amazon Simple Storage Service (Amazon S3) can host static websites without a need
for a web server. The website is highly performant and scalable at a fraction of the cost
of a traditional web server. Amazon S3 is storage for the cloud, providing you with
secure, durable, highly scalable object storage. 

A simple web services interface allows
you to store and retrieve any amount of data from anywhere on the web.1
You start by creating an Amazon S3 bucket, enabling the Amazon S3 website hosting
feature, and configuring access permissions for the bucket.

After you upload files,
Amazon S3 takes care of serving your content to your visitors.
Amazon S3 provides HTTP web-serving capabilities, and the content can be viewed by
any browser. You must also configure Amazon Route 53, a managed Domain Name
System (DNS) service, to point your domain to your Amazon S3 bucket.


PROJECT ARCHITECTURE:

