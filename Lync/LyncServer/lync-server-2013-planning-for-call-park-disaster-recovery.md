---
title: 'Lync Server 2013: コールパークの障害復旧の計画'
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
ms.openlocfilehash: f221947975c00eccefe50cb5ca72b264c9596014
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497754"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 でのコールパーク障害復旧の計画

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-30_

このセクションでは、障害復旧のためのコールパークアプリケーションの準備方法と、障害復旧プロセスに関するいくつかの考慮事項について説明します。

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>コールパーク障害復旧の準備

障害復旧手順を作成し、実行する際は、次に留意してください。

  - 処理能力計画を行う際に障害復旧を計画します。 障害復旧のためには、ペアになっているプールの各プールで、両方のプールのコールパークサービスのワークロードを処理できる必要があります。 コールパーク容量計画の詳細については、「 [Lync Server 2013 のコールパークの容量計画](lync-server-2013-capacity-planning-for-call-park.md)」を参照してください。

  - 障害復旧の間、フェールオーバー プロセスの一部としてバックアップ プールにリダイレクトされたユーザーは、バックアップ プールで実行されるたコール パーク サービスを使用します。 そのため、障害復旧時のコールパークのサポートでは、プライマリプールとバックアッププールの両方でコールパークアプリケーションを展開して有効にする必要があります。

  - 各プールは、そのプールに所属しているユーザーがパーキング コールに使用するための有効な範囲のオービット数を持っている必要があります。

  - コールパーク用にアップロードされたカスタマイズした保留音のバックアップコピーは常に別個に保管してください。 これらのファイルは、Lync Server 2013 の障害復旧プロセスの一部としてはバックアップされず、プールにアップロードされたファイルが破損、破損、または消去されると、失われます。

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>コールパーク障害復旧に関する考慮事項

1つのプールに対して1セットのコールパークアプリケーション構成設定と1つのカスタマイズされた音楽オンホールドオーディオファイルのみを定義できます。 これらの設定には、タイムアウトしきい値、保留音、コール ピックアップの最大試行回数、およびタイムアウト URI が含まれます。 構成設定を表示するには、**Get-CsCpsConfiguration** コマンドレットを実行します。 **New-cscpsconfiguration**コマンドレットの詳細については、「 [new-cscpsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)」を参照してください。

障害復旧時に、コールパークはバックアッププール内のコールパークアプリケーションを使用するので、プライマリプールの設定はバックアップされません。 プライマリプールを回復できない場合に、プライマリプールを置き換える新しいプールを展開すると、プライマリプールからの設定は失われ、新しいプールのコールパーク設定とカスタマイズされた音楽オンホールドオーディオファイルを再構成する必要があります。

プライマリプールを置き換えるために別の完全修飾ドメイン名 (FQDN) を使用して新しいプールを展開する場合は、プライマリプールに関連付けられたすべてのコールパークオービット範囲を新しいプールの FQDN に再割り当てする必要があります。 オービット範囲を新しいプールに再割り当てするには、Lync Server コントロールパネルまたは **get-cscallparkorbit** コマンドレットのいずれかを使用できます。 **Get-cscallparkorbit**コマンドレットの詳細については、「 [get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

