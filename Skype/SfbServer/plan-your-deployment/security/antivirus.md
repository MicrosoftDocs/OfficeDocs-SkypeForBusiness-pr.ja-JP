---
title: Skype for Business Server のウイルススキャン除外の除外
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296974"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Skype for Business Server のウイルススキャン除外の除外

Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。

この記事には、サポートされているバージョンの Microsoft Windows を実行しているコンピューターで、Active Directory ドメインでウイルス対策ソフトウェアを使用している場合に発生する可能性のある原因を特定するための推奨事項が記載されています。環境または管理されたビジネス環境。

システムを評価するために、これらの手順を一時的に適用することをお勧めします。 この記事に記載されている推奨事項に従ってシステムのパフォーマンスまたは安定性が改善された場合は、ウイルス対策ソフトウェアベンダーに問い合わせてください。または、ウイルス対策ソフトウェアの更新版をお探しください。

この記事では、セキュリティ設定のレベルを下げる方法、またはコンピューターのセキュリティ機能を一時的に無効にする方法について説明します。 これらの変更を加えて、特定の問題の性質を理解することができます。 これらの変更を行う前に、この回避策の実装に関連するリスクを特定の環境で評価することをお勧めします。 この回避策を実装する場合は、ウイルス対策ソフトウェアによってスキャンされなくなったファイルをコンピューターで保護するために、適切な追加の手順を実行します。

ウイルス対策スキャナーが Skype for Business Server の動作に干渉しないようにするには、ウイルス対策ソフトウェアを実行している各 Skype for Business Server サーバーまたはサーバーロールの特定のプロセスとディレクトリを除外する必要があります。 除外が必要なプロセスとディレクトリを以下に示します。

> [!NOTE]
> 次に示すフォルダーとファイルの場所は、Skype for Business Server の既定の場所です。 既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。

> [!IMPORTANT]
> 一部のウイルス対策プログラムでは、除外リストに相対パスでなく絶対パスが必要な場合があります。

- Skype for Business Server のプロセス:

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
  
  - LyncBackupService

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
    > これらのパスは、Skype for Business Server のバージョンに固有のものであることに注意してください。

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。

  - SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。データベースとログ ファイルは、トポロジ ビルダーで指定できます。既定の名前など、各データベースのデータおよびログ ファイルの詳細については、「展開」のドキュメントの「[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)」を参照してください。

  - SQL Server のデータとログファイル (フロントエンドデータベース、Skype for Business ストア、および RtcDatabase store のものを含む)。 これらは通常、%localdrive%\CSData の下位にあります。


