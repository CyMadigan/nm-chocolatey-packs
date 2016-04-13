# SQL Server 2008 Chocolatey Package
* Uses environment variables to configure.
* Minimum requirement is a local path to the ISO image.
* Path to the ISO is supplied to the package via the `choco:sqlserver2008:isoImage` environment variable.

See `chocolateyinstall.ps1` for all environment vars which mirror those in the [documentation](https://technet.microsoft.com/en-us/library/ms144259%28v=sql.110%29.aspx)

##Example install
Execute this from elevated PowerShell to install to an instance named `SQL2008` with sql management studio and a custom collation:

	#mandatory param
	$env:choco:sqlserver2008:isoImage="D:\Downloads\en_sql_server_2008_developer_edition_with_service_pack_3_x86_dvd_7286785.iso"
	
	#optional params
	$env:choco:sqlserver2008:INSTALLSQLDATADIR="C:\Data\Sql\sql2008"
	$env:choco:sqlserver2008:INSTANCEID="sql2008"
	$env:choco:sqlserver2008:INSTANCENAME="sql2008"
	$env:choco:sqlserver2008:FEATURES="SQLENGINE,SSMS,ADV_SSMS"
	$env:choco:sqlserver2008:AGTSVCACCOUNT="NT Service\SQLAgent`$SQL2008"
	$env:choco:sqlserver2008:SQLSVCACCOUNT="NT Service\MSSQL`$SQL2008"
	$env:choco:sqlserver2008:SQLCOLLATION="SQL_Latin1_General_CP1_CI_AS"

	choco install sqlserver2008












