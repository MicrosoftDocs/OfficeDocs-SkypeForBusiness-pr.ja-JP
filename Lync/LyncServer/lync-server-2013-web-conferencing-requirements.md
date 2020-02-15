---
title: 'Lync Server 2013: Web 会議の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 914fee9d2ddf0a7e6d6867879a197b55380d35c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013 での Web 会議の要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

Web 会議を有効にすることにした場合、次のものを計画する必要があります。

  - <span></span>  
    Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。

  - <span></span>  
    会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバーとの統合。

<div>

## <a name="file-store"></a>ファイル ストア

Lync Server 2013 web 会議サービスは、会議中に共有されたコンテンツをファイルストアに保存します。 展開の一環として、Standard Edition サーバーまたは Enterprise Edition フロントエンドプールのいずれかのファイルストアとして使用するファイル共有を指定する必要があります。 既存のファイル共有をファイルストアに使用することも、ファイル共有を配置するファイルサーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。詳細については、「トポロジビルダー-フロントエンドのファイルストアを定義する」を参照してください。 Web 会議サービスは、コンテンツを暗号化してからファイルストアに保存します。

Lync Server 2013 では、直接接続ストレージ (DAS) またはストレージエリアネットワーク (SAN) (分散ファイルシステム (DFS) や、ファイルストア用の独立したディスク (RAID) の冗長アレイ) のいずれかでのファイル共有の使用がサポートされています。 Lync server 展開ウィザードによってファイル共有の場所が定義されると、Lync Server は次のようなファイル共有内にフォルダー構造を作成します。

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-1-1
    
      - によっ
    
      - CollabMetadata
    
      - DataConf

次に、Web 会議サービスによって、PowerPoint スライド、ホワイトボード、ポーリング、および添付ファイルなどのコンテンツが WebServices フォルダーにある CollabContent フォルダーおよび CollabMetadata フォルダーに格納されます。

管理者は、ファイル共有に対するアクセス許可を設定して、必要な読み取りおよび書き込みのアクセスを RTC グループに付与する必要があります。

<div>


> [!WARNING]  
> アクセス許可に関するエラーが発生する場合は、トポロジ ビルダーを開き、既存のトポロジをダウンロードして再公開してください。トポロジを公開することによって、ファイル共有のアクセス許可が検証され、必要に応じてリセットされます。



</div>

次の設定項目を使用すると、会議用にコンテンツを格納する方法を管理できます。

  - **ContentGracePeriod**は、 [get-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)に配置されているため、会議が終了した後に web 会議のコンテンツをサーバー上に保持する時間を設定します。

  - **Maxcontentstoragemb**は、1 [](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)つの会議中にコンテンツの格納に使用できる最大ファイル領域を設定します。

**Maxuploadfilesizemb 枠**は、Lync Web App のファイルのアップロード設定を制限しません。 Lync Web App のファイルサイズのアップロードの制限は約30MB に設定されており、IIS web.config ファイルによって制御されます。/\[Datacollabweb/Int Ext\]/ハンドラー/web¥ config。Lync Web App のファイルサイズのアップロード制限を構成するに`maxRequestLength`は`maxAllowedContentLength` 、以下に示すように、web.config ファイルを更新します。

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

各フロントエンドサーバーの web.config ファイルを更新する必要があります。

</div>

<div>

## <a name="office-web-apps-server"></a>Office Web Apps サーバー

これらの新機能を使用するには、管理者が Office Web Apps サーバーをインストールする必要があります。また、Office Web Apps サーバーと通信するように Lync Server 2013 を構成する必要があります。 このドキュメントでは、Office Web Apps サーバーを使用するように Lync Server 2013 を構成する方法について説明します。 このドキュメントでは、Office Web Apps サーバーのインストール方法について説明します。 インストールの詳細については、「Microsoft Office Web Apps <http://go.microsoft.com/fwlink/p/?linkid=257525>展開 web サイト」を参照してください。 このガイドには、Office Web Apps サーバーの完全な前提条件に関する情報が含まれています。 Office Web Apps サーバーは、Lync Server、SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンのコンピューターにインストールする必要があることに注意してください。 (そのコンピューターに Office のバージョンがインストールされていない必要があります)。Office Web Apps サーバーを実行するために使用するすべてのコンピューターに、特定のソフトウェアセット (.NET Framework 4.5 および Windows PowerShell 3.0 を含む) がインストールされている必要もあります。 これらの要件と、証明書とインターネットインフォメーションサービス (IIS) の構成の詳細については、「Microsoft Office Web Apps 展開 web <http://go.microsoft.com/fwlink/p/?linkid=257525>サイト」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の web 会議の概要](lync-server-2013-web-conferencing-overview.md)  
[Lync Server 2013 での web 会議の展開チェックリスト](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

