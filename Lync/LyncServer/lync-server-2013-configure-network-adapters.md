---
title: 'Lync Server 2013: ネットワーク アダプターの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Lync Server 2013 ネットワーク アダプターの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

1つ以上の IP アドレスを外部ネットワークアダプターに割り当て、少なくとも1つの IP アドレスを内部ネットワークアダプターに割り当てる必要があります。

次の手順では、Forefront Threat Management Gateway (TMG) 2010 または Internet Information Server アプリケーション要求ルーティングのいずれかを実行しているサーバーに、2つのネットワークアダプターがあります。

  - Web サイト (通常はインターネット経由) に接続しようとしているクライアントの場合は、パブリックまたは外部のネットワークアダプター。

  - Web サービスをホストしている Lync Server を実行している内部サーバーの場合は、プライベートまたは内部ネットワークインターフェイス。

<div>


> [!IMPORTANT]  
> エッジサーバーの場合と同様に、外部ネットワークアダプターでのみ既定のゲートウェイを設定します。 既定のゲートウェイは、インターネットへのトラフィックを指示するルーターまたは外部向けのファイアウォールの IP アドレスです。 リバースプロキシから内部のネットワークアダプターへのトラフィックについては、web 発行ルールによって参照されるサーバーを含むすべてのサブネットに対して永続的な静的ルート (Windows Server の route コマンドなど) を使用する必要があります。 常設ルートを設定しても、コンピューターはルーターになりません。 IP 転送が有効になっていない場合、そのコンピューターは、別のネットワークに送信される特定のトラフィックを適切なインターフェイスに転送するためだけに動作しています。 これは、基本的に2つのゲートウェイを設定することです。1つは既定として外部ネットワークを指し、もう1つは内部インターフェイスとルーターなどのネットワークへのトラフィック用です。<BR>ただし、ネットワークのルーターがルートの概要として構成されている場合、すべてのサブネットに対して永続的なルートを作成する必要はありません。 ルーターが定義されているネットワークへの常設ルートを作成し、そのルーターを既定のゲートウェイとして使用します。 ネットワークがどのように構成されていて、どの固定ルートを作成する必要があるかについてのガイダンスが必要な場合は、会社のネットワークエンジニアにお問い合わせください。<BR>リバースプロキシは、web 発行ルールで使われる内部ディレクターまたはフロントエンドサーバーと次ホッププールの Fqdn の DNS ホスト (A) レコードを解決できる必要があります。 エッジサーバーの場合と同様に、セキュリティ上の理由から、内部ネットワーク内にある DNS サーバーを使用するようにリバースプロキシを構成しないことをお勧めします。 つまり、境界に DNS サーバーが必要です。または、これらの各 Fqdn をサーバーの内部 IP アドレスに解決する逆プロキシの HOSTS ファイルエントリが必要です。



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>リバースプロキシコンピューターのネットワークアダプターカードを構成するには

1.  リバースプロキシとして実行されている windows server 2008、windows server 2008 R2、windows Server 2012、または Windows Server 2012 R2 サーバーで、[**スタート**] をクリックし、[**コントロールパネル**]、[**ネットワークと共有センター**] の順にクリックして、[**アダプターの設定の変更**] を**クリックします**。

2.  外部インターフェイスとして使用する外部ネットワーク接続を右クリックし、[**プロパティ**] をクリックします。

3.  [**プロパティ**] ページで、[**ネットワーク**] タブをクリックし、[**この接続は次の項目を使用**します] ボックスの一覧の [ **Internet Protocol Version 4 (TCP/IPv4)** ] をクリックし、[**プロパティ**] をクリックします。

4.  [ **Internet Protocol (tcp/ip) のプロパティ**] ページで、ネットワークアダプターを接続するネットワークサブネットに合わせて IP アドレスを構成します。
    
    <div>
    

    > [!NOTE]  
    > リバースプロキシが、HTTPS/TCP/443 を使用する他のアプリケーションによって既に使用されている場合は、Outlook Web Access を公開する場合、既存のルールや web リスナーに干渉しないように、別の IP アドレスを追加する必要があります。これにより、HTTPS/TCP/443 で Lync Server 2013 Web サービスを公開することができます。また、既存の証明書を新しい外部の FQDN 名に追加する証明書と置き換えます。

    
    </div>

5.  [ **Ok**] をクリックし、[ **ok**] をクリックします。

6.  [**ネットワーク接続**] で、内部インターフェイスに使用する内部ネットワーク接続を右クリックし、[**プロパティ**] をクリックします。

7.  手順3から5を繰り返して、内部ネットワーク接続を構成します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

