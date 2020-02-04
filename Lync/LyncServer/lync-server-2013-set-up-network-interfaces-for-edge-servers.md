---
title: 'Lync Server 2013: エッジ サーバーのネットワーク インターフェイスの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Lync Server 2013 でのエッジ サーバーのネットワーク インターフェイスの設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

各エッジサーバーは、外部および内部接続インターフェイスを備えたマルチホームコンピューターです。 [Adapter Domain Name System (DNS)] の設定は、境界ネットワークに DNS サーバーがあるかどうかによって異なります。 DNS サーバーが境界内に存在する場合は、1つ以上の DNS A レコードと次ホップサーバーまたはプール (つまり、ディレクターまたは指定されたフロントエンドプール) が含まれているゾーンと、外部クエリが名前の参照を他のパブリック DNS サーバーに参照していることが必要です。 DNS サーバーが境界内に存在しない場合、エッジサーバーでは、外部 DNS サーバーを使ってインターネット名の参照を解決します。各エッジサーバーは、次ホップのサーバー名を IP アドレスに解決するためにホストを使用します。

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="証券" alt="security" />セキュリティメモ:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>セキュリティ上の理由から、内部ネットワーク内の DNS サーバーにエッジサーバーがアクセスしないようにすることをお勧めします。</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>境界ネットワークの DNS サーバーとのインターフェイスを構成するには

1.  エッジサーバーごとに2つのネットワークアダプターをインストールします。1つは内部接続インターフェイス用、もう1つは外部向きインターフェイス用です。
    
    <div>
    

    > [!IMPORTANT]  
    > 内部サブネットと外部サブネット間のルーティングは許可しないでください。

    
    </div>

2.  外部インターフェイスで、外部境界ネットワーク上の3つの静的 IP アドレス (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) のサブネットを構成し、既定のゲートウェイを外部ファイアウォールの内部インターフェイスにポイントします。 境界 DNS サーバーのペアを指すように、アダプターの DNS 設定を構成します。
    
    <div>
    

    > [!NOTE]  
    > このインターフェイスでは、IP アドレスを1つしか使用できませんが、そのためには、ポートの割り当てを標準以外の値に変更する必要があります。 これは、トポロジビルダーでトポロジを作成するときに決定します。

    
    </div>

3.  内部インターフェイスで、内部境界ネットワークサブネット上の1つの静的 IP アドレスを構成し、既定のゲートウェイを設定しません。 少なくとも1つの DNS サーバーをポイントするようにアダプターの DNS 設定を構成します。できれば、境界 DNS サーバーのペアを指定します。

4.  クライアント、Lync Server 2013、Exchange ユニファイドメッセージング (UM) サーバーが存在するすべての内部ネットワークへの内部インターフェイス上の常設静的ルートを作成します。

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>境界ネットワークに DNS サーバーのないインターフェイスを構成するには

1.  エッジサーバーごとに2つのネットワークアダプターをインストールします。1つは内部接続インターフェイス用、もう1つは外部向きインターフェイス用です。
    
    <div>
    

    > [!IMPORTANT]  
    > 内部サブネットと外部サブネット間のルーティングは許可しないでください。

    
    </div>

2.  外部インターフェイスで、外部境界ネットワークサブネット上の3つの静的 IP アドレスを構成します。 また、外部インターフェイスの既定のゲートウェイも構成します。 たとえば、インターネットに接続するルーターまたは外部ファイアウォールを既定のゲートウェイとして定義します。 DNS サーバーを指すように DNS 設定を構成します。1組の外部 DNS サーバーを指定します。
    
    <div>
    

    > [!NOTE]  
    > 外部インターフェイスに対しては、1つの IP アドレスを使用することはお勧めできませんが、お勧めしません。 この機能を有効にするには、ポートの割り当てを標準以外の値に変更し、通常はクライアント通信用の既定のポート443から離します。 トポロジビルダーでトポロジを作成するときに、IP アドレス設定とポート設定を決定します。

    
    </div>

3.  内部インターフェイスで、内部境界ネットワークサブネット上の1つの静的 IP アドレスを構成し、既定のゲートウェイを設定しません。 アダプターの DNS 設定は空のままにします。

4.  Lync クライアントまたは Lync Server 2013 が実行されているすべての内部ネットワークへの内部インターフェイスで永続的な静的ルートを作成します。

5.  各エッジサーバー上のホストファイルを編集して、次ホップサーバーまたは仮想 IP (VIP) のレコードが含まれるようにします (このレコードは、ディレクター、Standard Edition Server、またはトポロジビルダーで Edge Server の次ホップアドレスとして構成されたフロントエンドプールになります)。 DNS 負荷分散を使用している場合は、次ホッププールの各メンバーに1行を追加します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

