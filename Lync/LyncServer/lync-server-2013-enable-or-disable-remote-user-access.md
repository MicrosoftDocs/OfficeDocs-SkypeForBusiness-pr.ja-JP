---
title: 'Lync Server 2013: リモート ユーザー アクセスの有効化または無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

リモートユーザーは組織内のユーザーで、組織内に Active Directory id が固定されています。 リモートユーザーは、組織のネットワークに接続されていないときに仮想プライベートネットワーク (VPN) を使用して、ネットワークの外部から Lync Server にサインインすることがよくあります。 リモートユーザーには、自宅や外出先で作業している従業員や、信頼できるベンダーなど、企業の資格情報が付与されている信頼できる社員が含まれます。 リモートユーザーに対してリモートユーザーアクセスを有効にすると、サポートされているリモートユーザーはインターネット経由で接続し、Lync Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。

リモートユーザーアクセスをサポートするには、リモートユーザーアクセスを有効にする必要があります。 リモートユーザーアクセスを有効にすると、組織全体で有効にすることができます。 後でリモートユーザーのアクセスを一時的または完全に禁止する必要がある場合は、組織に対して無効にすることができます。 組織のリモートユーザーアクセスを有効または無効にするには、このセクションの手順を使用します。

<div>


> [!NOTE]  
> リモートユーザーアクセスを有効にすることは、アクセスエッジサービスを実行しているサーバーがリモートユーザーとの通信をサポートしていることを示しますが、リモートユーザーは、を構成するまで、組織内のインスタントメッセージング (IM) または会議に参加することはできません。リモートユーザーアクセスの使用を管理するためのポリシーが少なくとも1つあります。 1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。 Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。 リモートユーザーアクセスを使用するためのポリシーの構成の詳細については、「 <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを制御するためのポリシーを構成する</A>」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>組織のリモートユーザーアクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織のリモートユーザーアクセスを有効にするには、[**リモートユーザーアクセスを有効**にする] チェックボックスをオンにします。
    
      - 組織のリモートユーザーアクセスを無効にするには、[**リモートユーザーアクセスを有効に**する] チェックボックスをオフにします。

6.  [**コミット**] をクリックします。

リモートユーザーが Lync Server を実行しているサーバーにサインインできるようにするには、リモートユーザーのアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。 詳細については、「展開ドキュメントまたは運用ドキュメントの「 [Lync Server 2013 でリモートユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-remote-user-access.md)」を参照してください。

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したリモートユーザーアクセスの有効化または無効化

リモートユーザーアクセスを管理するには、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-enable-remote-user-access"></a>リモートユーザーアクセスを有効にするには

  - リモートユーザーアクセスを有効にするには、 **Allowoutsideusers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>リモートユーザーアクセスを無効にするには

  - リモートユーザーアクセスを無効にするには、 **Allowoutsideusers**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

