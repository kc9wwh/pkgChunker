![pkgChunker Logo](https://kc9wwh-media.s3.us-east-2.amazonaws.com/pkgChunker/pkgChunker-logo_256.png)

## Summary
**pkgChunker** was developed to address an limitation of the Jamf Cloud Distribution Service (JCDS) where packages larger than 20GB are not able to be distributed to clients. However with this utility, you can easily *chunk* the *parent* package into smaller *child* flat packages that can be uploaded directly into Jamf Pro and distributed via a single policy. All the logic is included in the *child* packages to reassemble once all pieces are present and complete the install of the *parent* package.

## Usage
Using the utility is quite simple. 
1. Download and install **pkgChunker** from [here](https://github.com/kc9wwh/pkgChunker/releases)
2. Open Terminal
3. Execute `pkgChunker -p {pathToParentPackage} -o {outputDirectory}`
4. Upload *child* packages from output directory
5. Create a Policy that includes all *child* packages
6. Scope to target computers

```
josh.roskos@MarvinsDepressedMBP:~/Desktop/PkgChunker$ ./pkgChunker 
both -p and -o are required options and need to be provided
pkgChunker [-h] [-p pathToPkg] [-o /path/to/output] -- program to split large pkg's into chunks for the JCDS

where:
	-h shows this help information
	-p specify the package to be chunked
	-o specify the output location for chunked packages
```

## Known Limitations
- This utility only support flat *parent* packages at this time, but support for non-flat packages is planned
- This utility does not current support passing additional arguments to `/usr/sbin/installer` including the use of `-applyChoiceChangesXML`

## Support
For any issues with this utility, please open an *Issue** on this repo and for any questions, please either open an *Issue* or reach out in the MacAdmins Slack channel **[#pkgchunker](https://macadmins.slack.com/messages/CMSCC6XB7)**