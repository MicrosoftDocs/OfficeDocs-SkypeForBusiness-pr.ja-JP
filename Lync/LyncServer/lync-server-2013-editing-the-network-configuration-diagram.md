---
title: 'Lync Server 2013: ネットワーク構成ダイアグラムの編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29e65fc660285501cf8d2326505ad46ea227e123
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク構成ダイアグラムの編集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

設計者が Lync Server 2013 で行う作業のほとんどは、計画ツールであり、ネットワークダイアグラム上のエントリの IP アドレスと完全修飾ドメイン名 (Fqdn) のエントリを定義することによって構成されます。 このページに入力された情報は、計画ツールに含まれるレポートやその他の情報に引き継がれます。

![計画ツール、ネットワーク図](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "計画ツール、ネットワーク図")

計画ツールは、IP アドレスと Fqdn の既定のテキストを使用してネットワーク図を作成します。

ネットワーク ダイアグラムを編集して値を入力するには、次の操作を行います。

1.  作業を開始するネットワークの部分を選択します。 たとえば、テキスト**access1.contoso.com**をダブルクリックします。 表示されるダイアログボックスで、サーバー access1.contoso.com の実際の FQDN と実際の IP アドレスを入力し、131.107.155.3 を置き換えます。

2.  **[OK]** をクリックしてエントリを保存します。

3.  IP アドレスと FQDN の編集を続行し、プール内のサーバーのドメイン ネーム システム (DNS) 負荷分散に使用するハードウェア ロード バランサーまたはサーバーのエントリの仮想 IP アドレスを入力していきます。

計画ツールには便利な機能があり、設計者がプール内の各サーバーを個別に編集する代わりに IP アドレス範囲およびサーバー ホスト名を増分して割り当てることができます。次にその例を示します。

1.  プールされたフロントエンドサーバーをダブルクリックします。 ダイアログボックスが開いたら、[**このクラスター内のすべての同等のサーバーの開始点として ip と FQDN を使用しますか?**] を選択します。

2.  たとえば、最初のサーバーの開始値は fe0101.contoso.com で、IP アドレスは192.168.21.122 です。

3.  「 **Fe0.contoso.com**に**フロントエンドサーバーの FQDN**」と入力し、「 **192.168.21.131** 」と入力し**て、[** **OK]** をクリックします。

4.  自動インクリメント機能は、プール内のすべてのサーバーをがそれぞれ経由で fe01 に更新し、すべての IP アドレスを192.168.21.131 から136に更新します。

すべての編集を完了したら、次の手順を実行してトポロジを保存します。

計画ツールのデザインを保存するには、[**ファイル**] をクリックし、[**トポロジの保存**] または [トポロジに名前を付け**て保存**] をクリックします。 **[名前を付けて計画ツールを保存]** ダイアログ ボックスが表示された場合、**[ファイル名]** にファイル名を入力して **[保存]** をクリックします。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での設計の編集](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

