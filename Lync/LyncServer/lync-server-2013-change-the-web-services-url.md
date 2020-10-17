---
title: 'Lync Server 2013: Web サービス URL の変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9eb2922913ee95bad11273b2e943812850da4402
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517820"
---
# <a name="change-the-web-services-url-in-lync-server-2013"></a>Lync Server 2013 で Web サービスの URL を変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-11-16_

フロントエンドプールおよび Standard Edition サーバーをセットアップする際に、外部 Web ファームの完全修飾ドメイン名 (FQDN) と関連するポートを構成することができます。 Lync Server 展開ウィザードを実行したときにこの URL を構成しなかった場合は、これらの設定を手動で構成する必要があります。 通常、管理者はこれらの設定を変更する必要はありません。これらは推奨される既定のポートです。

<div>


> [!NOTE]  
> Standard Edition サーバーの構成中に次のスクリーンショットが実行されたため、[上書き FQDN] オプションは無効になっています。 このオプションは、フロントエンドプールで Enterprise Edition サーバーを構成するときに有効になります。



</div>

![Web サービスのプール設定の編集](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Web サービスのプール設定の編集")

<div>

## <a name="to-configure-web-services"></a>Web サービスを構成するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

3.  トポロジビルダーのコンソールツリーで、[ **Standard Edition フロントエンドサーバー**]、[ **Enterprise Edition フロントエンドプール**]、[ **ディレクトリプール**] の順にクリックし、プール名を選択します。 名前を右クリックし、[ **プロパティの編集**]、[ **Web サービス**] の順にクリックします。

4.  [ **外部 Web サービスの FQDN**] を追加または編集し、[ **OK**] をクリックします。
    
    <div>
    

    > [!WARNING]  
    > フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。 たとえば、フロントエンドサーバーの外部 Web サービスの FQDN を <STRONG>pool01.contoso.com</STRONG>として定義した場合、別のフロントエンドプールまたはフロントエンドサーバーに <STRONG>pool01.contoso.com</STRONG> を使用することはできません。 ディレクターを展開している場合は、ディレクターまたはディレクタープールに対して定義されている外部 Web サービスの FQDN が、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーとも一意である必要があります。

    
    </div>

5.  リッスンポートと公開ポートが環境に対して正しく構成されていることを確認します。

6.  環境内のすべての Standard Edition サーバー、フロントエンドプール、およびディレクタープールに対して、これらの手順を繰り返します。

7.  コンソールツリーで、[ **Lync Server 2013**] をクリックし、[ **操作** ] ウィンドウで [ **トポロジの公開**] をクリックします。

リッスンポートと発行ポートを構成する際には、いくつかの要件を認識する必要があります。

  - 表示されるリスニングポートは、各フロントエンドサーバー上のインターネットインフォメーションサービス (IIS) 用に構成されているポートです。

  - 内部および外部のリスニングポートは IIS で異なる必要があります。 外部リスニングポートについては、通常、内部 web トラフィック用のハードウェアロードバランサーを表し、もう1つは外部 web トラフィック用のリバースプロキシサーバーを表します。

  - フロントエンドプール、ディレクター、またはディレクタープールの内部 web サービスを上書きして、独自の FQDN を定義することができます。
    
    <div>
    

    > [!WARNING]  
    > 内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。

    
    </div>

  - 公開ポートは、リバースプロキシまたはハードウェアロードバランサー上で、リッスンポートとして構成する必要があります。

  - フロントエンドプール (例には示されていません) の場合、web トラフィックはハードウェアロードバランサーを通過し、内部 SIP プールトラフィックは DNS ロードバランサーを経由するため、内部 SIP プールの FQDN は内部 web サービスの FQDN とは別のものにする必要があります。 この要件を満たす必要があります。

  - Lync Server Standard Edition の展開では、このサーバーの負荷分散ができないため、内部 web サービスの FQDN を上書きする必要はありません。

  - 内部 SIP と web トラフィックの両方で使用している環境にハードウェアロードバランサーがある場合は、トポロジビルダーで区別することはできません。
    
    Web サービスの Fqdn は、相互に簡単に区別する必要があります。これにより、URL リダイレクトがクライアントを適切なサーバーに確実に参照できるようになります。 たとえば、2つの Fqdn がある場合は、1つの meeting.contoso.com とその他の conferencing.contoso.com に名前を付けることを検討します。 Meet1.contoso.com や meet2.contoso.com など、似た名前の Fqdn を使用している場合は、リダイレクトの問題が発生する可能性があります。

外部 web サービスは、境界ネットワークのリバースプロキシと連携して動作します。 これらの web サービスを使用してクライアントに外部アクセスを提供します。 ここで構成された Fqdn は、ユーザーがログオンしたときにクライアントに送信され、リモート接続時にリバースプロキシに HTTPS 接続を行うために使用されます。 リバースプロキシサーバーは、外部 web サービスの FQDN を内部のハードウェアロードバランサーに転送するか、直接プールに転送します。 リバースプロキシは、外部 web サービスの FQDN を内部 Web サーバーの IP アドレスに解決できる必要があります。 外部 web サービスの FDQN、パブリックインターネットで解決可能である必要があります。

内部サーバーが Standard Edition サーバーの場合、内部 FQDN は Standard Edition サーバーの FQDN です。 内部サーバーがフロントエンドプールの場合、FQDN は、内部 web ファームサーバーの負荷を分散するハードウェアロードバランサー仮想 IP (VIP) です。 複数の Enterprise Edition サーバーを使用するフロントエンドプールには、ロードバランサー機器が必要です。 Standard Edition サーバーまたは1つの Enterprise Edition フロントエンドサーバーでロードバランサーを使用する必要はありません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

