---
title: 'Lync Server 2013: Lync Windows ストアアプリの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806fb7a71232492be7ef01474136817b7808111e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Lync Server 2013 の lync Windows ストアアプリの要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-12-03_

Lync Server のオンプレミス展開を使用する組織は、Lync Windows ストアアプリをサポートするために、次の要件を満たしている必要があります。

<div>


> [!NOTE]  
> Lync server 2010 の場合は、lync server 2010 の累積的な更新プログラムを実行し<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp</A>ます (2 月 2012 (使用可能)、またはその後のすべてのサーバーの場合)。 ユーザーが会議に参加できるようにするには、Lync Server 2010 の累積的な<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp</A>更新プログラム (2012 年10月、2737915) をサーバー上で実行します。



</div>

  - サーバー上で自動検出、Lync Web App、Web Ticket の各サービスを有効にします。

  - フロントエンドサーバーまたはフロントエンドプールで証明書の認証を有効にします。 (フロントエンドサーバーまたはフロントエンドプールでのユーザー登録プロセスは、レジストラーとも呼ばれます)。詳細については、「 [Lync Server 2013 でレジストラー構成の設定を作成する](lync-server-2013-create-registrar-configuration-settings.md)」を参照してください。

  - 自動検出サービスの DNS エイリアス (CNAME) リソースレコードを公開します。

  - Lync server に発行された証明書の証明書失効リスト (CRL) 配布ポイント (CDP) が、LDAP リソースではなく HTTP リソースをポイントしていることを確認する必要がなくなりました。 ただし、クライアントコンピューターに最新の Windows 更新プログラムがインストールされていることを確認してください。

  - Lync server 関連の HTTP トラフィックを許可するように、エンタープライズの HTTP プロキシを構成します。必要に応じて、自動検出、Lync Web App、WebTicket の各サービスの例外を追加します。

  - クライアントで、Windows 8.1 と最新バージョンの Lync Windows ストアアプリをインストールして、複数のドメインを使用する場合に一般的に発生するサインインの問題を解決します (たとえば、SIP URI が**userA@domainZ.com** 、エッジサーバーが**sip.domainX.com**されている場合)。

組織が Lync Online または Office 365 をサブスクライブしていて、独自のドメイン名を使用している場合は、Lync サーバーの自動検出用にネットワークをセットアップするための追加の手順を実行する必要があります。 ネットワーク構成要件は、Lync Windows ストアアプリとモバイルデバイス上の Lync と同じです。 Office 365 wiki の記事「Lync モバイルデバイスをセットアップする」の「ネットワークのセットアップ」の指示に従って[http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822)ください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Lync Windows ストアアプリの展開](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

