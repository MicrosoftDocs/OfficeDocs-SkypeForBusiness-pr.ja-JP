---
title: 'Lync Server 2013: 匿名ユーザーをサポートするための会議ポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4aaa2ee1f6734059983720ca9c3e228ab561a4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Lync Server 2013 で匿名ユーザーをサポートするための会議ポリシーの割り当て

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

既定では、どのユーザーも匿名ユーザーを会議に招待することはできません。 匿名ユーザーをサポートするよう会議ポリシーを構成し、この会議ポリシーを特定のユーザーに適用することで、匿名ユーザーを招待できるユーザーを制御します。 匿名ユーザーをサポートするように会議ポリシーを構成する方法の詳細については、「 [Lync server 2013 で会議ポリシーを作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)する」および「 [lync server 2013 へのフェデレーションと外部アクセスを管理](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)する」を参照してください。

このセクションの手順を使用して、既に作成した会議ポリシーを、1 人以上のユーザーまたは 1 つ以上のユーザー グループに適用します。

<div>


> [!NOTE]  
> ユーザーが匿名ユーザーを招待できるようにするポリシーを構成して適用するほかに、組織の匿名ユーザーのサポートを有効にする必要もあります。 詳細については、「 <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access In Lync Server 2013</A>」を参照してください。



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>会議への匿名参加に対するユーザー ポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**会議**] をクリックし、次のどちらかの操作を行います。
    
    1.  新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**名前**] フィールドに、ユーザー ポリシーの範囲を示す一意の名前を作成します (匿名ユーザーとの通信を有効にするユーザー ポリシーの場合は **EnableAnonymous** など)。
    
    2.  既存のユーザー ポリシーを編集する場合は、表の一覧にある適切なポリシーをクリックして [**編集**] をクリックし、[**詳細の表示**] をクリックします。

4.  [**会議ポリシー**] ダイアログ ボックスの [**参加者に匿名ユーザーの招待を許可する**] チェック ボックスをオンにします。

5.  [**確定**] をクリックします。

6.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

7.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

8.  [**Lync Server ユーザーの編集**] の [**会議ポリシー**] で、このユーザーに適用する匿名ユーザー アクセス構成を含むユーザー ポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG> ] 設定は、既定のサーバーインストール設定を適用し、サーバーによって自動的に適用されます。

    
    </div>

ユーザーが匿名ユーザーを会議に招待できるようにするには、組織で匿名ユーザーのサポートも有効にしておく必要があります。 詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Configure policies to control The Lync Server 2013」](lync-server-2013-configure-policies-to-control-public-user-access.md)を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

