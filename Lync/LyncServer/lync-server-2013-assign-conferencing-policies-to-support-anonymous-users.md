---
title: 'Lync Server 2013: 匿名ユーザー サポートのための会議ポリシーの割り当て'
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
ms.openlocfilehash: bab1c3da15bd72bb03233ca05d86e355eebbb233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Lync Server 2013 での匿名ユーザー サポートのための会議ポリシーの割り当て

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

既定では、すべてのユーザーが匿名ユーザーを招待して会議に参加することはできません。 匿名ユーザーをサポートする会議ポリシーを構成し、その会議ポリシーを特定のユーザーに適用することによって、匿名ユーザーを招待できるユーザーを制御します。 匿名ユーザーをサポートするように会議ポリシーを構成する方法の詳細については、「 [Lync server 2013 で会議ポリシーを作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)する」および「 [lync server 2013 のフェデレーションと外部アクセスを管理](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)する」を参照してください。

このセクションの手順を使用して、既に作成済みの会議ポリシーを1人または複数のユーザーまたはユーザーグループに適用します。

<div>


> [!NOTE]  
> ユーザーが匿名ユーザーを招待できるようにポリシーを構成して適用することに加えて、組織の匿名ユーザーのサポートも有効にする必要があります。 詳細については、「 <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013 でパブリックユーザーアクセスを制御するためのポリシーを構成する</A>」を参照してください。



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>会議への匿名参加用のユーザーポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**会議**] をクリックし、次のいずれかの操作を行います。
    
    1.  新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。 [**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、匿名ユーザーとの通信を可能にする、ユーザーポリシーに対して**anonymous**を有効にします)。
    
    2.  既存のユーザーポリシーを構成するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

4.  [**会議ポリシー** ] ダイアログボックスで、[**参加者に匿名ユーザーの招待を許可する**] チェックボックスをオンにします。

5.  [**コミット**] をクリックします。

6.  左側のナビゲーションバーで [**ユーザー**] をクリックし、構成するユーザーアカウントを検索します。

7.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

8.  [**会議ポリシー**] の [ **Lync Server ユーザーの編集**] で、このユーザーに適用する匿名ユーザーアクセス構成が設定されているユーザーポリシーを選択します。
    
    <div>
    

    > [!NOTE]  
    > <STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーインストール設定が適用され、サーバーによって自動的に適用されます。

    
    </div>

ユーザーが会議に匿名ユーザーを招待できるようにするには、組織内の匿名ユーザーのサポートも有効にする必要があります。 詳細については、「展開ドキュメントまたは運用ドキュメントの「 [Lync Server 2013 でのパブリックユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-public-user-access.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

