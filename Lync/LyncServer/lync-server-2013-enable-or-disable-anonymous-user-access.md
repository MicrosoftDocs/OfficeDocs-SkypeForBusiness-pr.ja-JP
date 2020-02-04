---
title: 'Lync Server 2013: 匿名ユーザー アクセスの有効化または無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d38d0d9f50ff06b2f7eb95944d9214c2c4c64a5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Lync Server 2013 匿名ユーザー アクセスの有効化または無効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

匿名ユーザーは、組織の Active Directory ドメインサービスまたはサポートされているフェデレーションドメインでユーザーアカウントを持っていないユーザーですが、オンプレミスの会議にリモートで参加するよう招待することができます。 会議への匿名参加を許可することにより、匿名ユーザーを有効にします (つまり、会議または会議キーによって id が確認されたユーザーのみ)、会議に参加できます。 匿名での参加を許可するには、組織で匿名参加を有効にする必要があります。

匿名ユーザーによるアクセスを一時的または完全に回避する必要がある場合は、組織で無効にすることができます。 このセクションの手順を使用して、組織の匿名ユーザーアクセスを有効または無効にします。

<div>


> [!NOTE]  
> 組織に対して匿名ユーザーアクセスを有効にすると、アクセスエッジサービスを実行しているサーバーでは、匿名ユーザーによるアクセスがサポートされることを指定するだけです。 匿名ユーザーは、少なくとも1つの会議ポリシーを構成し、1つ以上のユーザーまたはユーザーグループに適用するまで、組織内のすべての会議に参加することはできません。 匿名ユーザーを会議に招待できるユーザーは、匿名ユーザーをサポートするように構成されている会議ポリシーが割り当てられているユーザーのみです。 匿名ユーザーの招待をサポートするように会議ポリシーを構成する方法について詳しくは、「 <A href="lync-server-2013-conferencing-policies.md">Lync Server 2013 の会議ポリシー</A>」をご覧ください。



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>組織の匿名ユーザーアクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。

4.  [**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織の匿名ユーザーアクセスを有効にするには、[**匿名ユーザーとの通信を有効**にする] チェックボックスをオンにします。
    
      - 組織の匿名ユーザーアクセスを無効にするには、[**匿名ユーザーとの通信を有効**にする] チェックボックスをオフにします。

6.  [**コミット**] をクリックします。

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して匿名ユーザーのアクセスを有効または無効にする

Windows PowerShell と**CsAccessEdgeConfiguration**コマンドレットを使用して、匿名ユーザーのアクセスを管理できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-anonymous-user-access"></a>匿名ユーザーのアクセスを有効にするには

  - 匿名ユーザーのアクセスを有効にするには、 **AllowAnonymousUsers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>匿名ユーザーのアクセスを無効にするには

  - 匿名ユーザーのアクセスを無効にするには、 **AllowAnonymousUsers**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

