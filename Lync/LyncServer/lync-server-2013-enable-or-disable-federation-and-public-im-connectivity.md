---
title: 'Lync Server 2013: フェデレーションとパブリック IM 接続の有効化または無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c94b75aff1b79650adc846d3d761580e9429035d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526794"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-06-24_

組織内のユーザーと共同作業を行うために、パートナードメインや、サポートしているパブリックインスタントメッセージング (IM) プロバイダユーザーのユーザーを含む、信頼できる顧客またはパートナー組織のアカウントを持つユーザーを有効にするには、フェデレーションのサポートが必要です。 また、ホストされている exchange サービスプロバイダーを使用して、Microsoft Exchange Online などのホストされた Exchange サービスにメールボックスがある場合には、フェデレーションを使用して、エンタープライズ Voip ユーザーにボイスメールを提供する必要があります。 これらの外部ドメインとの信頼関係を確立したら、それらのドメイン内のユーザーによる展開へのアクセスと Lync Server の通信への参加を承認することができます。 この信頼関係は、フェデレーションと呼ばれ、Active Directory の信頼関係に関連していないか、またはそれに依存していません。

フェデレーション ドメインのユーザーによるアクセスをサポートするには、フェデレーションを有効にする必要があります。 組織に対してフェデレーションを有効にする場合、次のオプションを実装するかどうかも指定する必要があります。

  - **パートナードメインの検出**     を有効にするこのオプションを有効にした場合、Lync Server はドメインネームシステム (DNS) レコードを使用して、許可されたドメインリストに含まれていないドメインの検出を試み、検出されたフェデレーションパートナーからの受信トラフィックを自動的に評価し、信頼レベル、トラフィックの量、および管理設定に基づいてトラフィックを制限またはブロックします このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。 このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。 フェデレーションドメインによるアクセス制御の詳細については、「 [Configure support for allowed external domains In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。

  - **フェデレーションパートナー**     へのアーカイブ免責事項の送信免責事項については、展開でのアーカイブが実施されていることがフェデレーションパートナーに送信されます。 フェデレーションパートナードメインとの外部通信のアーカイブをサポートする場合は、アーカイブについての免責事項の通知を有効にして、メッセージがアーカイブされることをパートナーに警告する必要があります。

後でフェデレーション ドメイン ユーザーからのアクセスを一時的または永久に禁止する場合は、組織に対するフェデレーションを無効にできます。組織でサポートする適切なフェデレーション オプションを指定するなど、組織に対するフェデレーション ユーザーのアクセスを有効または無効にするには、このセクションの手順を使用します。

<div>


> [!NOTE]  
> 組織に対してフェデレーションを有効にしても、アクセス エッジ サービスを実行するサーバーで、フェデレーション ドメイン宛てのルーティングをサポートすることを指定するだけです。 フェデレーション ユーザー アクセスをサポートするポリシーを少なくとも 1 つ構成するまでは、フェデレーション ドメインのユーザーは、組織の会議や IM に参加できません。 パブリック IM 接続をサポートするポリシーを少なくとも 1 つ構成するまでは、パブリック IM サービス プロバイダーのユーザーも、組織の会議や IM に参加できません。 ルーティング情報を提供するホスト ボイス メール ポリシーを構成するまでは、Lync サーバーは、Hosted Exchange サービスを使用して、Hosted Exchange サービスにあるメールボックスを使用するユーザーに対して、通話応答、Outlook Voice Access (ボイス メールを含む)、および自動応答サービスを提供できません。 他の組織のフェデレーションドメインのユーザーと通信するためのポリシーの構成の詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">MANAGE SIP フェデレーションドメイン for Your Lync Server 2013</A> 」を参照してください。 さらに、IM サービス プロバイダーのユーザーとの通信をサポートする場合は、これをサポートするポリシーを構成し、サポートする個々のサービス プロバイダーのサポートも構成する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理</A> 」を参照してください。 ホストボイスメールポリシーの作成の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies In Lync Server 2013</A> 」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>組織に対するフェデレーション ユーザー アクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**アクセス エッジ構成の編集**] で、次のどちらかの操作を行います。
    
      - 組織に対してフェデレーション ユーザー アクセスを有効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオンにします。
    
      - 組織に対してフェデレーション ユーザー アクセスを無効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオフにします。

6.  [**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオンにした場合は、次を実行します。
    
    1.  パートナー ドメインの自動検出をサポートする場合は、[**パートナー ドメインの検出を有効にする**] チェック ボックスをオンにします。
    
    2.  組織で外部通信のアーカイブをサポートする場合は、[**フェデレーション パートナーにアーカイブについての免責事項を送信する**] チェック ボックスをオンにします。

7.  [**確定**] をクリックします。

フェデレーションユーザーが Lync Server 2013 展開内のユーザーと共同作業できるようにするには、フェデレーションユーザーアクセスをサポートするために少なくとも1つの外部アクセスポリシーを構成する必要があります。 詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Configure policies to control For Lync Server 2013」](lync-server-2013-configure-policies-to-control-federated-user-access.md) を参照してください。 特定のフェデレーションドメインのアクセスを制御するには、「展開」のドキュメントまたは「操作」のドキュメントの「 [Configure support for allowed external domains In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) 」を参照してください。

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してフェデレーションとパブリック IM 接続を有効または無効にする

フェデレーションとパブリック IM 接続は、Windows PowerShell および Set-CsAccessEdgeConfiguration コマンドレットを使用して管理することもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を有効にするには

  - フェデレーションとパブリック IM 接続を有効にするには、**AllowFederatedUsers** プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を無効にするには

  - フェデレーションとパブリック IM 接続を無効にするには、**AllowFederatedUsers** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

