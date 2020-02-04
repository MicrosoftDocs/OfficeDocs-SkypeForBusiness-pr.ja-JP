---
title: 'Lync Server 2013: フェデレーション パートナーの検出の有効化または無効化'
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
ms.openlocfilehash: f97a6ab26a3b8b3f011a62cd92bbd0271f781a1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

エッジサーバーを展開して組織のフェデレーションを有効にした時点で、フェデレーションパートナードメインの自動検出をサポートするかどうかを指定する必要があります。 この設定を変更するには、このトピックの手順を使用します。

<div>


> [!NOTE]  
> 次の手順では、組織のフェデレーションを既に有効にしていることを前提としています。 フェデレーションを有効にする方法について詳しくは、展開ドキュメントまたは運用ドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを有効または無効</A>にする」をご覧ください。



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>組織のフェデレーションドメインの自動検出を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。

4.  [**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] の [**フェデレーションユーザーとの通信を有効**にする] で、パートナードメインの自動検出を有効または無効にするには、[**パートナードメインの検出を有効**にする] チェックボックスをオンまたはオフにします。

6.  [**コミット**] をクリックします。

フェデレーションされたユーザーが Lync Server の展開でユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。 詳細については、展開ドキュメントまたは運用マニュアルの「 [Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」を参照してください。 特定のフェデレーションドメインのアクセス制御の詳細については、「 [lync server 2013 で組織の sip フェデレーションドメインを管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)する」、「lync server [2013 で組織の sip フェデレーションプロバイダーを管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)する」、「操作ドキュメントで[LYNC server 2013 で Xmpp フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)する」を参照してください。

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、フェデレーションパートナーの検出を有効または無効にする

フェデレーションパートナーの検出は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>フェデレーションパートナーの検出を有効にするには

  - フェデレーションパートナーの検出を有効にするには、 **Enablepartnerdiscovery**プロパティの値を True ($True) に設定します。 このプロパティ値を変更するには、DNS SRV ルーティングを有効にする必要があることに注意してください。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>フェデレーションパートナーの検出を無効にするには

  - フェデレーションパートナーの検出を無効にするには、 **Enablepartnerdiscovery**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

