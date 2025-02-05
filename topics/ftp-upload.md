[//]: # (title: FTP Upload)
[//]: # (auxiliary-id: FTP Upload)
FTP Upload allows deploying files/directories to an FTP server.
 
The settings common for all runners are described in [Configuring Build Steps](configuring-build-steps.md); this page details the FTP Upload settings. 

The fields below support [parameter references](predefined-build-parameters.md): any text between percentage signs (`%`) is considered a reference to a property by TeamCity. To prevent TeamCity from treating the text in the percentage signs as a property reference, use two percentage signs to escape them: for example, if you want to pass "`%Y%m%d%H%M%S`" into the build, change it to "`%%Y%%m%%d%%H%%M%%S`".

<table><tr>

<td>

Option

</td>

<td>

Description

</td></tr><tr>

<td>

__Deployment Target__

</td></tr><tr>

<td>

Target host

</td>

<td>

Specify an FTP server (usehostname or IP address) and a remote directory (relative to the FTP user's home).

To use an absolute `*nix` path, use `%2F` as the forward slash. For example:

```Shell
ftp://hostname.com/hostname.com:34445/subdir127.0.0.1/%2Fetc/

```


</td></tr><tr>

<td>

Secure connection

</td>

<td>

Choose between an insecure (FTP) and a secure connection (FTPS, FTPES).


</td></tr><tr>

<td>

__Deployment Credentials__

</td></tr><tr>

<td>

Authentication method

</td>

<td>

Select either _Anonymous_ (will submit username `anonymous` and a single space as the password) or _username/password_ (for custom credentials)

</td></tr><tr>

<td>

__FTP modes__

</td></tr><tr>

<td>

FTP Mode

</td>

<td>

Select the passive or active mode

</td></tr><tr>

<td>

Transfer Mode

</td>

<td>

Optional. Select an FTP transfer mode to force:  the ASCII or Binary FTP transfer modes (if the automatically detected mode leads to broken files transfer)

</td></tr><tr>

<td>

__Deployment Source__

</td></tr><tr>

<td>

Paths to sources

</td>

<td>

Specify the deployment sources as a newline\- or comma\-separated list of paths to files/direсtories to be deployed. Ant\-style wildcards like `dir/**/*.zip` and target directories like `*.zip => winFiles,unix/distro.tgz => linuxFiles`, where `winFiles` and `linuxFiles` are target directories, are supported.

</td></tr></table>

__ __