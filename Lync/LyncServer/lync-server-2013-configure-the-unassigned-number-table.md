---
title: 'Lync Server 2013: 割り当てられていない番号の表を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb3aa60273439c94a5d936efe826e77dcc683be
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Lync Server 2013 で割り当てられていない番号の表を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-30_

Lync Server 2013 では、組織で有効になっているが、ユーザーまたは電話に割り当てられていない電話番号への着信呼び出しに対して実行される処理を指定できます。 発信者は、メッセージを聞くことも、別の宛先にルーティングすることもできます。またはその両方を指定することもできます。

割り当てられていない番号の表の構成方法はその使用方法によって異なります。 組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。 割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。 有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。 割り当てられていない拡張子を表に含める場合は、特定の番号に対して発生する操作を変更できます。 たとえば、顧客サービスデスクの拡張機能を変更した場合は、古い顧客サービス番号を表に含めて、新しい番号を提供するアナウンスに割り当てることができます。

<div>


> [!IMPORTANT]  
> 割り当てられていない番号の表を構成する前に、システムにアナウンスが定義されているか、Exchange ユニファイドメッセージング (UM) 自動応答が設定されている必要があります。



</div>

<div>


> [!TIP]  
> 他のユーザーが割り当てられていない番号を呼び出すと、Lync Server は、未使用の番号の表を上から順に検索し、最初の一致する範囲を使用します。 そのため、最後の手段として実行するアクションは、テーブルの最後の範囲に対して指定する必要があります。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

[Lync server 2013 で割り当てられていない番号範囲を作成または変更](lync-server-2013-create-or-modify-an-unassigned-number-range.md)する[lync server 2013 でアナウンスを作成](lync-server-2013-create-an-announcement.md)する

</div>

</div>

<span> </span>

</div>

</div>

</div>

