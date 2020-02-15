---
title: XMPP ゲートウェイアクセスポリシーと証明書を構成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e785b3f3df2e37bc7cdaaaccdb2e027652a0da36
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP ゲートウェイアクセスポリシーと証明書を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-15_

XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づいて外部展開を定義します。XMPP を構成すると、Lync ユーザーは XMPP ドメイン ユーザーに次の方法でアクセスできます。

  - IM およびプレゼンス (1 対 1 のみ)

  - XMPP フェデレーションからの連絡先を Lync クライアントに作成

XMPP (eXtensible Messaging and Presence Protocol) フェデレーション パートナーをサポートするポリシーを構成すると、そのポリシーは XMPP フェデレーション ドメインのユーザーには適用されますが、SIP (セッション開始プロトコル) インスタント メッセージング (IM) サービス プロバイダー (Windows Live など) のユーザーや、SIP フェデレーション ドメインのユーザーには適用されません。ユーザーによる連絡先の追加や通信を許可する XMPP フェデレーション ドメインごとに XMPP フェデレーション パートナーを構成します。ポリシーを設定したら、XMPP ゲートウェイ証明書を構成する必要があります。

<div>


> [!NOTE]  
> XMPP ゲートウェイの移行を開始するには、Lync Server 2013 XMPP ゲートウェイを展開し、Lync Server 2013 XMPP ゲートウェイのユーザーを有効にするためのアクセスポリシーを構成する必要があります。 これらの手順を実行する前に、すべてのユーザーを Lync Server 2013 展開に移動する必要があります。 詳細については、「 <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway On Lync Server 2013</A>」を参照してください。



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Lync Server 2013 XMPP ゲートウェイに対してユーザーを有効にする外部アクセス ポリシーを構成する

1.  [Lync Server コントロール パネル] を開きます。

2.  左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

3.  [**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。

4.  外部アクセス ユーザー ポリシーの名前を入力します。

5.  外部アクセス ユーザー ポリシーの説明を入力します。

6.  [**フェデレーション ユーザーとの通信を有効にする**] を選択します。

7.  [**XMPP フェデレーション ユーザーとの通信を有効にする**] を選択します。

8.  [**確定**] をクリックして、サイトまたはユーザー ポリシーへの変更を保存します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

