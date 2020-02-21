---
title: 'Lync Server 2013: Lync Windows ストアアプリの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06d32aa0cf2248c80b8f98d80e8c796818b89a6b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Lync Server 2013 の lync Windows ストアアプリの要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-12-03_

社内で Lync Server を展開している組織は、Lync Windows ストアアプリをサポートするために以下の要件を満たしている必要があります。

<div>


> [!NOTE]  
> Lync server 2010 の場合は、lync server 2010 の累積的な更新プログラム (2 月 1 <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp2012 日 (kbid = 2670352</A>) 以降) を実行します。 ユーザーが会議に参加できるようにするには、サーバー上で Lync Server 2010 の累積的<A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp</A>な更新プログラム (10 月 2012) を実行します (kbid = 2737915)。



</div>

  - サーバー上の自動検出、Lync Web App、および Web チケットサービスを有効にします。

  - フロントエンドサーバーまたはフロントエンドプールで証明書認証を有効にします。 (フロントエンドサーバーまたはフロントエンドプールでのユーザー登録プロセスは、多くの場合レジストラーと呼ばれます)。詳細については、「 [Create レジストラー configuration settings In Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md)」を参照してください。

  - 自動検出サービスの DNS エイリアス (CNAME) リソースレコードを公開します。

  - Lync server に発行された証明書の証明書失効リスト (CRL) 配布ポイント (CDP) が、LDAP リソースではなく HTTP リソースを指していることを確認する必要はなくなりました。 ただし、クライアントコンピューターに最新の Windows 更新プログラムがインストールされていることを確認してください。

  - Lync server 関連の HTTP トラフィックを許可するように、エンタープライズで HTTP プロキシを構成します。必要に応じて、自動検出、Lync Web App、および WebTicket サービスの例外を追加します。

  - クライアントで、Windows 8.1 と Lync Windows ストアアプリの最新バージョンをインストールして、複数のドメインを使用するときに一般的に発生するサインインの問題を修正します (たとえば、SIP URI が**userA@domainZ.com** 、エッジサーバーが**sip.domainX.com**)。

組織が Lync Online または Office 365 をサブスクライブしていて、独自のドメイン名を使用している場合は、Lync サーバーの自動検出のためにネットワークをセットアップするための特別な手順を実行する必要があります。 ネットワーク構成の要件は、モバイルデバイスの Lync Windows ストアアプリと Lync で同じです。 「Office 365 wiki」の「ネットワークをセットアップする」の手順に従い[https://go.microsoft.com/fwlink/?LinkId=271822](https://go.microsoft.com/fwlink/?linkid=271822)ます (「Lync モバイルデバイスをセットアップする」の記事を参照してください)。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Lync Windows ストアアプリの展開](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

