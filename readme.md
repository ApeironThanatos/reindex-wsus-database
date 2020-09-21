Archived from Microsoft TechNet

https://gallery.technet.microsoft.com/scriptcenter/6f8cde49-5c52-4abd-9820-f1d270ddea61

The performance of large Windows Server Update Services (WSUS) deployments will
degrade over time if the WSUS database is not maintained properly. The 
WSUSDBMaintenance script is a T-SQL script that can be run by SQL Server 
administrators to re-index and defragment WSUS databases. It should not be used 
on WSUS 2.0 databases.This script contributed by the Microsoft WSUS team.

If you are using Windows Internal Database, you will need to use the sqlcmd 
utility, which can be downloaded from docs.microsoft.com page for SQLCMD. This 
page will also contain additional information about the sqlcmd utility.

To use this script with Windows Internal Database, you should run the following 
command:

sqlcmd -S np:\\.\pipe\MSSQL$MICROSOFT##SSEE\sql\query –i <scriptLocation>\WsusDBMaintenance.sql

The call to sqlcmd needs to have a -I (capital i) parameter, which tells SQL to
run the script with QUOTED_IDENTIFIERS enab