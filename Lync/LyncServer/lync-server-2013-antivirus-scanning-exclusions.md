---
title: 'Lync Server 2013: ウイルス スキャン除外範囲'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90847830d9f2586e0d111846f2867400c52fc940
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Lync Server 2013 用のウイルス スキャン除外範囲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-11-02_

ウイルス対策スキャナーが Lync Server 2013 の動作を妨害しないようにするには、ウイルススキャンを実行している Lync Server 2013 サーバーまたはサーバーの役割ごとに、特定のプロセスとディレクトリを除外する必要があります。 除外が必要なプロセスとディレクトリを以下に示します。

<div>


> [!NOTE]  
> 次に示すフォルダーとファイルの場所は、Lync Server 2013 の既定の場所です。 既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。



</div>

<div>


> [!IMPORTANT]  
> 一部のウイルス対策プログラムでは、除外リストに相対パスでなく絶対パスが必要な場合があります。



</div>

  - Lync Server 2013 のプロセス:
    
      - ABServer.exe
    
      - AcpMcuSvc
    
      - ASMCUSvc.exe
    
      - AVMCUSvc.exe
    
      - ChannelService.exe
    
      - ClsAgent.exe
    
      - ComplianceService.exe
    
      - DataMCUSvc.exe
    
      - DataProxy.exe
    
      - FileTransferAgent.exe
    
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
    
      - % systemroot%\\system32\\inetsrv\\w3wp
    
      - % systemroot%\\SysWOW64\\inetsrv\\は、w3wp

  - SQL Server バックエンドのプロセス:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。MSSQLSERVER\\MSSQL\\Binn\\sqlservr.exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11。MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\reportingサービスの service .exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11。MSSQLSERVER\\OLAP\\Bin\\MSMDSrv

  - SQL Server フロントエンドのプロセス:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。LYNCLOCAL\\MSSQL\\Binn\\sqlservr.exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。RTCLOCAL\\MSSQL\\Binn\\sqlservr.exe

  - ディレクトリとファイル:
    
      - % systemroot%\\System32\\ログのログ
    
      - % systemroot%\\SysWow64\\ログ
    
      - % systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL
    
      - % programfiles%\\Microsoft Lync Server 2013
    
      - % programfiles%\\共通ファイル\\Microsoft Lync Server 2013\\ウォッチャーノード
    
      - % programfiles%\\(共通\\ファイル Microsoft Lync Server 2013)
    
      - % SystemDrive%\\RtcReplicaRoot
    
      - ファイル共有ストア (トポロジ ビルダーで指定)。 ファイル ストアはトポロジ ビルダーで指定されています。
    
      - SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。 データベースとログ ファイルは、トポロジ ビルダーで指定できます。 既定の名前など、各データベースのデータファイルとログファイルの詳細については、「 [SQL server のデータと、Lync Server 2013 用のログファイルの配置](lync-server-2013-sql-server-data-and-log-file-placement.md)」を参照してください。
    
      - SQL Server のデータファイルとログファイル (フロントエンドデータベース、Lync ストア、および RtcDatabase store のものを含む)。 通常、% localdrive%\\csdata の下にあります。

</div>

<span> </span>

</div>

</div>

</div>

