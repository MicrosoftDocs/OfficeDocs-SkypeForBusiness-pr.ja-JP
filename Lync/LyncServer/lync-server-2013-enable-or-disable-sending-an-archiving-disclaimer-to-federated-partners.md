---
title: フェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化
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
ms.openlocfilehash: 1f53e03ebfdc24ff969ff44a9b39149456ab3f16
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

エッジサーバーを展開して組織のフェデレーションを有効にした時点で、アーカイブの免責事項をフェデレーションパートナーに自動的に送信するかどうかを指定する必要があります。 外部通信をアーカイブする場合は、アーカイブの免責事項の送信を有効にする必要があります。 この設定を変更するには、このトピックの手順を使用します。

<div>


> [!NOTE]
> 次の手順では、組織のフェデレーションを既に有効にしていることを前提としています。 フェデレーションを有効にする方法について詳しくは、展開ドキュメントまたは運用ドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを有効または無効</A>にする」をご覧ください。



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>フェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] の [**フェデレーションユーザーとの通信を有効**にする] で、[アーカイブの**免責事項をフェデレーションパートナーに送信**する] チェックボックスをオンまたはオフにして、アーカイブの免責事項の自動送信を有効または無効にします。

6.  [**コミット**] をクリックします。

フェデレーションされたユーザーが Lync Server 2013 の展開でユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。 詳細については、展開ドキュメントまたは操作のドキュメントの「 [Lync Server 2013 で XMPP フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)する」を参照してください。 特定のフェデレーションドメインのアクセス制御の詳細については、「展開ドキュメントまたは操作のドキュメントの「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成する](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してアーカイブ免責事項を有効または無効にする

アーカイブ免責事項の使用は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>アーカイブの免責事項を有効にするには

  - アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>アーカイブの免責事項を無効にするには

  - アーカイブについての免責事項を無効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

