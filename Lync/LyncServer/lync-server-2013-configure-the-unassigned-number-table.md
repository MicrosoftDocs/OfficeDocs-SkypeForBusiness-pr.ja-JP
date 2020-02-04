---
title: 'Lync Server 2013: 割り当てられていない番号の表の構成'
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
ms.openlocfilehash: b99679d439257b54b6bb40d8e724bb63da4a1ea5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Lync Server 2013 での割り当てられていない番号の表の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-30_

Lync Server 2013 では、組織で有効であっても、ユーザーまたは電話に割り当てられていない電話番号への着信通話に対して実行される処理を指定できます。 発信者はメッセージを聞くことができます。または、別の送信先またはその両方にルーティングすることができます。

割り当てられていない番号の表の構成方法はその使用方法によって異なります。組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。割り当てられていない内線番号を表に入れる場合、特定の番号について行う処理を変更できます。たとえば、顧客サービス デスクの内線番号を変更する場合、古い顧客サービス番号を表に入れ、新しい番号を知らせるアナウンスをそれに割り当てることができます。

<div>


> [!IMPORTANT]  
> [割り当てられていない番号] テーブルを構成する前に、システムで既にお知らせを定義するか、Exchange ユニファイドメッセージング (UM) 自動応答を設定する必要があります。



</div>

<div>


> [!TIP]  
> ユーザーが割り当てられていない番号を呼び出した場合、Lync Server は、未割り当ての番号テーブルを上から下に検索し、最初の一致する範囲を使用します。 したがって、最後の手段として実行される処理は、表の最終範囲に指定されている必要があります。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

[Lync server 2013 で、割り当てられていない番号範囲を作成または変更](lync-server-2013-create-or-modify-an-unassigned-number-range.md)する[lync server 2013 でお知らせを作成](lync-server-2013-create-an-announcement.md)する

</div>

</div>

<span> </span>

</div>

</div>

</div>

