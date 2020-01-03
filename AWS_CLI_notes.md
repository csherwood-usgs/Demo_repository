## Notes on AWS CLI commands

Using multiple profiles:

For some reason, this works:

`aws s3 ls cmgp_bucket/dir --profile = profilename`

but the parallel syntax for `sync` does not. In Windows Powershell, you have to do this:

`setx AWS_PROFILE=profilename`

then shut down and reopen Powershell (honest!) then:

`aws s3 sync s3://cmgp_bucket/dir dest_folder`

(note the addition of `s3://`)
