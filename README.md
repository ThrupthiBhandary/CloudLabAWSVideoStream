# AWS Video Streaming Service

## Aim

To implement a cloud-based video streaming service using **Amazon S3, AWS Elemental MediaConvert, and Amazon CloudFront** for storing, processing, and delivering video content efficiently.

## Objective

The objective of this lab is to understand how AWS cloud services can be integrated to build a basic video processing and streaming pipeline.

The implementation demonstrates:

- Uploading and storing videos using Amazon S3
- Transcoding videos using AWS Elemental MediaConvert
- Storing processed videos in Amazon S3
- Delivering video content using Amazon CloudFront
- Accessing the processed video through a CloudFront distribution

---

## AWS Services Used

| AWS Service | Purpose |
|---|---|
| **Amazon S3** | Stores source and processed video files |
| **AWS Elemental MediaConvert** | Transcodes and processes the source video |
| **Amazon CloudFront** | Delivers processed video content through a CDN |

---

## Architecture

```text
                 User
                   |
                   v
              Amazon S3
            Source Video
                   |
                   v
        AWS Elemental MediaConvert
           Video Processing
                   |
                   v
              Amazon S3
          Processed Video
                   |
                   v
           Amazon CloudFront
          Content Delivery
                   |
                   v
            Video Player
```

---

# Lab Implementation

## Step 1: Create an Amazon S3 Bucket

1. Open the AWS Management Console.
2. Navigate to **Amazon S3**.
3. Create a new S3 bucket.
4. Upload the source video file to the bucket.
5. Create a suitable folder structure for source and processed videos.

Example:

```text
S3 Bucket
│
├── input/
│   └── source-video.mp4
│
└── output/
    └── processed-video/
```

---

## Step 2: Configure AWS Elemental MediaConvert

1. Open **AWS Elemental MediaConvert** from the AWS Management Console.
2. Create a new MediaConvert job.
3. Select the source video stored in Amazon S3 as the input.
4. Configure the required video output settings.
5. Specify an Amazon S3 location for the processed output.
6. Submit the MediaConvert job.
7. Wait for the job to complete successfully.

### Processing Flow

```text
Source Video
     |
     v
Amazon S3
     |
     v
MediaConvert
     |
     v
Transcoding
     |
     v
Processed Video
     |
     v
Amazon S3
```

---

## Step 3: Verify the Processed Video

After the MediaConvert job is completed:

1. Open the S3 bucket.
2. Navigate to the output location.
3. Verify that the processed video has been generated.
4. Confirm that the output files are available in Amazon S3.

---

## Step 4: Configure Amazon CloudFront

1. Open **Amazon CloudFront**.
2. Create a new CloudFront distribution.
3. Configure the S3 bucket as the origin.
4. Configure the required distribution settings.
5. Create the distribution.
6. Wait for the distribution to become deployed.
7. Copy the CloudFront distribution domain name.

Example:

```text
https://<cloudfront-distribution-domain>/processed-video.mp4
```

The processed video can then be accessed through the CloudFront distribution.

---

# Complete Workflow

```text
1. Upload Source Video
          ↓
2. Amazon S3
          ↓
3. AWS Elemental MediaConvert
          ↓
4. Video Transcoding
          ↓
5. Processed Video
          ↓
6. Amazon S3
          ↓
7. Amazon CloudFront
          ↓
8. Video Delivery
          ↓
9. Video Player / User
```

---

# Technologies Used

- **Amazon Web Services (AWS)**
- **Amazon S3**
- **AWS Elemental MediaConvert**
- **Amazon CloudFront**
- **Video Streaming**
- **Content Delivery Network (CDN)**

---


# Result

The video was successfully:

1. Uploaded and stored in Amazon S3.
2. Processed and transcoded using AWS Elemental MediaConvert.
3. Stored as processed output in Amazon S3.
4. Delivered through Amazon CloudFront.
5. Accessed using the CloudFront distribution domain.

---

# Learning Outcomes

After completing this lab, the following concepts were understood:

- Cloud-based object storage using **Amazon S3**
- Video transcoding using **AWS Elemental MediaConvert**
- CDN-based content delivery using **Amazon CloudFront**
- Integration of multiple AWS services in a single workflow
- Basic video streaming architecture on AWS
- Source and processed media management
- Cloud-based media delivery and distribution

---

# Conclusion

This lab demonstrates how AWS services can be combined to build a basic cloud-based video streaming pipeline. **Amazon S3** provides scalable storage, **AWS Elemental MediaConvert** handles video processing and transcoding, and **Amazon CloudFront** provides efficient content delivery to users.

The implementation provides practical experience in integrating cloud storage, media processing, and CDN services to deliver video content through the AWS cloud.
