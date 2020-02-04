---
title: 'Lync Server 2013: Web ファームの FQDN の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Lync Server 2013 向けの Web ファームの FQDN の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-29_

Standard Edition server、フロントエンドプール、ディレクター、またはディレクターの構成をトポロジビルダーで定義した場合、外部 web サービスの完全修飾ドメイン名 (FQDN) を構成します。 Standard Edition server またはフロントエンドプールに所属しているクライアントのログオンプロセスでは、構成された web サービスの Fqdn は、インバンドプロビジョニングを通じて送信されます。 外部 web サービスの URL を追加または変更する必要がある場合は、このトピックの手順を使用して、トポロジビルダーを使用して web サービスの構成を構成または再構成します。

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Web サービス用の外部プール FQDN を構成するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  [トポロジビルダー] のコンソールツリーの、**標準エディションのフロントエンド**、 **Enterprise Edition のフロントエンド**、および**ディレクター**で、編集する必要があるプール名を右クリックし、[**プロパティの編集**] をクリックします。

3.  [ **Web services** ] セクションで、**外部 WEB サービスの FQDN**を追加または編集します。

4.  HTTP と HTTPS の両方の**リスニングポート**を確認し、調整します。 既定値は、次のようになります。
    
      - **リスニングポート:** HTTP 8080、HTTPS 4443
    
      - 公開された**ポート:** HTTP 80、HTTPS 443
    
    このポート**は、** 外部 web サービスがリバースプロキシからの要求を受信するように構成されているポートであり、公開された**ポート**はリバースプロキシによって外部で公開されるポートであり、インバンドプロビジョニング中にクライアントに伝達されます。

5.  追加と更新が完了したら、[ **OK]** をクリックして操作を続けます。

6.  [ **Lync Server 2013**] を右クリックし、[**発行**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > 発行が正常に完了すると、追加の手順を実行する必要があることを知らせるリンクが表示されることがあります。 リンクをクリックすると、[トポロジビルダー] で行った変更の影響を受けるサーバーの一覧が表示されます。このリンクをクリックすると、一覧の各サーバーで Lync Server 展開ウィザードを再実行して、追加、削除、または変更されたコンポーネントの構成を更新する必要があります。

    
    </div>

7.  組織内の標準エディションサーバー、フロントエンドプール、ディレクター、またはディレクタープールごとに、この手順を繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

