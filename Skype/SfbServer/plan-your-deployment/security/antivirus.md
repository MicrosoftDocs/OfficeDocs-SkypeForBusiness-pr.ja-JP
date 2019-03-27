---
title: ビジネス サーバーの Skype の除外リストをスキャンするウイルス対策
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: ビジネス サーバーの Skype でのウイルス対策プログラムの相互運用の概要です。
ms.openlocfilehash: 377c9e8fb9de71187978fe541a23f43cc2282749
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895966"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>ビジネス サーバーの Skype の除外リストをスキャンするウイルス対策

ビジネス サーバーの Skype でのウイルス対策プログラムの相互運用の概要です。

この資料には、管理者は Active Directory ドメインでのウイルス対策ソフトウェアで使用されている場合、サポートされているバージョンの Microsoft Windows を実行しているコンピューター上の潜在的な不安定の原因を特定するのに役立つ推奨事項が含まれています。環境またはマネージ ビジネス環境です。

システムを評価するためにこれらの手順を一時的に適用することをお勧めします。 場合はここで行われるための推奨事項により、システムのパフォーマンスや安定性が向上し、またはウイルス対策ソフトウェアの更新されたバージョンの手順については、ウイルス対策ソフトウェアの製造元に問い合わせてください。

この資料には、セキュリティ設定を低くする方法、またはコンピューターのセキュリティ機能を一時的に無効する方法を示す情報が含まれています。 特定の問題の性質を理解するのにはこれらの変更を行うことができます。 これらの変更を行う前に、特定の環境でこの回避策の実装に関連付けられているリスクを評価することをお勧めします。 この回避策を実装する場合は、不要になったウイルス対策ソフトウェアによってスキャンされているファイルには、コンピューターを保護するために適切な追加の手順を実行します。

ウイルス対策スキャナーが、Skype のビジネス サーバーの操作に干渉しないことを確認するには、ウイルス対策スキャナーを実行するビジネスのサーバーまたはサーバーの役割の各 Skype の特定のプロセスおよびディレクトリを除外する必要があります。 除外が必要なプロセスとディレクトリを以下に示します。

> [!NOTE]
> 以下のフォルダーとファイルの場所は、Skype のビジネス サーバーの既定の場所です。 既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。

> [!IMPORTANT]
> 一部のウイルス対策プログラムでは、除外リストに相対パスでなく絶対パスが必要な場合があります。

- ビジネス サーバー用の Skype を処理します。

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

    > [!NOTE]
    > これらのパスがビジネスのサーバーのバージョンの Skype に固有に注意してください。

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。

  - SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。データベースとログ ファイルは、トポロジ ビルダーで指定できます。既定の名前など、各データベースのデータおよびログ ファイルの詳細については、「展開」のドキュメントの「[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)」を参照してください。

  - SQL Server データ ファイルとログ ファイル、Skype ビジネス ストア、および RtcDatabase のストアのフロント エンド データベースを含みます。 これらは通常、%localdrive%\CSData の下位にあります。


