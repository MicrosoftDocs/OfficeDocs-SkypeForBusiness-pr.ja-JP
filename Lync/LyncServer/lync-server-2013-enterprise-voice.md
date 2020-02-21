---
title: Lync Server 2013 エンタープライズ Voip
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924e15aae9590b6148864084aa68924e4c080f7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 のエンタープライズ Voip

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-04-08_

エンタープライズ Voip では、Lync Server は、従来の構内交換 (PBX) システムを拡張または置換するためのスタンドアロンボイスオーバーインターネットプロトコル (VoIP) を提供します。 エンタープライズ VoIP ユーザーは、組織の VoIP ネットワークまたは PBX で仕事仲間を呼び出し、組織外の従来の電話番号を呼び出すことができます。 エンタープライズ Voip ソリューションには、answer、forward、transfer、hold、divert、release and パーク、Enhanced 9-1-1 (E9-1-1) 通話などの一般的な通話機能が含まれています (E9-1-1) (米国でのみ使用可能)。エンタープライズ Voip では、広範な現在および古い IP デバイスと USB デバイスもサポートしています。

<div>

## <a name="placing-and-receiving-calls"></a>通話の発信と着信

Lync を使用すると、ユーザーは自分のキーボードで名前または電話番号を入力するか、画面に表示されているダイヤルパッドを使用して通話を行うことができます。 ユーザーは、連絡先一覧から直接通話を開始することもできます。 また、Microsoft パートナーによって提供されるスタンドアロンの IP 電話デバイスである、Lync Phone Edition デバイスを展開することもできます。

ユーザーは、Lync Server に登録されている複数の電話デバイスを使用して、それらを簡単に切り替えることができます。

ユーザーは、自分のすべてのデバイスで同時に通話の着信を知らされます。IP 電話機ではカスタマイズが可能な着信音、PC ではインスタント メッセージに類似の通知が使用されます。

また、ユーザーは卓上電話、PC、携帯電話に接続する電話番号を 1 つに設定できるため、どこにいても連絡を受けられます。

</div>

<div>

## <a name="basic-call-features"></a>基本的な通話機能

通話中、ユーザーは別の着信通話に応答したり発信通話を開始したりできます。その間、既存のアクティブな通話は自動的に保留されます。 通話は、あるユーザーから別のユーザーに直接転送するか、最初のユーザーが 2 番目のユーザーと個人的に話した後に転送できます。 ユーザーは通話を別のデバイスに転送することもできます。たとえば、オフィスの外に出るときに、アクティブな通話を携帯電話に転送できます。

</div>

<div>

## <a name="richer-communications"></a>より高度な通信

Lync を使用して他のユーザーと話すときに、ユーザーはテキスト、ビデオ、またはデスクトップ共有を簡単に通話に追加できます。 "応答不可" 機能は、Lync のプレゼンス設定と統合されています。

Exchange ユニファイドメッセージング (UM)、Lync および Lync Server は、Microsoft Exchange Server 2013 および Microsoft Outlook 2013 と統合されています。 ユーザーは、Lync ウィンドウと電子メールの両方に新しいボイスメールがあるかどうかを確認できます。 さらに電子メールでは、クリックして、電子メール メッセージ内のボイス メールの音声を再生したり、ボイス メール メッセージのトランスクリプトを表示したりできます。

</div>

<div>

## <a name="advanced-calling-features"></a>高度な通話機能

エンタープライズ Voip には、Lync 通話の委任、チーム呼び出し、グループ通話ピックアップ、応答グループなど、いくつかの高度な通話機能も含まれています。

Lync 通話の委任を使用すると、[**ツール** \> **オプション]** \>の [着信**転送設定**] にアクセスして、ユーザーが1人または複数のアシスタントに通話処理を委任できるようになります。 委任されたスタッフは、ユーザーの代わりに、通話の選別、通話の発信、会議の開始などの複数の通話タスクを実行できます。

<div>


> [!IMPORTANT]  
> 同じような名前の別の機能である Lync 予定表の委任を検索している可能性があります。 エンタープライズ Voip 機能を必要とせず、ユーザーが Outlook からオンラインで Lync 会議をスケジュールできるようにします。 この情報を検索するには、「 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> 」を参照して、Exchange 代理人の同期を有効にすることをお勧めします。



</div>

チーム呼び出しを使用すると、ユーザーは、チームの全員が通話に応答できるように、参加者の電話を同時に着信することができます。

グループ通話ピックアップ (Lync Server 2013 の累積的な更新プログラムの新機能: 2 月 2013) を使用すると、ユーザーは自分の電話から自分の仕事仲間への着信呼び出しに応答できます。 グループ通話ピックアップは主に、目的の受信者の電話でのみ着信呼び出しが発信されるということですが、他のユーザーは通話ピックアップグループ番号をダイヤルすることによって応答することができます。

応答グループは、キューイング、および呼び出し先エージェントへの通話の複雑なルーティングに対応するように設定できます。 一般的な使用法には、IT ヘルプデスク、人事部ホットライン、その他の社内コンタクト センターなどがあります。

</div>

<div>

## <a name="enterprise-voice-administration"></a>エンタープライズ VoIP の管理

Lync Server は、標準と発行されたインターフェイスを使用して、既存のインフラストラクチャと相互運用します。 IP PBX システムおよび PSTN ネットワークへの相互接続用にゲートウェイと SIP オプション (SIP トランキングなど) の両方をサポートするため、混乱を最小限に抑えながら、時間をかけてユーザーをエンタープライズ VoIP に移行できます。 Lync Server は、従来の VoIP ソリューションとの相互運用性を実現するために、g.722、g.723.1 などの従来のコーデックをサポートしています。

通話受付管理 (CAC) を使用すると、管理者は、制限されたネットワークリンクで実行される Lync Server の音声およびビデオのトラフィックの量に関する制限を設定したり、新しい呼び出しが制限を超えた場合に実行するアクションを指定したりできます。 このアクションには、代替パスによるルーティングや、通話の拒否などがあります。

Lync Server は、サードパーティ製の存続可能ブランチアプライアンスと連携して、中央サイトで WAN 障害が発生した場合に、ローカルの通話サービスを提供し、支店で PSTN に接続します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

