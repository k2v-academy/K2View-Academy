# Fabric BI Installation on Linux

## Introduction

The Fabric BI application is based on *ExagoBI*. So, the installation of Fabric BI starts from ExagoBI application installation. Once the application is installed, complete the configuration and implementation by following all the steps described in the [Fabric BI User Guide](/articles/38_bi_integration/00_BI_user_guide_overview.md).

## Prerequisites

- Debian OS version 11 and up, with the latest update.
- Disable SELinux.
- Apache Web server with installed modules:  mono-fastcgi-server4 libapache2-mod-fcgid.
- The following modules enabled (a2enmod): fcgid, proxy, proxy_fcgi.
- PHP 7.1 engine with the following modules : php-common php-opcache php-mcrypt php-cli php-gd php-curl php-xml
- Hardware - TDB.

[Click for more details about ExagoBI Technical Specifications](https://exagobi.com/support/administrators/installation-and-configuration/technical-specifications/).

## Installation on Linux

1. Download the ExagoBI installer: ExagoInstaller_vXXX.X.X.XXX.tgz from [here](https://download.k2view.com/index.php/s/uqSlM6wJjLUeKlC) into a temporary directory.

2. Download the the K2View additional files and installation script from [here](https://download.k2view.com/index.php/s/g4ixtpPnIIcDb0T) into a temporary directory.

3. Open a CLI, move to the temporary directory and extract the downloaded file by running the following command as a user with root permissions:

   ~~~bash
   tar -zxvf exago_installer_debian.tar.gz
   ~~~

4. Run the installation script with 2 variables: the installation folder **/opt/apps/exago** and the ExagoBI installation file name. 
   In the example, the installation filename is: **ExagoInstaller_v2021.1.15.239**.

   ~~~bash
   ./k2view_exago_install.sh /opt/apps/exago ExagoInstaller_v2021.1.15.239
   ~~~

   **Note**: the Exago installation folder name **/opt/apps/exago** is case-sensitive.
   
5. Continue to other installation and configuration steps described in the [User Guide Installation article](/articles/38_bi_integration/01_Installation.md).

6. in AWS enviroments or when Local IP is not accessible (NAT) the file **WebReportsApi.xml** in the folder **{Exago installation folder}/WebServiceApi/Config** need to be updated with the correct DNS/IP record.
update the line
~~~
webreportsbaseurl>http://{local_IP}/Exago/</webreportsbaseurl> 
~~~
and replace the local IP with the correct record.


7. In order to restart the enviroment or after system restart make sure the Apache service and FastCGI service are running.
   **FastCGI** managment script is located in the installation folder of exago (usualy **'/opt/apps/exago'**)
   
   To **start** the FastCGI service:
   
   ~~~bash
   ./fastcgi.sh start
   ~~~
   
   To **restart** the FastCGI service:
   
   ~~~bash
   ./fastcgi.sh restart
   ~~~
   

**Directory Locations**

<table style="border-collapse: collapse; width: 100%;">
<tbody>
<tr>
<td style="width: 50%; height: 18px;">Application Binaries</td>
<td style="width: 50%; height: 18px;">/opt/apps/exago/bin</td>
</tr>
<tr>
<td style="width: 50%; height: 18px;">API for Exago Web Service</td>

<td style="width: 50%; height: 18px;">/opt/apps/exago/WebServiceApi</td>
</tr>
<tr>
<td style="width: 50%; height: 18px;">3rd Party’s Utilities</td>


<td style="width: 50%; height: 18px;">/opt/apps/exago/Utilities</td>
</tr>
<tr>
<td style="width: 50%; height: 18px;">3rd Party’s Drivers</td>

<td style="width: 50%; height: 18px;">/opt/apps/exago/Drivers</td>
</tr>
<tr>
<td style="width: 50%; height: 18px;">Personalization Configuration</td>

<td style="width: 50%; height: 18px;">/opt/apps/exago/Config</td>
</tr>
<tr>
<td style="width: 50%; height: 18px;">Exago Report Scheduler</td>
<td style="width: 50%; height: 18px;">/opt/apps/exago/Scheduler</td>
</tr>
</tbody>
</table>

