---
title: フェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170bb71b00e01bff53d743122a1712660914ad01
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

エッジ サーバーを展開し、組織に対してフェデレーションを有効にした時点で、フェデレーション パートナーにアーカイブについての免責事項を自動で送信するかどうかを指定する必要があります。 外部通信をアーカイブする場合は、アーカイブについての免責事項の送信を有効にする必要があります。 このトピックの手順を使用して、この構成を変更します。

<div>


> [!NOTE]
> 次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。 フェデレーションを有効にする方法の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを有効または無効</A>にする」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>フェデレーション パートナーへのアーカイブ免責事項の送信を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  [**アクセス エッジ構成の編集**] の [**フェデレーション ユーザーとの通信を有効にする**] で、[**フェデレーション パートナーにアーカイブについての免責事項を送信する**] チェック ボックスをオンまたはオフにして、アーカイブについての免責事項の自動送信を有効または無効にします。

6.  [**確定**] をクリックします。

フェデレーションユーザーが Lync Server 2013 展開内のユーザーと共同作業できるようにするには、フェデレーションユーザーアクセスをサポートするために少なくとも1つの外部アクセスポリシーも構成する必要があります。 詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync Server 2013 での XMPP フェデレーションパートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)」を参照してください。 特定のフェデレーションドメインのアクセス制御の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Configure support for allowed external domains In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) 」を参照してください。

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してアーカイブの免責事項を有効または無効にする

アーカイブ免責事項の使用は、Windows PowerShell と Set-csaccessedgeconfiguration コマンドレットを使用して管理できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>アーカイブについての免責事項を有効にするには

  - アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>アーカイブについての免責事項を無効にするには

  - アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

