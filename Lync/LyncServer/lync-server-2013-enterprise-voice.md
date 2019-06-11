---
title: 'Lync Server 2013: エンタープライズ VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c8131c2f52dfc7ab061d8dec46ee34b62f89e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 のエンタープライズ VoIP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-04-08_

エンタープライズ Voip では、Lync Server は、従来の構内交換 (PBX) システムを強化または交換するための、スタンドアロンのボイスオーバーインターネットプロトコル (VoIP) サービスを提供します。 エンタープライズボイスユーザーは、組織の VoIP ネットワークまたは PBX で同僚に通話を発信したり、組織外の従来の電話番号に通話したりすることができます。 エンタープライズ Voip ソリューションには、回答、forward、transfer、hold、転送すれば、release、パークなどの一般的な通話機能、強化された 9-1-1 (E9) 通話 (E9 は米国でのみ利用可能) が含まれています。エンタープライズボイスは、さまざまな現在および古い IP デバイスと USB デバイスもサポートしています。

<div>

## <a name="placing-and-receiving-calls"></a>通話の発信と受信

Lync を使用すると、ユーザーはキーボードで名前または電話番号を入力したり、画面に表示されているダイヤルパッドを使って通話を発信したりすることができます。 ユーザーは、連絡先リストから直接通話を開始することもできます。 また、Microsoft パートナーによって提供されるスタンドアロンの IP 電話デバイスである Lync Phone Edition デバイスを展開することもできます。

ユーザーは、複数の電話デバイスを Lync Server に登録して、簡単に切り替えることができます。

ユーザーには、すべてのデバイスで同時に着信があった場合に、IP 電話デバイスのカスタマイズ可能な着信音、および PC でのインスタントメッセージに似た通知が表示されます。

また、ユーザーは、自分の机の電話、PC、携帯電話に接続する1つの電話番号を設定して、どこにいても連絡できるようにすることができます。

</div>

<div>

## <a name="basic-call-features"></a>基本的な通話機能

通話中に、ユーザーは追加の着信通話に応答したり、発信通話を開始したりできます。また、既存のアクティブな通話が自動的に保留になります。 通話は、直接、または最初のユーザーが2番目のユーザーとプライベートに話すと、別のユーザーに転送できます。 また、ユーザーは通話を別のデバイスに転送することもできます。たとえば、office のドアを見ながら、アクティブな通話を携帯電話に転送することができます。

</div>

<div>

## <a name="richer-communications"></a>より充実したコミュニケーション

Lync を使用して別のユーザーと話すときに、ユーザーはテキスト、ビデオ、またはデスクトップの共有を簡単に通話に追加できます。 [応答不可] 機能は、Lync のプレゼンス設定と統合されています。

Exchange ユニファイドメッセージング (UM)、Lync、Lync Server を Microsoft Exchange Server 2013 および Microsoft Outlook 2013 と統合します。 ユーザーは、Lync ウィンドウとメールの両方で、新しいボイスメールがあるかどうかを確認できます。 メールでは、クリックしてメールメッセージでボイスメールの音声を再生したり、ボイスメールメッセージのトランスクリプトを表示したりすることができます。

</div>

<div>

## <a name="advanced-calling-features"></a>高度な通話機能

エンタープライズボイスには、Lync 通話の委任、チーム呼び出し、グループ通話のピックアップ、応答グループなど、高度な通話機能もいくつか含まれています。

Lync 通話の委任を使用すると、ユーザーは [**ツール** \> **]** \>の [着信の**転送設定**] に移動して、1人または複数のアシスタントに通話処理を委任することができます。 代理人は、ユーザーに代わって複数の通話タスクを実行できます。これには、通話のスクリーニング、通話の発信、会議の開始などがあります。

<div>


> [!IMPORTANT]  
> 同じような名前の付いた Lync 予定表の代理人を探している可能性があります。 エンタープライズ Voip 機能は不要であり、ユーザーは Outlook からのオンライン Lync 会議のスケジュールを設定することができます。 この情報を探していた場合は、Exchange 委任の同期を有効にする方法については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> 」を確認することをお勧めします。



</div>

チーム呼び出しを使用すると、ユーザーは、チームメンバーが着信に応答できるように、参加者の電話を同時に呼び出すことができます。

グループ通話のピックアップ (Lync Server 2013 の累積更新プログラムの新機能: 2013 年2月) では、ユーザーは自分の電話から同僚への着信に応答できます。 グループ通話の集配は、主に、目的の受信者の電話でのみ着信が発生するという点で、チーム呼び出しとは異なります。ただし、他のユーザーは、通話ピックアップグループ番号にダイヤルすることによって応答することを選択できます。

応答グループは、指定したエージェントへの通話をキューに入れ、インテリジェントにルーティングするように設定できます。 一般的な用途としては、ヘルプデスク、人的リソースホットライン、その他の社内連絡先センターがあります。

</div>

<div>

## <a name="enterprise-voice-administration"></a>エンタープライズボイス管理

Lync Server は、標準および公開されたインターフェイスを使って、既存のインフラストラクチャと相互運用します。 この機能は、IP PBX システムと PSTN ネットワークとの間のゲートウェイと SIP の両方のオプション (SIP トランキングなど) をサポートしているので、中断を最小限に抑えながら、ユーザーをエンタープライズ Voip に移行することができます。 Lync Server は、722、723.1 などの従来のコーデックをサポートしており、従来の VoIP ソリューションとの相互運用性を実現します。

通話受付制御 (CAC) では、管理者は、制限付きのネットワークリンクで伝送される Lync Server の音声とビデオのトラフィックの量に制限を設定し、新しい通話が制限を超えた場合に実行する操作を指定できます。 アクションには、代替パスによるルーティング、または通話の拒否を含めることができます。

Lync Server は、サードパーティの Survivable ブランチアプライアンスと連携して、中央サイトで WAN 障害が発生した場合に、支店の PSTN へのローカル通話サービスと接続を提供します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

