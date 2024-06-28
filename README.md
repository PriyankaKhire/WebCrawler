# WebCrawler
## Creating lambda function and adding source trigger
- Follow the [video](https://www.youtube.com/watch?v=xyHLX1dUwuA&ab_channel=BeABetterDev) to setup lambda
  - The video also tells how to add source trigger to lambda function.
- If you make any changes to the code, don't forget to hit the deploy button to save the changes.
  ![deploy button](https://github.com/PriyankaKhire/WebCrawler/assets/12015512/099e34bc-f02d-4a40-819d-6a07bc91fd06)
- Currently I have added 2 source triggers for lambda
  - SQS Queue
  - SNS topic
### SQS vs SNS
- [AWS SNS vs. SQS - What Are the Main Differences?](https://blog.awsfundamentals.com/aws-sns-vs-sqs-what-are-the-main-differences)
- [Comparing AWS SNS and SQS](https://ably.com/topic/aws-sns-vs-sqs)
### Reasons why we will be useing SNS as source trigger
- Functionality of lambda
  1. A message arrives through source trigger
  2. Lambda opens the message and processes it
  3. Lambda then sends message to destination.
- If we want lambda to have a destination the source of invocation needs to be asynchronous.
  - Since SQS is NOT an asynchronous invocation we cannot use it.
  - Thus we use SNS.
## Add destination trigger
- This is a good [video](https://www.youtube.com/watch?v=r2BbMuZ_Ip8&ab_channel=BeABetterDev) showing how to add destinations
- However I didn't end up using destination trigger, I added boto3 dependencies and sent messages.
## Adding BeautifulSoup dependency to lambda to scrape the webpage
- Follow this [video](https://www.youtube.com/watch?v=grRW1Z_C9vw&ab_channel=TechwithHitch) to get general idea on how to create layers.
- Since I am using windows, I opened pycharm and it already creates virtual environment for every new project.
  - I installed beautifulsoup4 and requests using pip and created zip file as instructed in the video.
  - Followed [this](https://docs.aws.amazon.com/lambda/latest/dg/packaging-layers.html) webpage to know what the path should be.

