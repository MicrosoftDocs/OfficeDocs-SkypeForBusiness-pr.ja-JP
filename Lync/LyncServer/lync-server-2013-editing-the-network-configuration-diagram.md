---
title: 'Lync Server 2013: ネットワーク構成ダイアグラムを編集する'
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
ms.openlocfilehash: dc199098d27364c3bc5f512a48d2e512c7c9d984
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク構成図の編集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

デザイナーが Lync Server 2013、計画ツールで行うことの大半は、IP アドレスとネットワークダイアグラム上のエントリの完全修飾ドメイン名 (Fqdn) のエントリを定義することで構成されています。 このページに入力された情報は、計画ツールに含まれているレポートやその他の情報に引き継がれます。

![計画ツール、ネットワーク図](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "計画ツール、ネットワーク図")

計画ツールでは、IP アドレスと Fqdn の既定のテキストを含むネットワークダイアグラムを作成します。

ネットワーク ダイアグラムを編集して値を入力するには、次の操作を行います。

1.  ネットワークのセクションを選択して作業を開始します。たとえば、**access1.contoso.com** というテキストをダブルクリックします。表示されるダイアログ ボックスで、サーバー access1.contoso.com の実際の FQDN と実際の IP アドレスを入力します (131.107.155.3 を置き換えます)。

2.  [**OK**] をクリックしてエントリを保存します。

3.  IP アドレスと FQDN の編集を続行し、プール内のサーバーのドメイン ネーム システム (DNS) 負荷分散に使用するハードウェア ロード バランサーまたはサーバーのエントリの仮想 IP アドレスを入力していきます。

計画ツールには便利な機能があり、設計者がプール内の各サーバーを個別に編集する代わりに IP アドレス範囲およびサーバー ホスト名を増分して割り当てることができます。次にその例を示します。

1.  プールされているフロント エンド サーバーをダブルクリックします。ダイアログ ボックスが表示されたら、[**このクラスター内の対応するすべてのサーバーの開始点としてこの IP と FQDN を使用しますか?**] チェック ボックスをオンにします。

2.  たとえば、最初のサーバーの開始値は fe0101.contoso.com で、IP アドレスは 192.168.21.122 です。

3.  [**フロント エンド サーバーの FQDN**] に「**fe0.contoso.com**」、[**フロント エンド サーバーの IP アドレス**] に「**192.168.21.131**」と入力し、[**OK**] をクリックします。

4.  自動増分機能により、プール内のすべてのサーバーが fe01 ～ fe06 に更新され、すべての IP アドレスが 192.168.21.131 ～ 136 に更新されます。

すべての編集が完了したら、次の手順を実行してトポロジを保存します。

計画ツールのデザインを保存するには、[**ファイル**] をクリックし、[**トポロジの保存**] または [**トポロジを名前を付けて保存**] をクリックします。 [**名前を付けて計画ツールを保存**] ダイアログ ボックスが表示された場合、[**ファイル名**] にファイル名を入力して [**保存**] をクリックします。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での設計の編集](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

