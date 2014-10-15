# FreeBSD EC2 Build

This is a git clone of the SVN subdirectory here:
 * http://svnweb.freebsd.org/base?view=revision&revision=261953

Here are the original instructions on using the code in this repo:

```bash
# Keys to my AWS account
export AWS_CONFIG_FILE=aws-keys.conf

# Release configuration
export REL=10.0-RELEASE
export REPO=http://people.freebsd.org/~gjb/$REL/
export HASH_AMD64=9c377b4a4e63443c0b210080694de26133e6a276eddb07c7e00e1c9aebd84109
export HASH_I386=2c09643b3f79c703e424c03408882369025cec655c24a6d81ee073081ee75ebc
export TARGET_REGIONS="us-east-1 us-west-1 us-west-2 eu-west-1 ap-southeast-1 ap-northeast-1 sa-east-1 ap-southeast-2"
export BUILD_REGION="US-W2"

# Build FreeBSD disk images
. s-build-disks

# Build Amazon Machine Images from our disk images
. s-build-images

# Copy AMIs to all the other regions
. s-copy-images

# Test images
. s-test-images

# Publish images
. s-publish-images
```