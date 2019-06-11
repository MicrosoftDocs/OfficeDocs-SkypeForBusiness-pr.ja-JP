---
title: 'Lync Server 2013: 共有線の外観を計画する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 938bc723d9803acc955899a2b625f983d860b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Lync Server 2013 での共有線の外観を計画する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-03-21_

このトピックでは、Lync Server 2013 での共有線の外観 (SLA) を計画する方法について説明します。累積更新プログラム (2016 年4月)

共有された線の外観は、Lync Server 2013 の累積更新プログラムである、共有番号という特定の番号での複数の通話を処理するための、2016年4月の機能です。 SLA では、エンタープライズボイス対応の Lync ユーザーを、複数の回線と複数の通話に応答する共有番号として構成できます。 実際には共有番号で通話を受信するのではなく、共有番号の代理人として機能するユーザーに通話が転送されます。 いずれかの代理人が通話に応答すると、残りの代理人は誰が通話に応答したか、またその結果としてどの回線が通話中になったかを示す通知を自分の電話で受け取ります。 SLA では、回線の番号と代理人の両方を共有番号に対して構成できます。 さらに、BusyOption (すべての回線が通話中のときに実行する処理) と MissedCallOption (通話に応答できる代理人がいない場合の処理) などの高度なオプションも共有番号に対して構成できます。

SLA は、次の電話デバイスでのみサポートされます (コンピューター、携帯電話、その他のデバイス上の Lync クライアントではサポートされていません)。

  - Polycom VVX300 (ファームウェア更新プログラム 5.4.1 インストール済み)

  - Polycom VVX400 (ファームウェア更新プログラム 5.4.1 インストール済み)

  - Polycom VVX500 (ファームウェア更新プログラム 5.4.1 インストール済み)

  - Polycom VVX600 (ファームウェア更新プログラム 5.4.1 インストール済み)

SLA は、Lync Server 2013 の累積更新プログラム、2016年4月の新機能です。

SLA の展開については、「 [Lync Server 2013 で共有線の外観を展開](lync-server-2013-deploy-shared-line-appearance.md)する」を参照してください。

<div>

## <a name="feature-list"></a>機能リスト

SLA グループをセットアップすると次のことが可能になります。

  - グループ内のすべての代理人が同じ共有番号への着信通話に応答できます。PSTN ベースまたは SIP ベースの通話を利用できます。

  - 代理人は、通話に応答することも保留にすることもできます。

  - 代理人は、SLA グループの外部の番号に通話を転送できます。

  - 代理人は、現在の共有番号上の通話数と、それらの各通話のステータスを表示できます。

  - 共有番号で受信する通話の最大数を構成できます。この最大数に達した後にかかってきた通話の処理方法も設定できます。その後の通話に対しては、話中音を流すか、代替番号に転送するか、ボイス メールに転送できます。

  - 不在着信 (一定の時間が経過しても応答されなかった通話) の処理方法を構成できます。グループ ID のボイス メールを有効にした場合、不在着信は自動的にボイス メールに転送されます。グループ ID (共有番号) のボイス メールを有効にしない場合、不在着信に対して話中音を流すか、代替番号に転送するか、切断するかを選ぶことができます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

