---
title: 'Lync Server 2013: ウイルス対策スキャンの除外'
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
ms.openlocfilehash: f8faeba1d3b661110bcaf633d3c780dc2c2ad2b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Lync Server 2013 のウイルススキャン除外

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-11-02_

ウイルス検出プログラムが Lync Server 2013 の動作に干渉しないようにするには、ウイルス対策スキャナーを実行する Lync Server 2013 サーバーまたはサーバーの役割ごとに特定のプロセスとディレクトリを除外する必要があります。 除外が必要なプロセスとディレクトリを以下に示します。

<div>


> [!NOTE]  
> 下にリストされているフォルダーとファイルの場所は、Lync Server 2013 の既定の場所です。 既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。



</div>

<div>


> [!IMPORTANT]  
> 一部のウイルス対策プログラムでは、除外リストに相対パスではなく、絶対的なパスが必要になることに注意してください。



</div>

  - Lync Server 2013 プロセス:
    
      - ABServer
    
      - AcpMcuSvc
    
      - ASMCUSvc .exe
    
      - AVMCUSvc .exe
    
      - ChannelService .exe
    
      - ClsAgent .exe
    
      - ComplianceService
    
      - DataMCUSvc
    
      - DataProxy .exe
    
      - FileTransferAgent
    
      - IMMCUSvc .exe
    
      - LysSvc
    
      - MasterReplicatorAgent .exe
    
      - メディア Relaysvc
    
      - MediationServerSvc
    
      - MRASSvc
    
      - OcsAppServerHost
    
      - ReplicaReplicatorAgent
    
      - ReplicationApp .exe
    
      - RtcHost
    
      - RTCSrv
    
      - XmppProxy .exe
    
      - XmppTGW. .exe

  - Windows Fabric ホストサービスプロセス:
    
      - Fabric
    
      - FabricDCA
    
      - FabricHost

  - IIS のプロセス:
    
      - % systemroot%\\system32\\inetsrv\\
    
      - % systemroot%\\SysWOW64\\inetsrv\\w3wp

  - SQL Server バックエンドプロセス:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。MSSQLSERVER\\MSSQL\\Binn\\sqlservr.exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11。MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\reportingサービス .exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11。MSSQLSERVER\\OLAP\\Bin\\msmdsrv.ini

  - SQL Server フロントエンドプロセス:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。LYNCLOCAL\\MSSQL\\Binn\\sqlservr.exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。RTCLOCAL\\MSSQL\\Binn\\sqlservr.exe

  - ディレクトリとファイル:
    
      - % systemroot%\\System32\\のログログ
    
      - % systemroot%\\SysWow64\\ログログ
    
      - % systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL
    
      - % programfiles%\\Microsoft Lync Server 2013
    
      - % programfiles%\\Common Files\\Microsoft Lync Server 2013\\監視ノード
    
      - % programfiles%\\Common Files\\Microsoft Lync Server 2013
    
      - % SystemDrive%\\RtcReplicaRoot
    
      - ファイル共有ストア (トポロジ ビルダーで指定)。 ファイル ストアはトポロジ ビルダーで指定されています。
    
      - SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。 データベースとログ ファイルは、トポロジ ビルダーで指定できます。 既定の名前など、各データベースのデータおよびログファイルの詳細については、「展開」のドキュメントの「 [SQL server data and log file placement For Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) 」を参照してください。
    
      - SQL Server のデータおよびログファイル (フロントエンドデータベース、Lync ストア、および RtcDatabase store のものを含む)。 通常、% localdrive%\\csdata の下にあります。

</div>

<span> </span>

</div>

</div>

</div>

