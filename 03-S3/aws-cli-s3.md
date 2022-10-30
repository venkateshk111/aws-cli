# S3 AWS CLI Commands
## s3 make bucket (create bucket)
```
aws s3 mb s3://mys3bucket --region <aws-region>
aws s3 mb s3://mys3bucket --region us-west-2
```

## S3 Create bucket using api
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
## s3 remove bucket
```
aws s3 rb s3://mys3bucket
aws s3 rb s3://mys3bucket --force
```

## s3 ls commands
```
aws s3 ls
aws s3 ls s3://mys3bucket
aws s3 ls s3://mys3bucket --recursive
aws s3 ls s3://mys3bucket --recursive  --human-readable --summarize
```
### Sample Output
```
	C:\Windows\system32>aws s3 ls
	2020-04-13 15:29:14 simples3staticwebsite.com
	2020-04-12 16:11:17 www.simples3staticwebsite.com
	2020-04-11 22:33:45 www.venkiwebsite.com
```

## s3 cp commands
```
aws s3 cp getdata.php s3://mys3bucket
aws s3 cp /local/dir/data s3://mys3bucket --recursive
aws s3 cp s3://mys3bucket/getdata.php /local/dir/data
aws s3 cp s3://mys3bucket/ /local/dir/data --recursive
aws s3 cp s3://mys3bucket/init.xml s3://mybackups3bucket
aws s3 cp s3://mys3bucket s3://mybackups3bucket --recursive
```

## s3 mv commands
```
aws s3 mv source.json s3://mys3bucket
aws s3 mv s3://mys3bucket/getdata.php /home/project
aws s3 mv s3://mys3bucket/source.json s3://mybackups3bucket
aws s3 mv /local/dir/data s3://mys3bucket/data --recursive
aws s3 mv s3://mys3bucket s3://mybackups3bucket --recursive
```

## s3 rm commands
```
aws s3 rm s3://mys3bucket/queries.txt
aws s3 rm s3://mys3bucket --recursive
```

## s3 sync commands
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
