---
title: XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: d7353d6bfdd4c045d9d592ababf92f2aaaec2365
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP ゲートウェイ アクセス ポリシーおよび証明書の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-15_

XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:

  - IM およびプレゼンス (1 対 1 のみ)

  - XMPP フェデレーションからの連絡先を Lync クライアントに作成

When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.

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

