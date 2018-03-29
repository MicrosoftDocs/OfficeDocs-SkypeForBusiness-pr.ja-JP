---
title: Skype for Business Server 2015 のウイルス スキャン除外範囲
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: ビジネス サーバー 2015 の Skype でのウイルス対策プログラムの相互運用の概要です。
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 のウイルス スキャン除外範囲
 
ビジネス サーバー 2015 の Skype でのウイルス対策プログラムの相互運用の概要です。 
  
ウイルス対策スキャナーがビジネス サーバー 2015 の Skype の操作に干渉しないことを確認するには、ウイルス対策スキャナーを実行するビジネス サーバー 2015 のサーバーまたはサーバーの役割の各 Skype の特定のプロセスおよびディレクトリを除外する必要があります。 除外が必要なプロセスとディレクトリを以下に示します。
  
> [!NOTE]
> 以下のフォルダーとファイルの場所は、ビジネス サーバー 2015 の Skype のデフォルトの場所です。 既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。 
  
> [!IMPORTANT]
> 一部のウイルス対策プログラムでは、除外リストに相対パスでなく絶対パスが必要な場合があります。 
  
- ビジネス サーバー 2015 の Skype を処理します。
    
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
    
- Windows Fabric Host Service のプロセス:
    
  - Fabric.exe
    
  - FabricDCA.exe
    
  - FabricHost.exe
    
- IIS のプロセス:
    
  - %systemroot%\system32\inetsrv\w3wp.exe
    
  - %systemroot%\SysWOW64\inetsrv\w3wp.exe
    
- SQL Server バックエンドのプロセス:
    
    > [!NOTE]
    > これらのパスは、SQL Server バージョン固有のパスです。 
  
  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe
    
- SQL Server フロントエンドのプロセス:
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - Standard Edition インストールの RTC インスタンス 
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe
    
- ディレクトリとファイル:
    
  - %systemroot%\System32\LogFiles
    
  - %systemroot%\SysWow64\LogFiles
    
  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL
    
  - %programfiles%\Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node
    
  - %programfiles%\Common Files\Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Online
    
  - %SystemDrive%\RtcReplicaRoot
    
  - ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。
    
  - SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。 データベースとログ ファイルは、トポロジ ビルダーで指定できます。 既定の名前を含む、各データベースのデータとログ ファイルの詳細については、展開に関するドキュメントで[SQL Server のデータとログ ファイルの配置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)を参照してください。
    
  - SQL Server データ ファイルとログ ファイル、Skype ビジネス ストア、および RtcDatabase のストアのフロント エンド データベースを含みます。 これらは通常、%localdrive%\CSData の下位にあります。
    

