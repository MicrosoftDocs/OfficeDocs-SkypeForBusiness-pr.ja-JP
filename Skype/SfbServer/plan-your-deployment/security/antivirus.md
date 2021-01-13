---
title: Skype for Business Server のウイルス対策スキャンの除外
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832267"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Skype for Business Server のウイルス対策スキャンの除外

Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。

ウイルス対策スキャナーが Skype for Business Server の動作に干渉しないようにするには、ウイルス対策スキャナーを実行する Skype for Business Server サーバーまたはサーバーの役割ごとに特定のプロセスとディレクトリを除外する必要があります。 除外が必要なプロセスとディレクトリを以下に示します。

> [!NOTE]
> 次に示すフォルダーとファイルの場所は、Skype for Business Server の既定の場所です。 既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。

> [!IMPORTANT]
> 一部のウイルス対策プログラムでは、除外一覧に相対パスではなく絶対パスが必要な場合があります。

- Skype for Business Server プロセス:

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

- Windows Fabric Host Service プロセス:

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

  - Standard Edition インストール RTC インスタンス

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- ディレクトリとファイル:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > これらのパスは、Skype for Business Server のバージョンに固有のパスです。

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。

  - SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。 データベースとログ ファイルは、トポロジ ビルダーで指定できます。 既定の名前など、各データベースのデータおよびログ ファイルの詳細については、展開のドキュメントの「[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)」を参照してください。

  - SQL Server、フロントエンド データベース、Skype for Business ストア、RtcDatabase ストア用のデータファイルやログ ファイルを含めます。 通常、%localdrive%\CSData の下にあります。


