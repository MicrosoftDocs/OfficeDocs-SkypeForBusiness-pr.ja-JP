---
title: 'Lync Server 2013: 共有線の外観を計画する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6bb768ca892aa684613d1261d88266237ab111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Lync Server 2013 での共有線の外観を計画する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-03-21_

このトピックでは、Lync Server 2013 (累積更新プログラム4月 2016) での共有回線の外観 (SLA) の計画方法について説明します。

共有線の外観は、Lync Server 2013 の機能で、累積的な更新プログラム4月2016は、共有番号と呼ばれる特定の番号で複数の通話を処理します。 SLA では、エンタープライズ voip が有効な Lync ユーザーが複数の通話に応答するために複数の回線を使用して共有番号として構成することができます。 呼び出しは、実際には共有番号で受信されません。代わりに、共有番号の代理人として機能するユーザーに転送されます。 いずれかの代理人が通話を取得できますが、残りの代理人は通話をピックアップしたユーザーと、その結果としてどの回線がビジー状態になったかについての通知を電話で受け取ります。 行数と代理人の両方が、SLA の共有番号に対して構成できます。 さらに、BusyOption などの高度なオプション (すべての回線がビジー状態で行われる状況) および MissedCallOption (代理人が通話を選択しない場合) は、共有番号に対しても構成できます。

SLA は、次の電話デバイスでのみサポートされます (コンピューター、携帯電話、その他のデバイス上の Lync クライアントではサポートされていません)。

  - Polycom VVX300 with ファームウェア更新5.4.1

  - Polycom VVX400 with ファームウェア更新5.4.1

  - Polycom VVX500 with ファームウェア更新5.4.1

  - Polycom VVX600 with ファームウェア更新5.4.1

SLA は、Lync Server 2013 の新しい機能で、累積更新プログラムは4月2016です。

SLA の展開については、「 [Lync Server 2013 での共有線の外観の展開](lync-server-2013-deploy-shared-line-appearance.md)」を参照してください。

<div>

## <a name="feature-list"></a>機能リスト

SLA グループを設定すると、次のことが可能になります。

  - グループ内のすべての委任は、同じ共有番号への着信呼び出しに応答できます。 通話は、PSTN ベースまたは SIP ベースの場合があります。

  - 代理人は、通話を保留および取得できます。

  - 代理人は、SLA グループの外部の番号に通話を転送できます。

  - 代理人は、現在共有番号にある通話数を確認したり、それぞれの通話の状態を表示したりできます。

  - 共有番号に対して同時呼び出しの最大数を構成できます。 また、この最大数に達した後に、追加の呼び出しを処理する方法を設定することもできます。 余分な通話は、通話中の信号を使用して拒否したり、代替番号に転送したり、ボイスメールに転送したりすることができます。

  - 不在着信 (一定の時間が経過した後に呼び出されなかった通話) を処理する方法を構成できます。 グループ id に対してボイスメールを有効にした場合、不在着信は自動的にボイスメールに移動します。 グループ id (共有番号) に対してボイスメールが有効になっていない場合、不在着信を拒否する場合は、通話中の信号を使用して拒否するか、代替番号に転送するか、または切断するかを選択できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

