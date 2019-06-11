---
title: 'Lync Server 2013: Web 会議の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddfd7c2fdfe6cbcefcca7533e93c3c377cceea8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013 での Web 会議の要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-30_

Web 会議を有効にすることにした場合、次のものを計画する必要があります。

  - <span></span>  
    Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。

  - <span></span>  
    会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバーとの統合。

<div>

## <a name="file-store"></a>ファイル ストア

Lync Server 2013 web 会議サービスでは、会議中に共有されたコンテンツをファイルストアに保存します。 展開の一環として、Standard Edition server または Enterprise Edition のフロントエンドプールのファイルストアとして使用するファイル共有を指定する必要があります。 ファイルストアには既存のファイル共有を使用できます。また、ファイル共有が配置されているファイルサーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。詳細については、「トポロジビルダー–フロントエンド用のファイルストアの定義」を参照してください。 Web 会議サービスによって、コンテンツがファイルストアに保存される前に暗号化されます。

Lync Server 2013 は、直接接続型ストレージ (DAS) またはストレージエリアネットワーク (SAN) 上でのファイル共有の使用をサポートします。これには、分散ファイルシステム (DFS) や、ファイルストアの独立したディスク (RAID) の冗長配列が含まれます。 Lync Server 展開ウィザードでファイル共有の場所が定義されると、Lync Server によって、次のようなファイル共有内にフォルダー構造が作成されます。

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

次に、Web 会議サービスによって、PowerPoint スライド、ホワイトボード、ポーリング、および添付ファイルなどのコンテンツが WebServices フォルダーにある CollabContent フォルダーおよび CollabMetadata フォルダーに格納されます。

管理者は、ファイル共有に対するアクセス許可を設定して、RTC グループが必要な読み取りおよび書き込みアクセス権を持つようにする必要があります。

<div>


> [!WARNING]  
> 権限に関するエラーが発生した場合は、トポロジビルダーを開き、既存のトポロジをダウンロードして再公開します。 トポロジを公開することで、ファイル共有のアクセス許可を確認し、必要に応じてリセットできます。



</div>

会議のコンテンツの保存方法を管理するには、次の設定を使用できます。

  - **ContentGracePeriod**は、 [CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)で指定された web 会議コンテンツが、会議終了後にサーバー上に残る長さを設定します。

  - **Maxcontentstoragemb**は、1 [](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)回の会議中にコンテンツの保存に使用できるファイル領域の最大サイズを設定します。

**Maxuploadfilesizemb 枠**は、Lync Web App のファイルアップロード設定を制限していません。 Lync Web App のファイルサイズのアップロードの上限は約30MB に設定されており、IIS の web.config ファイルで制御されます:/Datacollabweb/Int\[\]Lync Web App のファイルサイズのアップロード制限を構成するに`maxRequestLength`は`maxAllowedContentLength` 、以下に示すように、web.config ファイルを使用します。

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

これらの新機能を使用するには、管理者が Office Web Apps サーバーをインストールしている必要があります。また、管理者は、Office Web Apps サーバーと通信するように Lync Server 2013 を構成する必要があります。 このドキュメントでは、Lync Server 2013 を Office Web Apps サーバーと連携するように構成する方法について説明します。 このドキュメントでは、Office Web Apps サーバーをインストールする方法について説明していません。 インストールの詳細については、の Microsoft Office Web Apps <http://go.microsoft.com/fwlink/p/?linkid=257525>展開 web サイトを参照してください。 このガイドには、Office Web Apps サーバーの必要な情報がすべて記載されています。 Office Web Apps サーバーは、Lync Server、SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンコンピューターにインストールする必要があることに注意してください。 (そのコンピューターに Office のバージョンがインストールされていない必要があります)。Office Web Apps サーバーを実行するために使用されるコンピューターには、特定のソフトウェアセット (.NET Framework 4.5 および Windows PowerShell 3.0 を含む) がインストールされている必要もあります。 これらの要件と、証明書とインターネットインフォメーションサービス (IIS) を構成する方法については、Microsoft Office Web Apps 展開の web <http://go.microsoft.com/fwlink/p/?linkid=257525>サイトで詳しく説明します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での web 会議の概要](lync-server-2013-web-conferencing-overview.md)  
[Lync Server 2013 の web 会議の展開チェックリスト](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

