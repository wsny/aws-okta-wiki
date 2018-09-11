# Debian/Ubuntu from packagecloud.io

We publish `apt-get install`able .debs on packagecloud.io.

**Warning: `curl`ing to `bash` has all the usual caveats.** [packagecloud has more detailed instructions.](https://packagecloud.io/segment/aws-okta/install#bash-deb)

```
curl -s https://packagecloud.io/install/repositories/segment/aws-okta/script.deb.sh | sudo bash
apt-get install -y aws-okta
```

# Fedora from packagecloud.io

**Warning: `curl`ing to `bash` has all the usual caveats.** [packagecloud has more detailed instructions.](https://packagecloud.io/segment/aws-okta/install#bash-rpm)

```
curl -s https://packagecloud.io/install/repositories/segment/aws-okta/script.rpm.sh | sudo bash
yum install -y aws-okta
```

# Linux binaries

(Our Github release page)[https://github.com/segmentio/aws-okta/releases] has binaries.

```
curl -LOs https://github.com/segmentio/aws-okta/releases/download/${version}/aws-okta-${version}-linux-amd64
```

# macOS binaries

(Our Github release page)[https://github.com/segmentio/aws-okta/releases] has binaries.

```
curl -LOs https://github.com/segmentio/aws-okta/releases/download/${version}/aws-okta-${version}-darwin-amd64
```
