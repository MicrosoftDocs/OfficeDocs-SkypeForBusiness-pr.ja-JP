---
title: 'Lync Server 2013: 割り当てられていない電話番号の構成'
description: 'Lync Server 2013: 割り当てられていない電話番号を構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 702f297ea0a77d5e81be8b650a514ea4fa939d32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578053"
---
# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Lync Server 2013 で割り当てられていない電話番号を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server を使用すると、組織に対して有効であっても、ユーザーまたは電話に割り当てられていない電話番号への着信呼び出しに対して行われる処理を構成できます。 このような通話の処理を構成するには、割り当てられていない番号の表を設定します。 この表を使用して、アナウンスアプリケーションまたは Exchange UM サーバーへの通話をルーティングできます。

割り当てられていない番号の表の構成方法はその使用方法によって異なります。組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。割り当てられていない内線番号を表に入れる場合、特定の番号について行う処理を調整できます。たとえば、顧客サービス デスクの内線番号を変更する場合、古い顧客サービス番号を表に入れ、新しい番号を知らせるアナウンスをそれに割り当てることができます。

<div>


> [!IMPORTANT]  
> 割り当てられていない番号の表を構成する前に、1つまたは複数のアナウンスを定義しているか、または Exchange UM 自動応答を設定しておく必要があります。 アナウンスの作成の詳細については、「 <A href="lync-server-2013-create-an-announcement.md">Lync Server 2013 のアナウンスを作成</A>する」を参照してください。 Exchange UM 設定が構成されているかどうかを確認するには、 <STRONG>Get-CsExUmContact</STRONG> コマンドレットを実行します。 詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">get-help</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 で割り当てられていない番号範囲を作成または変更する](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Lync Server 2013 で割り当てられていない番号範囲を削除する](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

