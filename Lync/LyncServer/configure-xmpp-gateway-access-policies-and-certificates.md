---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
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
ms.openlocfilehash: 5b1aab41b1a9af8c7b8df888dcb3a0c8621fa44e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-15_

XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコル (XMPP) に基づいて外部展開を定義します。 XMPP の構成により、Lync ユーザーは次の方法で XMPP ドメインユーザーにアクセスできます。

  - IM とプレゼンス–人物との連絡のみ

  - Lync クライアントでの XMPP フェデレーション連絡先の作成

拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションパートナーをサポートするためにポリシーを構成すると、そのポリシーは XMPP フェデレーションドメインのユーザーに適用されますが、セッション開始プロトコル (SIP) のインスタントメッセージング (IM) サービスプロバイダーのユーザーには適用されません。(たとえば、Windows Live など)、または SIP フェデレーションドメイン。 ユーザーが連絡先を追加して通信できるようにする、各 XMPP フェデレーションドメインに対して XMPP フェデレーションパートナーを構成します。 ポリシーが設定されたら、XMPP ゲートウェイ証明書を構成する必要があります。

<div>


> [!NOTE]  
> XMPP ゲートウェイの移行を開始するには、Lync Server 2013 XMPP ゲートウェイを展開し、アクセスポリシーを構成して、Lync Server 2013 XMPP ゲートウェイのユーザーを有効にする必要があります。 これらの手順を実行する前に、すべてのユーザーを Lync Server 2013 展開に移動する必要があります。 詳細については、「 <A href="configure-xmpp-gateway-on-lync-server-2013.md">Lync Server 2013 での XMPP ゲートウェイの構成</A>」を参照してください。



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>外部アクセスポリシーを構成して Lync Server 2013 XMPP ゲートウェイのユーザーを有効にする

1.  [Lync Server コントロール パネル] を開きます。

2.  左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[**外部アクセスポリシー**] をクリックします。

3.  [**新規作成**] をクリックし、[**ユーザーポリシー**] をクリックします。

4.  外部アクセスのユーザーポリシーの名前を入力します。

5.  外部アクセスユーザーポリシーの説明を入力します。

6.  [**フェデレーションユーザーとの通信を有効にする**] を選択します。

7.  [ **XMPP フェデレーションユーザーとの通信を有効にする**] を選択します。

8.  [**コミット**] をクリックして、サイトまたはユーザーポリシーの変更を保存します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

