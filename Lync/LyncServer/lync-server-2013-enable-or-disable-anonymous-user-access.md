---
title: 'Lync Server 2013: 匿名ユーザーアクセスの有効化または無効化'
description: 'Lync Server 2013: 匿名ユーザーアクセスを有効または無効にします。'
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
ms.openlocfilehash: 4ca36cffc25cd31d057b00c22cb299c56cfd7b3c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544773"
---
# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Lync Server 2013 で匿名ユーザーアクセスを有効または無効にする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

匿名ユーザーは、組織の Active Directory ドメインサービスまたはサポートされているフェデレーションドメインにユーザーアカウントを持たないユーザーですが、社内の会議にリモートで参加するよう招待することができます。 会議への匿名参加を許可することにより、匿名ユーザー (つまり、会議キーまたは会議キーで本人のみが確認されるユーザー) が会議に参加できるようになります。 匿名参加を許可するには、組織に対して有効にする必要があります。

後で匿名ユーザーによるアクセスを一時的または完全に禁止する場合は、組織に対して無効にすることができます。 このセクションの手順を使用して、組織の匿名ユーザーアクセスを有効または無効にします。

<div>


> [!NOTE]  
> 組織で匿名ユーザーアクセスを有効にすることで、アクセスエッジサービスを実行しているサーバーが匿名ユーザーによるアクセスをサポートすることを指定するだけです。 匿名ユーザーは、少なくとも1つの会議ポリシーを構成して、1人以上のユーザーまたはユーザーグループに適用するまでは、組織内のすべての会議に参加できません。 匿名ユーザーを会議に招待できるユーザーは、匿名ユーザーをサポートするように構成された会議ポリシーが割り当てられているユーザーのみです。 匿名ユーザーの招待をサポートするための会議ポリシーの構成の詳細については、「 <A href="lync-server-2013-conferencing-policies.md">Lync Server 2013 の会議ポリシー</A>」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>組織の匿名ユーザーアクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織で匿名ユーザーアクセスを有効にするには、[ **匿名ユーザーとの通信を有効** にする] チェックボックスをオンにします。
    
      - 組織の匿名ユーザーアクセスを無効にするには、[ **匿名ユーザーとの通信を有効に** する] チェックボックスをオフにします。

6.  [**確定**] をクリックします。

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して匿名ユーザーアクセスを有効または無効にする

匿名ユーザーアクセスを管理するには、Windows PowerShell と **set-csaccessedgeconfiguration** コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-anonymous-user-access"></a>匿名ユーザーアクセスを有効にするには

  - 匿名ユーザーアクセスを有効にするには、 **AllowAnonymousUsers** プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>匿名ユーザーアクセスを無効にするには

  - 匿名ユーザーアクセスを無効にするには、 **AllowAnonymousUsers** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の会議ポリシー設定のリファレンス](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

