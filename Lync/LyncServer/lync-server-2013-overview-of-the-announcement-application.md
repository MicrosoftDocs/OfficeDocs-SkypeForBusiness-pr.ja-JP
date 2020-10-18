---
title: 'Lync Server 2013: アナウンスメントアプリケーションの概要'
description: 'Lync Server 2013: アナウンスメントアプリケーションの概要。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15e9834be5edc67777f258f8d041e134287a891a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577253"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 のアナウンスアプリケーションの概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-13_

アナウンスメントアプリケーションを展開するときに、割り当てられていない番号にダイヤルしたときに実行されるアクションを決定する割り当てられていない番号の表を構成する必要があります。 割り当てられていない番号の表には、組織に対して有効な電話番号の範囲が含まれており、各範囲を処理するアナウンスアプリケーションを指定します。 発信者が組織に対して有効な電話番号をダイヤルしたが、だれにも割り当てられていない場合、Lync Server は、未使用の番号ルーティングテーブルから番号を検索し、その番号がどの範囲に該当するかを識別し、その範囲に指定されたアナウンスアプリケーションに通話をルーティングします。 アナウンスアプリケーションは、通話に応答して、音声メッセージを再生し (そのように構成した場合)、呼び出しを切断するか、またはオペレーターなどの事前に決められた送信先に転送します。 Lync Server 管理シェルコマンドレットを使用して、複数のオーディオメッセージを構成したり、宛先を転送したりすることができます。

割り当てられていない番号の表の構成方法はその使用方法によって異なります。 使用されなくなった特定の番号が、それぞれの番号に対してカスタマイズされたメッセージを再生する必要がある場合は、これらの番号を割り当てられていない番号の表に入力することができます。 たとえば、顧客サービスデスクの番号を変更した場合は、古い顧客サービス番号を入力して、それを新しい番号を提供するアナウンスに関連付けることができます。 割り当てられていない番号を呼び出すユーザー (組織を退職した従業員など) に対して、一般的なメッセージを再生する場合は、組織内のすべての有効な内線番号の範囲を入力できます。 割り当てられていない番号の表は、発信者が現在割り当てられていない番号をダイヤルしたときに呼び出されます。

Lync Server 2013 では、アナウンスアプリケーションは応答グループアプリケーションと共に自動的にインストールされます。 アナウンスメントおよび応答グループアプリケーションは、エンタープライズ Voip 展開の標準的なコンポーネントです。エンタープライズ Voip を展開すると、これらの両方のアプリケーションが自動的に展開されます。

</div>

<span> </span>

</div>

</div>

</div>

