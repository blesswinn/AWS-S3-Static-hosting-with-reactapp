# AWS-S3-Static-hosting-with-reactapp-project-01
PROJECT on hosting a static website in aws cloud
AWS SERVICES USED :
1. AWS S3
2. AWS ROUTE 53
3. AWS CERTIFICATE MANAGER

Before starting buy your own domain name & domain shoulde be same as that of the buckets your 
are creating in further stages of your project.

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


![Screenshot 2023-08-06 165608](https://github.com/blesswinn/AWS-S3-Static-hosting-with-reactapp/assets/113033635/f6f58c4e-d1b6-4f46-92d8-f6b2b023b9bb)

Step 0:

Create react app directory anywhere using terminal,
ie :  npx create-react-app appname

Step 1:

create 2 buckets in aws s3.
aslo disable the public acess settings

![Screenshot 2023-08-06 170400](https://github.com/blesswinn/AWS-S3-Static-hosting-with-reactapp/assets/113033635/ea86adc8-2700-4ca9-b264-6fe9ccbb4bf0)

followed by uploading of the files u created for your react app:


![Screenshot 2023-08-06 170528](https://github.com/blesswinn/AWS-S3-Static-hosting-with-reactapp/assets/113033635/4112e596-f830-4bb6-a841-d321598dda41)


Step 2: 

Enable static website hosting
After you create a bucket, you can enable static website hosting for your bucket.

To enable static website hosting
* Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/.
* In Index document, enter the file name of the index document, typically index.html.
* Choose Save changes.
* Amazon S3 enables static website hosting for your bucket. At the bottom of the page, under Static website hosting, you see the website endpoint for your 
  bucket.Under Static website hosting, note the Endpoint.The Endpoint is the Amazon S3 website endpoint for your bucket. After you finish configuring your 
  bucketasa static website, you can use this endpoint to test your website.
* To accept the default settings and create the bucket, choose Create.

 
in s3-buckets-proprties-static hosting: 

![Screenshot 2023-08-06 170929](https://github.com/blesswinn/AWS-S3-Static-hosting-with-reactapp/assets/113033635/015935d5-2c9b-4949-b356-694abdd8f4b0)

do this for both the buckets created www and the normal one.

Step 3:

Add a bucket policy that makes your bucket content publicly available

bucket policy code :

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::Bucket-Name/*"
            ]
        }
    ]
}

```

paste and save changes.

Step 4:

add routing settings :

* simple routing.
* define simple record (2)
* create records


![Screenshot 2023-08-06 171856](https://github.com/blesswinn/AWS-S3-Static-hosting-with-reactapp/assets/113033635/41e80c06-af95-46df-8c0b-07ef39c63b5d)

Step 5:

add certificates and validate them using AWS certificate manager.

![Screenshot 2023-08-06 172054](https://github.com/blesswinn/AWS-S3-Static-hosting-with-reactapp/assets/113033635/8ba97a27-b0b9-46ad-a23f-a108dcb82e53)

![Screenshot 2023-08-06 172043](https://github.com/blesswinn/AWS-S3-Static-hosting-with-reactapp/assets/113033635/3ad28bfe-c09d-4f64-9020-2c7d86352966)

step 5:
Browse the site using your domain which is hosted in aws S3
domain : www.blesswindevops.click


THANK YOU!!.

