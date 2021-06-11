# DeepLens
This repository has all the necessary Python files, to run a face detection model on AWS DeepLens device.

To setup, you need to register your DeepLens camera to your AWS Account. Then you would need to deploy a Face Detection project onto the DeepLens camera. The Lambda function that is deployed on the DeepLens camera is the greengrassHelloWorld.py file.

The greengrassHelloWorld.py file will has an event that will trigger in the case that a person walks in front of the camera. The DeepLens camera will detect take a snapshot of the individual and send it to an S3 Bucket.

The face_function.py will be deployed on another lambda function which will then trigger its event when the S3 bucket has an image uploaded to it. The face_function.py will use AWS Rekognition in order to compute the various metrics about their individual such as the confidence interval of the person's emotions. This confidence data will then be sent to an AWS RDS.
