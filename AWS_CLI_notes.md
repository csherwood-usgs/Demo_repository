## Notes on AWS CLI commands

Using multiple profiles:

For some reason, this works:

`aws s3 ls cmgp_bucket/dir --profile = profilename`

but the parallel syntax for `sync` does not. In Windows Powershell, you have to do this:

`setx AWS_PROFILE=profilename`

then shut down and reopen Powershell (honest!) then:

`aws s3 sync s3://cmgp_bucket/dir dest_folder`

(note the addition of `s3://`)

This works

`aws s3 ls s3://cmgp-upload-download-bucket/2022-09_FL/10020925/ --profile updown | tail`

CoastCam directory:  

`aws s3 ls s3://cmgp-coastcam/cameras/caco-01/new_products/products/1617298200.c1.snap.jpg --profile coastcam`  

This grabs all of the timex exposures:

`aws s3 cp s3://cmgp-coastcam/cameras/caco-02/products/ . --recursive --exclude "*" --include "*timex*" --profile coastcam`  

