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
ms.openlocfilehash: 4b67f1472bbb8225bf952b5b678bcae8401d211d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508974"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Lync Server 2013 のウイルススキャン除外

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
    
      - ABServer.exe
    
      - AcpMcuSvc.exe
    
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

  - Windows Fabric ホストサービスプロセス:
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - IIS のプロセス:
    
      - % systemroot% \\ system32 \\ inetsrv \\w3wp.exe
    
      - % systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe

  - SQL Server Back-End プロセス:
    
      - % ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe
    
      - % ProgramFiles% \\ MICROSOFT SQL Server \\ MSRS11。MSSQLSERVER \\ Reporting Services \\ ReportServer \\ Bin \\ReportingServicesService.exe
    
      - % ProgramFiles% \\ MICROSOFT SQL Server \\ MSAS11。MSSQLSERVER \\ OLAP \\ Bin \\MSMDSrv.exe

  - SQL Server Front-End プロセス:
    
      - % ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe
    
      - % ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe

  - ディレクトリとファイル:
    
      - % systemroot% \\ System32 の \\ ログログ
    
      - % systemroot% \\ SysWow64 \\ ログログ
    
      - % systemroot% \\ Microsoft.NET \\ assembly \\ GAC \_ MSIL
    
      - % programfiles% \\ Microsoft Lync Server 2013
    
      - % programfiles% \\ Common Files \\ Microsoft Lync Server 2013 \\ 監視ノード
    
      - % programfiles% \\ Common Files \\ Microsoft Lync Server 2013
    
      - % SystemDrive% \\ RtcReplicaRoot
    
      - ファイル共有ストア (トポロジ ビルダーで指定)。 ファイル ストアはトポロジ ビルダーで指定されています。
    
      - SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。 データベースとログ ファイルは、トポロジ ビルダーで指定できます。 既定の名前など、各データベースのデータおよびログファイルの詳細については、「展開」のドキュメントの「 [SQL server data and log file placement For Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) 」を参照してください。
    
      - SQL Server のデータおよびログファイル (フロントエンドデータベース、Lync ストア、および RtcDatabase store のものを含む)。 通常、% localdrive% csdata の下にあり \\ ます。

</div>

<span> </span>

</div>

</div>

</div>

