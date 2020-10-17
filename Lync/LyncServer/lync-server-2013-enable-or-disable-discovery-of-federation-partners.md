---
title: 'Lync Server 2013: フェデレーションパートナーの検出の有効化または無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff9fb4e0b243cc1ce9b51deac1c4021f9b3dff56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526824"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

エッジ サーバーを展開して組織のフェデレーションを有効にした際に、フェデレーション パートナー ドメインの自動検出をサポートするかどうかを指定しています。 このトピックの手順を使用して、この構成を変更します。

<div>


> [!NOTE]  
> 次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。 フェデレーションを有効にする方法の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを有効または無効</A> にする」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>組織に対してフェデレーション ドメインの自動検出を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**アクセス エッジ構成の編集**] で、[**フェデレーション ユーザーとの通信を有効にする**] の [**パートナー ドメインの検出を有効にする**] チェック ボックスをオンまたはオフにして、パートナー ドメインの自動検出を有効また無効にします。

6.  [**確定**] をクリックします。

フェデレーションユーザーが Lync Server 展開内のユーザーと共同作業できるようにするには、フェデレーションユーザーアクセスをサポートするために少なくとも1つの外部アクセスポリシーも構成する必要があります。 詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync Server 2013 でのフェデレーションとパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 」を参照してください。 特定のフェデレーションドメインのアクセス制御の詳細については、「操作」のドキュメントの「 [MANAGE sip フェデレーションドメイン](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)を lync server 2013 で管理する」、「 [組織の sip フェデレーションプロバイダーを lync server 2013 で管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) する」、および「 [LYNC server 2013 で Xmpp フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) する」を参照してください。

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したフェデレーションパートナーの検出の有効化または無効化

フェデレーションパートナーの検出は、Windows PowerShell と Set-CsAccessEdgeConfiguration コマンドレットを使用して管理できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>フェデレーションパートナーの検出を有効にするには

  - フェデレーションパートナーの検出を有効にするには、 **Enablepartnerdiscovery** プロパティの値を True ($True) に設定します。 このプロパティの値を変更するには、DNS SRV ルーティングを有効にする必要があることに注意してください。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>フェデレーションパートナーの検出を無効にするには

  - フェデレーションパートナーの検出を無効にするには、 **Enablepartnerdiscovery** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

