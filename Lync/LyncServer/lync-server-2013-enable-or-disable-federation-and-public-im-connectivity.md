---
title: 'Lync Server 2013: フェデレーションおよびパブリック IM 接続の有効化または無効化'
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
ms.openlocfilehash: edbf03ee2e2772e6df1425ffd666176c1947f0e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-06-24_

フェデレーションのサポートは、信頼された顧客またはパートナー組織のアカウントを持っているユーザー (パートナーのドメインや、サポートしているパブリックインスタントメッセージング (IM) プロバイダーのユーザーを含む) を有効にして、ユーザーとの共同作業を行うことができるようにする必要があります。組織. また、ホストされている exchange サービスプロバイダーを使用して、メールボックスが Microsoft Exchange Online などのホスティングされた Exchange サービス上にあるエンタープライズボイスユーザーに、ボイスメールを提供する必要があります。 これらの外部ドメインとの信頼関係を確立したら、これらのドメインのユーザーに対して、展開にアクセスして Lync Server の通信に参加することを許可することができます。 この信頼関係はフェデレーションと呼ばれており、Active Directory の信頼関係に関連していない、または依存していません。

フェデレーションドメインのユーザーによるアクセスをサポートするには、フェデレーションを有効にする必要があります。 組織のフェデレーションを有効にする場合は、次のオプションを実装するかどうかも指定する必要があります。

  - **パートナードメインの検出**   を有効にするこのオプションを有効にした場合、Lync Server はドメインネームシステム (DNS) レコードを使って、[許可したドメイン] 一覧にないドメインを検出し、検出されたフェデレーションパートナーから受信トラフィックを自動的に評価し、信頼レベル、トラフィック量、管理設定に基づいてトラフィックを制限またはブロックします このオプションが選択されていない場合、フェデレーションされたユーザーのアクセス許可は、[許可したドメイン] リストに含めるドメイン内のユーザーに対してのみ有効になります。 このオプションが選択されているかどうかにかかわらず、フェデレーションドメインでアクセスエッジサービスを実行している特定のサーバーへのアクセスを制限するなど、個々のドメインをブロックまたは許可するように指定することができます。 フェデレーションドメインによるアクセスの制御の詳細については、「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成する](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。

  - **フェデレーションパートナー**    にアーカイブの免責事項を送信する免責事項は、展開にアーカイブすることが適切に行われるフェデレーションパートナーに送信されます。 フェデレーションパートナードメインとの外部通信のアーカイブをサポートしている場合は、アーカイブの免責事項の通知を有効にして、メッセージがアーカイブされていることをパートナーに警告する必要があります。

後でフェデレーションドメインのユーザーによるアクセスを一時的または完全に禁止する場合は、組織のフェデレーションを無効にできます。 このセクションの手順を使用して、組織のフェデレーションされたユーザーアクセスを有効または無効にします。組織でサポートする必要のあるフェデレーションオプションを指定するなどの操作を行います。

<div>


> [!NOTE]  
> 組織でフェデレーションを有効にすると、アクセスエッジサービスを実行しているサーバーでフェデレーションドメインへのルーティングがサポートされるようになります。 フェデレーションドメイン内のユーザーは、フェデレーションされたユーザーアクセスをサポートするために少なくとも1つのポリシーを構成するまで、組織内の IM または会議に参加することはできません。 パブリック IM サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするように少なくとも1つのポリシーを構成するまで、組織内の IM または会議に参加することはできません。 ホストされている exchange サービスを使用して、ホストされているボイスメールポリシーを構成するまで、ホストされている Exchange サービスにメールボックスがあるユーザーのために、通話応答、Outlook Voice Access (ボイスメールを含む)、自動応答サービスを提供することはできません。ルーティング情報を提供します。 他の組織のフェデレーションドメインのユーザーと通信するためのポリシーを構成する方法について詳しくは、「運用ドキュメントの「 <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 で組織の SIP フェデレーションドメインを管理</A>する」をご覧ください。 さらに、IM サービスプロバイダーのユーザーとの通信をサポートする必要がある場合は、それをサポートするようにポリシーを構成し、サポートする個々のサービスプロバイダーのサポートも構成する必要があります。 詳細については、操作のドキュメントの「 <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Lync Server 2013 で組織の SIP フェデレーションプロバイダーを管理</A>する」を参照してください。 ホスト型ボイスメールのポリシーを作成する方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013 でホストされているボイスメールポリシーを管理</A>する」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>組織のフェデレーションされたユーザーアクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。

4.  [**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織のフェデレーションされたユーザーアクセスを有効にするには、[**フェデレーションユーザーとの通信を有効**にする] チェックボックスをオンにします。
    
      - 組織のフェデレーションされたユーザーアクセスを無効にするには、[フェデレーションされ**たユーザーとの通信を有効**にする] チェックボックスをオフにします。

6.  [**フェデレーションユーザーとの通信を有効に**する] チェックボックスをオンにした場合は、次の操作を行います。
    
    1.  パートナードメインの自動検出をサポートするには、[**パートナードメイン探索を有効に**する] チェックボックスをオンにします。
    
    2.  組織で外部通信のアーカイブがサポートされている場合は、[**フェデレーションパートナーにアーカイブの免責事項を送信する**] チェックボックスをオンにします。

7.  [**コミット**] をクリックします。

フェデレーションされたユーザーが Lync Server 2013 の展開でユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。 詳細については、「展開ドキュメントまたは運用ドキュメントの「 [Lync Server 2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」を参照してください。 特定のフェデレーションドメインへのアクセスを制御するには、展開ドキュメントまたは操作のドキュメントの「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成](lync-server-2013-configure-support-for-allowed-external-domains.md)する」を参照してください。

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してフェデレーションおよびパブリック IM 接続を有効または無効にする

フェデレーションとパブリック IM 接続は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理することもできます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を有効にするには

  - フェデレーションとパブリック IM 接続を有効にするには、 **AllowFederatedUsers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を無効にするには

  - フェデレーションとパブリック IM 接続を無効にするには、 **AllowFederatedUsers**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

