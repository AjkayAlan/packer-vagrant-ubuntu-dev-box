# packer-vagrant-ubuntu1804-dev-box
Creates a base developer box with Packer that can be extended upon. Installs a gui, some nice IDE's, and a fair bit of programming languages.

** This project assumes you are using Windows due to Hyper-V.

## Computer Setup

1. Install Hyper-V (by running the following in an admin PowerShell session):
```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
```

2. Install Vagrant (via Chocolatey):
```
choco install vagrant
```

3. Install Packer (via Chocolatey):
```
choco install packer
```

4. Install needed plugins:
```
vagrant plugin install vagrant-env
```

## Building
CD to the repo root, and run the build script!
```
./scripts/build.ps1
```

## Adding The Box
After building, you can add it to be used by your future projects by running the following (note this is based on how I have named my box):
```
./scripts/add.ps1
```

## Testing The Box
After you have added the box to your machine, you can make a small [vagrantfile that you can use. Note for this specific image, it is setup to use [enhanced mode](https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/learn-more/use-local-resources-on-hyper-v-virtual-machine-with-vmconnect). You need to enable it on your system after booting the instance:
```
./scripts/run.ps1
```