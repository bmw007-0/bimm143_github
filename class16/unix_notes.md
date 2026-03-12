## Basic Unix

Some important file system commands include

pwd:    Print working directory
ls:     List files and folders
cd:     Change Directory
mkdir:  Make a new Directory
rm:     Delete files and directories
nano:   A very basic text editor that is always available 
less:   To view/read text files page by page (pager program)

My AWS instance: 
ssh -i ~/Downloads/bimm143_bmw.pem ubuntu@ec2-54-201-11-176.us-west-2.compute.amazonaws.com

To copy from my AWS instance

scp -i ~/Downloads/bimm143_bmw.pem ubuntu@ec2-54-201-11-176.us-west-2.compute.amazonaws.com:~/work/results.tsv .  

## Class 17 AWS Instance Address
ssh -i ~/Downloads/bimm143_bmw.pem ubuntu@ec2-44-255-68-110.us-west-2.compute.amazonaws.com


scp -r -i ~/Downloads/bimm143_bmw.pem ubuntu@ec2-44-255-68-110.us-west-2.compute.amazonaws.com:~/*_quant .
