# Ark-PsScripts
Powershell scripts for Ark and Nitrado hosting


To create an oAuth key:

https://server.nitrado.net
(User name, top right) / My Account
Developer Portal
Long-life tokens
Fill in description
Check everything except service_order
Generate key, copy and paste into script when requested.

Key is saved in the registry at HKCU:\Software\NitrAPI\oAuth.
Keep this key secure, anybody that obtains it can mess with your server.


Functions:

NtrGet $uri $body
  Generic Get request to the API
  
NtrPost $uri $body
  Generic Post request to the API
  
NtrUserDetails
NtrServiceList

$ntrid = (NtrServiceList).id
$ntrusername = (NtrServiceList).username

Below functions require $ntrid set:
NtrServiceDetails
NtrServiceLogs
NtrServiceNotifications
NtrGameserverDetails
NtrSetFtpPassword
NtrFilesList $dir $searchcriteria
NtrFileDownload $filepath
NtrFileCopy $sourcepath $destpath $destname
NtrListPlayers
NtrListBackups

$game = (NtrGameserverDetails).game
$sg = "/games/$ntrusername/noftp/$game/ShooterGame/Saved"

NtrDirDownload $sourcepath
