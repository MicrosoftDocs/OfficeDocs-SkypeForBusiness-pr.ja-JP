---
title: 'Lync Server 2013: コール パーク障害復旧の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a76052297e527e24fd3daf0c03d02661c7ddc255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 でのコール パーク障害復旧の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-30_

このセクションでは、障害回復用のコールパークアプリケーションを準備する方法と、障害回復プロセスの考慮事項について説明します。

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>コールパークの障害回復の準備

障害回復の手順を準備して実行する場合は、次の点にご注意ください。

  - キャパシティ計画を行うときの障害回復計画を立てます。 障害回復キャパシティの場合、ペア化されたプール内の各プールは、両方のプールのコールパークサービスの作業負荷を処理できる必要があります。 通話パークキャパシティ計画の詳細については、「 [Lync Server 2013 でのコールパークのキャパシティ計画](lync-server-2013-capacity-planning-for-call-park.md)」を参照してください。

  - 障害回復中に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、バックアッププールで実行されているコールパークサービスを使用します。 そのため、障害回復中のコールパークのサポートでは、プライマリプールとバックアッププールの両方でコールパークアプリケーションを展開して有効にする必要があります。

  - 各プールには、そのプールに所属しているユーザーがパーキング通話に使用するために、有効な範囲の軌道番号が必要です。

  - 通話パーク用にアップロードされた、カスタマイズした音楽の個別のバックアップコピーを常に保持しておきます。 これらのファイルは、Lync Server 2013 の障害回復プロセスの一部としてはバックアップされません。また、プールにアップロードされたファイルが破損、破損、または消去された場合は、失われます。

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>コールパーク障害回復に関する考慮事項

1組のコールパークアプリケーションの構成設定と、1つのプールにつき1つのカスタマイズされた音楽オンホールドオーディオファイルを定義できます。 これらの設定には、タイムアウトしきい値、保留中の音楽、最大通話ピックアップ試行回数、タイムアウト URI が含まれます。 これらの構成設定を表示するには、 **CsCpsConfiguration**コマンドレットを実行します。 **CsCpsConfiguration**コマンドレットの詳細については、「 [get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)」を参照してください。

障害回復中に、コールパークはバックアッププールのコールパークアプリケーションを使用するため、プライマリプールの設定はバックアップされません。 プライマリプールを復元できない場合に、プライマリプールの代わりに新しいプールを展開すると、プライマリプールの設定は失われ、新規プール内のコールパーク設定とカスタマイズされた音楽の保留中のオーディオファイルを再設定する必要があります。

別の完全修飾ドメイン名 (FQDN) で新しいプールを展開してプライマリプールを置き換える場合は、プライマリプールに関連付けられていたすべてのコールパークの範囲を、新しいプールの FQDN に再割り当てする必要があります。 新しいプールに軌道範囲を再割り当てするには、Lync Server コントロールパネルまたは**CsCallParkOrbit**コマンドレットを使用できます。 **CsCallParkOrbit**コマンドレットの詳細については、「 [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

