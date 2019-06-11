---
title: 'Lync Server 2013: Web サービスの URL を変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335c73a56da1d8b9a28e7089a7cc2238724a322b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>Lync Server 2013 で Web サービスの URL を変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-11-16_

フロントエンドプールと Standard Edition サーバーをセットアップするときに、外部 Web ファームの完全修飾ドメイン名 (FQDN) と関連付けられたポートを構成するオプションがあります。 Lync Server 展開ウィザードを実行したときにこの URL を構成しなかった場合は、これらの設定を手動で構成する必要があります。 通常、管理者はこれらの設定を変更する必要はありません。これは、推奨される既定のポートであるためです。

<div>


> [!NOTE]  
> Standard Edition サーバーの構成中に、次のスクリーンショットが表示されたため、[FQDN の上書き] オプションが無効になっています。 このオプションは、フロントエンドプールで Enterprise Edition サーバーを構成するときに有効になります。



</div>

![Web サービスプール設定を編集]する(images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Web サービスプール設定を編集")する

<div>

## <a name="to-configure-web-services"></a>Web サービスを構成するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

3.  [トポロジビルダー] のコンソールツリーで、[ **Standard Edition フロントエンドサーバー**]、[ **Enterprise Edition フロントエンドプール**]、[**ディレクトリプール**] の [プール名] を選びます。 名前を右クリックし、[**プロパティの編集**] をクリックして、[ **Web サービス**] をクリックします。

4.  **外部 Web サービスの FQDN**を追加または編集して、[ **OK]** をクリックします。
    
    <div>
    

    > [!WARNING]  
    > 複数のフロントエンドプールまたはフロントエンドサーバーがある場合は、外部 Web サービスの FQDN が一意である必要があります。 たとえば、フロントエンドサーバーの外部 Web サービス FQDN を<STRONG>pool01.contoso.com</STRONG>として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して<STRONG>pool01.contoso.com</STRONG>を使用することはできません。 ディレクターも展開する場合、任意のディレクターまたはディレクタープール用に定義された外部 Web サービスの FQDN は、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーから一意である必要があります。

    
    </div>

5.  リッスンおよび公開されているポートが、お使いの環境に対して正しく構成されていることを確認します

6.  環境内のすべての標準エディションサーバー、フロントエンドプール、およびディレクタープールについて、この手順を繰り返します。

7.  コンソールツリーで、[ **Lync Server 2013**] をクリックし、[**操作**] ウィンドウで [**トポロジの公開**] をクリックします。

リッスンポートと発行ポートを構成する際に注意すべき要件がいくつかあります。

  - 表示されるリスニングポートは、各フロントエンドサーバー上でインターネットインフォメーションサーバー (IIS) 用に構成されているポートです。

  - 内部と外部のリッスンポートは、IIS によって異なる必要があります。 外部リッスンポートの場合、通常は、内部 web トラフィック用のハードウェアロードバランサーを表し、1つは外部 web トラフィックのリバースプロキシサーバーを表します。

  - フロントエンドプール、ディレクター、またはディレクタープールの内部 web サービスを上書きして、独自の FQDN を定義することができます。
    
    <div>
    

    > [!WARNING]  
    > 自動定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。

    
    </div>

  - 公開されたポートは、リバースプロキシまたはハードウェアロードバランサーでリスニングポートとして構成されている必要があります。

  - フロントエンドプール (この例では説明しません) については、web トラフィックがハードウェアロードバランサーを介して送信され、内部 SIP プールトラフィックが DNS ロードバランサーを通過するため、内部の SIP プールの FQDN と内部の web サービス FQDN との間に違いがある必要があります。. この要件は満たされている必要があります。

  - Lync Server Standard Edition の展開では、サーバーの負荷を分散できないため、内部 web サービスの FQDN を上書きする必要はありません。

  - 内部 SIP と web トラフィックの両方に使用している環境にハードウェアロードバランサーがある場合、トポロジビルダーで区別することはできません。
    
    Web サービスの Fqdn は、相互に簡単に区別する必要があります。これにより、URL リダイレクションが適切なサーバーにクライアントを確実に指し示すことができます。 たとえば、2つの Fqdn がある場合は、1つの meeting.contoso.com とその他の conferencing.contoso.com に名前を付けることを検討します。 Meet1.contoso.com や meet2.contoso.com などの類似した名前の Fqdn を使用している場合は、リダイレクトの問題が発生する可能性があります。

外部 web サービスは、境界ネットワークのリバースプロキシと連携して動作します。 これらの web サービスを使用して、クライアントが外部アクセスを提供します。 ここで構成された Fqdn は、ユーザーがログオンするときにクライアントに送信され、リモート接続時に HTTPS 接続をリバースプロキシに戻すために使用されます。 リバースプロキシサーバーは、外部 web サービスの FQDN を内部のハードウェアロードバランサーに転送するか、直接プールに転送します。 リバースプロキシは、内部 Web サーバーの IP アドレスに対して、外部 web サービスの FQDN を解決できる必要があります。 外部 web サービスの FDQN、公開インターネットで解決できる必要があります。

内部サーバーが Standard Edition サーバーの場合、内部 FQDN は標準エディションのサーバー FQDN です。 内部サーバーがフロントエンドプールの場合、FQDN は、内部の web ファームサーバーの負荷を分散するハードウェアロードバランサー仮想 IP (VIP) です。 複数の Enterprise Edition サーバーがあるフロントエンドプールでは、ハードウェアロードバランサーが必要です。 Standard Edition サーバーまたは1つの Enterprise Edition フロントエンドサーバーでは、ロードバランサーは必要ありません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

