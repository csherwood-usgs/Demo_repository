Notes on getting set up

Prerequisites:
* CHS log-in (must request from XXX)
* Log-in is accociated with an account that must be fed money via local AO
* Access is only from TIC or PulseSecure VPN

Login is via `http://awsconsole.usgs.gov` (not https !). This can be sketchy...and won't always connect reliably.
IE works better than Chrome, but gives a warning that can be fixed according to this: 
https://aws.amazon.com/premiumsupport/knowledge-center/ec2-windows-file-download-ie/

Once you are logged in and looking at the AWS console:
* Create a key pair. Required for connecting to EC2 instances. Each instance needs to use a key pair, and they are assigned when you
create the instance. It is possible to change keys associated with an instance, but not straightforward and probably not something we
should plan on.
* Choose (or create a new) Security Group (SG). More info: https://cloudacademy.com/blog/aws-security-groups-instance-level-security/
My understanding is that we only need a few of these, but they are somewhat specific to the type of access the instance will require.
I created two: one for SSH access (best for Linux), and one for RDP access (best for Windows).
* 
