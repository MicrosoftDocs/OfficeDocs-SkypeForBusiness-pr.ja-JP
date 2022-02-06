---
title: ウイルス対策スキャンの除外Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: ウイルス対策スキャナーとウイルス対策スキャナーの相互運用Skype for Business Server。
---

# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>ウイルス対策スキャンの除外Skype for Business Server

ウイルス対策スキャナーとウイルス対策スキャナーの相互運用Skype for Business Server。

ウイルス対策スキャナーが Skype for Business Server の操作を妨げないよう、ウイルス対策スキャナーを実行する Skype for Business Server サーバーまたはサーバーの役割ごとに特定のプロセスとディレクトリを除外する必要があります。 除外が必要なプロセスとディレクトリを以下に示します。

> [!NOTE]
> 以下に示すフォルダーとファイルの場所は、ユーザーの既定の場所Skype for Business Server。 既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。

> [!IMPORTANT]
> 一部のウイルス対策プログラムでは、除外リストに相対パスではなく絶対パスが必要な場合があります。

- Skype for Business Serverプロセス:

  - ABServer.exe

  - ASMCUSvc.exe

  - AVMCUSvc.exe

  - ChannelService.exe

  - ClsAgent.exe

  - ComplianceService.exe

  - DataMCUSvc.exe

  - DataProxy.exe

  - FileTransferAgent.exe

  - HealthAgent.exe

  - IMMCUSvc.exe
  
  - LyncBackupService.exe

  - LysSvc.exe

  - MasterReplicatorAgent.exe

  - MediaRelaySvc.exe

  - MediationServerSvc.exe

  - MRASSvc.exe

  - OcsAppServerHost.exe

  - ReplicaReplicatorAgent.exe

  - ReplicationApp.exe

  - RtcHost.exe

  - RTCSrv.exe

  - XmppProxy.exe

  - XmppTGW.exe

- Windows Fabricホスト サービス プロセス:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- IIS のプロセス:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-Endプロセス:

    > [!NOTE]
    > これらのパスは、特定のバージョンに固有SQL Server注意してください。

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-Endプロセス:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Standard Edition RTC インスタンス

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- ディレクトリとファイル:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > これらのパスは、特定のバージョンに固有Skype for Business Server注意してください。

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。

  - SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。データベースとログ ファイルは、トポロジ ビルダーで指定できます。既定の名前など、各データベースのデータおよびログ ファイルの詳細については、展開のドキュメントの「[SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)」を参照してください。

  - SQL Server、フロントエンド データベース、ストア、RtcDatabase ストアのデータ ファイルSkype for Businessログ ファイルを作成します。 通常、%localdrive%\CSData の下にあります。