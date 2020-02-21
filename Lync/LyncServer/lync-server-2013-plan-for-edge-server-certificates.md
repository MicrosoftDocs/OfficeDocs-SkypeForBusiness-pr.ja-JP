---
title: 'Lync Server 2013: エッジサーバーの証明書の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ac330914a0d748c366d2a6e40ac0ad9f03543d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Lync Server 2013 でエッジサーバー証明書を計画する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-05_

Lync Server 2013 では、エッジの証明書の作成が簡略化されています。

**エッジ サーバーの証明書のフロー チャート**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

単一のパブリック証明書を作成し、その証明書用に定義されたエクスポート可能な秘密キーがあることを確認した後、証明書ウィザードを使用して次のエッジ サーバー外部インターフェイスに割り当てます。

<div>


> [!IMPORTANT]  
> ワイルドカード証明書は Lync Server ではサポートされていませんが、リバースプロキシを介して簡易 Url を要約するために使用される場合を除きます。 展開で提供される SIP ドメイン名、Web 会議エッジサービス、音声ビデオエッジサービス、および XMPP ドメインごとに、個別のサブジェクト代替名 (San) を定義する必要があります。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 で導入された、現在の証明書の有効期限が切れる前に、オーディオ/ビデオ認証証明書をステージングするには、追加の計画が必要になります。 外部エッジインターフェイスに複数の目的を持つ1つの証明書を使用するのではなく、アクセスエッジサービスと Web 会議エッジサービスに1つずつ、音声ビデオエッジサービスに1つの証明書を割り当てる必要があります。 詳細については、「 <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Lync Server 2013 のステージングの AV および OAuth 証明書」を</A>参照してください。



</div>

<div>


> [!IMPORTANT]  
> エッジサーバーのプールの場合は、各エッジサーバーに秘密キーを持つ証明書をエクスポートし、各エッジサーバーサービスに証明書を割り当てます。 内部エッジサーバー証明書に対して同じ手順を実行し、証明書を秘密キーと共にエクスポートして、各内部エッジインターフェイスに割り当てます。



</div>

  - 証明書用に割り当てられたエクスポート可能な秘密キーがあることの確認

  - アクセスエッジサービス (証明書ウィザードでは、 **SIP アクセスエッジ**と呼ばれる)

  - Web 会議エッジサービス (証明書ウィザードの [ **Web 会議エッジ**] と呼ばれます)

  - 音声ビデオ認証サービス (証明書ウィザードでは、[**音声エッジ外部**] と呼ばれます)

エクスポート可能な秘密キーを持つ単一の内部証明書を作成し、各エッジ サーバー内部インターフェイスに割り当てます。

  - エッジ サーバー (証明書ウィザードでは、[**エッジ内部**] と呼ばれます)

<div>


> [!IMPORTANT]  
> エッジサーバーサービスごとに異なる証明書を使用することができます。 別の証明書を選択することをお勧めする理由は、音声ビデオエッジサービスの証明書に新しいローリング証明書機能を使用する場合です。 この機能の場合は、音声ビデオエッジサービス証明書をアクセスエッジサービスと Web 会議エッジサービスから分離することをお勧めします。 各サービスに対して個別の証明書を取得して割り当てることを選択した場合は、音声ビデオエッジサービスに対してエクスポート可能な秘密キーを要求する必要があります (これが実際には音声ビデオ認証サービスであることを示します)。また、各エッジサーバーの音声ビデオエッジの外部インターフェイスに同じ証明書を割り当てます。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での AV および OAuth 証明書のステージング (セットを使用)-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[エッジサーバーの計画に影響する Lync Server 2013 の変更点](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

