# S3 AWS CLI Commands
## *mb* - make bucket (create bucket)
```
aws s3 mb s3://mys3bucket --region <aws-region>
aws s3 mb s3://mys3bucket --region us-west-2
```

## *s3api* - Create bucket using api
```
aws s3api create-bucket --bucket mys3bucket --region <aws-region> --create-bucket-configuration LocationConstraint=<aws-region>
```
### Sample Output
```
aws s3api create-bucket --bucket simples3staticwebsite.com --region ap-south-1 --create-bucket-configuration LocationConstraint=ap-south-1

	C:\Windows\system32>aws s3api create-bucket --bucket simples3staticwebsite.com --region ap-south-1 --create-bucket-configuration LocationConstraint=ap-south-1
	{
		"Location": "http://simples3staticwebsite.com.s3.amazonaws.com/"
	}
```
## *rb* - Remove/Delete bucket
```
aws s3 rb s3://mys3bucket
aws s3 rb s3://mys3bucket --force
```

## *ls* - List S3 objects
### Lists all of the bucket owned by the user
```
aws s3 ls
```
#### Sample Output
```
	C:\Windows\system32>aws s3 ls
	2020-04-13 15:29:14 simples3staticwebsite.com
	2020-04-12 16:11:17 www.simples3staticwebsite.com
	2020-04-11 22:33:45 www.venkiwebsite.com
```
### Lists objects under a specified bucket
```
aws s3 ls s3://mys3bucket
```

### Recursively list objects in a bucket, or list in human readable and summarize option
```
aws s3 ls s3://mys3bucket --recursive
aws s3 ls s3://mys3bucket --recursive  --human-readable --summarize
```


## *cp* Copy files
### Copying a local file "getdata.php" to S3 Bucket "mys3bucket"
```
aws s3 cp getdata.php s3://mys3bucket
```
### Copying a file "getdata.php" from S3 Bucket to local path "/local/dir/data"
```
aws s3 cp s3://mys3bucket/getdata.php /local/dir/data
```
### Copying a folder "/local/dir/data" recursively to S3 Bucket "mys3bucket"
```
aws s3 cp /local/dir/data s3://mys3bucket --recursive
```
### Copying S3 Bucket "mys3bucket" to local folder "/local/dir/data" recursively
```
aws s3 cp s3://mys3bucket/ /local/dir/data --recursive
```
### Copying a file from one S3 bucket to another S3 bucket
```
aws s3 cp s3://mys3bucket/init.xml s3://mybackups3bucket
```
### Copying a entire bucket contents from one S3 bucket to another S3 bucket
```
aws s3 cp s3://mys3bucket s3://mybackups3bucket --recursive
```

## *mv* - Move Files commands
```
aws s3 mv source.json s3://mys3bucket
aws s3 mv s3://mys3bucket/getdata.php /home/project
aws s3 mv s3://mys3bucket/source.json s3://mybackups3bucket
aws s3 mv /local/dir/data s3://mys3bucket/data --recursive
aws s3 mv s3://mys3bucket s3://mybackups3bucket --recursive
```

## *rm* - Remove files 
```
aws s3 rm s3://mys3bucket/queries.txt
aws s3 rm s3://mys3bucket --recursive
```

## *sync* - Sync files
```
aws s3 sync backup s3://mys3bucket
aws s3 sync s3://mys3bucket/backup /tmp/backup
aws s3 sync s3://mys3bucket s3://mybackups3bucket
```

### Sample Output
```
aws s3 sync s3://www.simples3staticwebsite.com s3://simples3staticwebsite.com

	C:\Windows\system32>aws s3 sync s3://www.simples3staticwebsite.com s3://simples3staticwebsite.com
	copy: s3://www.simples3staticwebsite.com/awss3.png to s3://simples3staticwebsite.com/awss3.png
	copy: s3://www.simples3staticwebsite.com/error.html to s3://simples3staticwebsite.com/error.html
	copy: s3://www.simples3staticwebsite.com/index.html to s3://simples3staticwebsite.com/index.html
	copy: s3://www.simples3staticwebsite.com/awss3bucket.png to s3://simples3staticwebsite.com/awss3bucket.png
	copy: s3://www.simples3staticwebsite.com/venki.png to s3://simples3staticwebsite.com/venki.png
	copy: s3://www.simples3staticwebsite.com/s32018.mp4 to s3://simples3staticwebsite.com/s32018.mp4
```


## s3 bucket website
```
aws s3 website s3://mys3bucket/ --index-document index.html --error-document error.html
```

## s3 presign url (default 3600 seconds)
```
aws s3 presign s3://mys3bucket/dnsrecords.txt
aws s3 presign s3://mys3bucket/dnsrecords.txt --expires-in 60
```
