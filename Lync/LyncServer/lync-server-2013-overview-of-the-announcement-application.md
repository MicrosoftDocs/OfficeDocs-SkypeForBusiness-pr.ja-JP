---
title: 'Lync Server 2013: お知らせアプリケーションの概要'
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
ms.openlocfilehash: a4c1b9210fcb0734b305a30d27c77b4e81257909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 のお知らせアプリケーションの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-13_

アナウンスメントアプリケーションを展開するときに、割り当てられていない番号をダイヤルしたときに実行されるアクションを決定する、割り当てられていない番号テーブルを構成する必要があります。 割り当てられていない番号テーブルには、組織で有効な電話番号の範囲が含まれており、各範囲を処理するアナウンスメントアプリケーションが指定されています。 発信者が組織で有効な電話番号をダイヤルしても、すべてのユーザーに割り当てられていない場合、Lync Server は、割り当てられていない番号ルーティングテーブルの番号を検索して、どの範囲の番号が一致しているかを特定し、その通話をお知らせにルーティングします。その範囲に対して指定されたアプリケーション。 アナウンスメントアプリケーションは、通話に応答し、音声メッセージを再生し (設定している場合)、電話を切断するか、オペレーターなどの事前に定義された宛先に転送します。 Lync Server Management Shell コマンドレットを使用して、複数の音声メッセージを構成するか、または移行先を転送することができます。

割り当てられていない番号の表の構成方法はその使用方法によって異なります。現在使用されていない特定の番号があり、各番号用に作成したメッセージを再生する必要がある場合、これらの特定の番号を割り当てられていない番号の表に入力できます。たとえば、顧客サービス デスクの番号を変更した場合、古い顧客サービス番号を入力して、新しい番号を知らせるアナウンスをその番号に関連付けることができます。組織から離れた従業員の番号など、割り当てられていない番号を呼び出す発信者に対して一般的なメッセージを再生する必要がある場合、組織内のすべての有効な内線番号の範囲を入力できます。割り当てられていない番号の表は、発信者が現在割り当てられていない番号をダイヤルすると常に呼び出されます。

Lync Server 2013 では、応答グループアプリケーションを使用して、アナウンスメントアプリケーションが自動的にインストールされます。 お知らせと応答グループのアプリケーションは、エンタープライズ Voip 展開の標準的なコンポーネントです。エンタープライズボイスを展開すると、これらの両方のアプリケーションが自動的に展開されます。

</div>

<span> </span>

</div>

</div>

</div>

