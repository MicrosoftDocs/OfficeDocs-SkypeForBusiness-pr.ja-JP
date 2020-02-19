---
title: 'Lync Server 2013: web ファームの Fqdn の構成'
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
ms.openlocfilehash: 50813855e4181add65ff279933a952116768dcec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Lync Server 2013 用に web ファーム Fqdn を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-29_

トポロジビルダーで、Standard Edition サーバー、フロントエンドプール、ディレクター、またはディレクタープールの構成を定義した場合は、外部 web サービスの完全修飾ドメイン名 (FQDN) を構成します。 Standard Edition サーバーまたはフロントエンドプールに所属しているクライアントのログオンプロセス時に、構成された web サービスの Fqdn は、インバンドプロビジョニングの方法で送信されます。 外部 web サービスの URL を追加または変更する必要がある場合は、このトピックの手順を使用して、トポロジビルダーを使用して web サービス構成を構成または再構成します。

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Web サービスで使用する外部プールの FQDN を構成するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  トポロジビルダーで、[ **Standard Edition フロントエンド**]、[ **Enterprise Edition フロントエンド**]、および [**ディレクター**] の下にあるコンソールツリーで、編集する必要があるプール名を右クリックし、[**プロパティの編集**] をクリックします。

3.  [**Web サービス**] セクションで、[**外部 Web サービスの FQDN**] を追加または編集します。

4.  HTTP および HTTPS 両方の [**リッスン ポート**] を確認して調整します。既定値は次のとおりです。
    
      - **リッスン ポート:** HTTP 8080、HTTPS 4443
    
      - **公開ポート:** HTTP 80、HTTPS 443
    
    [**リッスン ポート**] は外部 Web サービスがリバース プロキシからの要求を受信するように構成されているポートであり、[**公開ポート**] はリバース プロキシによって外部に公開されているポートで、インバンド プロビジョニングの間にクライアントに通知されます。

5.  追加および更新が終了したら、[**OK**] をクリックして続行します。

6.  [ **Lync Server 2013**] を右クリックし、[**発行**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > 公開が正常に完了した後、実行する必要のある追加手順があることを示すリンクが表示される場合があります。 リンクをクリックすると、表示された各サーバーで Lync Server 展開ウィザードを再実行して、追加、削除、または変更されたコンポーネントの構成を更新する必要があるトポロジビルダーで行われた変更の影響を受けるサーバーの一覧が開きます。

    
    </div>

7.  組織内の Standard Edition サーバー、フロントエンドプール、ディレクター、またはディレクタープールごとに、これらの手順を繰り返します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

