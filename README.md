# arXiv-Bulk-Data-Download-AWS

**This is a very simple steps to Bulk Download arXiv data**

PDFs are available on S3 in the arxiv requester pays bucket. They are grouped into .tar files of \~500MB each (which we've found is a good size chunk). The complete set of PDFs is about 270GB, source files about 190GB, and we make about 40GB of additions/updates each month (2012-02). Examples keys for these files with the arxiv bucket are:



Get EC2 Instance on AWS 
**Install s3cmd command**

```sudo yum install s3cmd```

***In case you get an error like: No package s3cmd available.***
```sudo yum --enablerepo=epel install s3cmd```

**Download the whole bucket. Please note that you will be charged for the download traffic based on AWS pricing.** 

```s3cmd get --recursive --skip-existing s3://arxiv/src/ --requester-pays```

**Check the recent size of the bucket**

```s3cmd du -H s3://arxiv/src/ --requester-pays```

**List all files in the bucket**

```s3cmd ls -l s3://arxiv/src/ --requester-pays```
