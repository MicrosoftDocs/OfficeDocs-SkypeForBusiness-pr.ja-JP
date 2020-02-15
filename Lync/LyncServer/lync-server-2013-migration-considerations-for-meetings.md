---
title: 'Lync Server 2013: 会議の移行に関する考慮事項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2657136b66675d08deb906879cb50962809f009c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Lync Server 2013 での会議の移行に関する考慮事項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-10_

このセクションでは、次のトピックについて説明しています。

  - Microsoft Lync Server 2013 での会議への変更

  - 電話会議のニーズに基づくユーザーの移行

  - 既存の会議と会議コンテンツの移行

  - Lync Server 2010 の移行中のユーザーの作業

  - Office Communications Server 2007 R2 の移行中のユーザーの作業状況

  - Microsoft Lync 2013 の以前のサーバーバージョンの会議との互換性

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Lync Server 2013 での会議の変更

**Lync Server 2013 の機能。**   Lync server 2013 は、アカウントが lync server 2013 に移動され、lync 2013 クライアントを使用してサインインした後で、ユーザーが利用できるようになる新しい会議機能を提供します。 新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」と「 [lync server 2013 のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能」に記載されています。

**会議の URL。**   Lync server 2010 と同様に、lync server 2013 で新しくスケジュールされた会議には、HTTPS://の URL プレフィックスがあり、既存の会議はユーザーアカウントと共に移行されます。 ただし、Lync Server 2013 は、Office Communications Server 2007 R2 会議通話 (conf://URL プレフィックス) または web 会議 (meet://URL プレフィックス) をサポートしていません。 詳細については、このトピックで後述する「Office Communications Server 2007 R2 からの会議の移行」を参照してください。

**クライアントのサポート。**   Lync server 2010 とは異なり、lync server 2013 は会議用の Office Communicator クライアントをサポートしていません。 次のクライアントを使用して、Lync 2013 用のオンライン会議アドインによってスケジュールされた会議に参加することはできません。

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

移行時に、Office Communicator 2007 R2 ユーザーは Lync Web App 2013 を使用して、クライアントがアップグレードされるまで Lync Server 2013 会議に参加する必要があります。 Office Communicator 2007 R2 ユーザーは、プレゼンスおよび IM 機能に対して Lync Server 2013 に対して既存のクライアントを引き続き使用することができますが、会議機能はサポートされていません。

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>電話会議のニーズに基づくユーザーの移行

**会議の開催者が頻繁に行われます。**    [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)と、 [lync 2013 server のクライアント向けの新](lync-server-2013-what-s-new-for-clients.md)機能について説明されている新しい lync server 2013 および lync 2013 の機能を利用できるように、プロセスの早い段階で移行を行うことを検討してください。

**Live Meeting ユーザー。**   Office Communications Server 2007 R2 から移行していて、Live Meeting 固有の web 会議機能 (特に、大規模な会議およびブレイクアウトルームのサポート) を必要とするユーザーがいる場合は、次のオプションを使用できます。

  - 組織で使用できる場合は、開催者に Live Meeting サービスを使用するように勧めます。

  - 以前のバージョンの Office Communications Server に所属している開催者には、引き続きサーバーベースの Live Meeting web 会議のスケジュールを設定できるようにしておきます。

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>既存の会議と会議コンテンツの移行

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Lync Server 2010 からの会議の移行

Lync Server 2010 から Lync Server 2013 にユーザーを移動すると、次の情報がユーザーのアカウントと共に移動します。

  - そのユーザーがスケジュール済みの会議。 これには、会議ディレクトリと会議データが含まれます。

  - ユーザーの暗証番号 (PIN)。 ユーザーの現在の PIN は、有効期限が切れるか、またはユーザーが新しい PIN を要求するまでの間、引き続き有効です。

ただし、次のユーザーアカウント情報は新しいサーバーに移動しません。

  - 会議コンテンツ (PowerPoint プレゼンテーション、ホワイトボードコンテンツ、投票データなど)

会議で共有されているコンテンツを移動するには、MoveMeetingContent コマンドレットのパラメーターを使用します。 このコマンドレットの使用の詳細については、「Lync Server 2013 コマンドレット」のドキュメントの「 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 」を参照してください。

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Office Communications Server 2007 R2 からの会議の移行

Office Communications Server 2007 R2 会議は、電話会議通話 (conf://URL プレフィックス) または web 会議 (meet://URL プレフィックス) のいずれかです。 Lync Server 2013 では、これらの以前の conf://および meet://会議がサポートされておらず、ユーザーアカウントと共に移行されることもありません。 移行後に、スケジュールされたオンライン会議のリンクを更新するようにユーザーに指示する必要があります。 これは、Lync 2013 クライアントをインストールした後で、会議 URL を更新して参加者に招待状を再送信する予定の会議出席依頼を開くことによって行うことができます。

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Lync Server 2010 の移行中のユーザーの作業

このセクションでは、Lync 2010 から移行する場合のユーザーの電話会議の概要について説明します。 Lync Server 2013 クライアントが以前のクライアントおよびサーバーバージョンと共存して操作する方法の詳細については、「 [lync 2013 でのクライアント相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」を参照してください。

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Lync Server 2010 会議の Lync 2013 クライアントへの参加

Lync Server 2010 からの移行中に、ユーザーが lync Server 2010 会議に Lync 2013 クライアントを参加させる場合、共存の期間が発生することがあります。 これらのユーザーは、以下の例外を除き、Lync 2013 クライアント機能にアクセスできます。

  - [**参加者**の管理] オプションでは、会議ウィンドウの [ユーザー] アイコンをポイントすることによってアクセスできます。 [**会議 IM**を利用しない] オプションは機能しません。

  - ギャラリービューは、ビデオ会議では機能しません。 ユーザーには、すべてのスピーカーではなく、アクティブなスピーカーのみが表示されます。 [レイアウトオプションの**選択**] の一覧で、**ギャラリービュー**を使用できません

  - 参加者リストは、既定では、ビデオ会議に表示されます。

  - [参加者] リストでユーザーを右クリックすると、[**ビデオスポットライトをロック**する] および [ギャラリー参加者管理**にピン留めする**] オプションが使用できなくなります。

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Office Communications Server 2007 R2 の移行中のユーザーの作業状況

このセクションでは、Lync 2013 をインストールする前と後に、Office Communications Server 2007 R2 から移行する場合のユーザーの電話会議の概要について説明します。 Lync Server 2013 クライアントが以前のクライアントおよびサーバーバージョンと共存して操作する方法の詳細については、「 [lync 2013 でのクライアント相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」を参照してください。

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>ユーザーアカウントが移行された後、Lync 2013 がインストールされる前

ユーザーが Lync Server 2013 サーバーに移行された後、新しいクライアントがインストールされる前に、Office Communicator 2007 R2 ユーザーが既存のクライアントを Lync Server 2013 に対して引き続き使用し、プレゼンスおよび IM 機能を使用できるようになります。いる.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>ユーザーアカウントが移行された後、Lync 2013 のインストール後

移行したユーザーが Lync 2013 をインストールすると、Lync 2013 用のオンラインミーティングアドインもインストールされます。 この場合、次の影響があります。

  - 今後予約する会議ではすべて、従来の会議形式の「meet:// Live Meeting アドレス」ではなく、新しい会議形式の「https:// アドレス」を使用します。

  - Lync 2013 の IT 管理展開では、管理者は Live Meeting サーバーとサービスベースの会議のスケジュール設定に使用される Microsoft Office Outlook 用会議アドインをアンインストールすることができます。 ただし、Live Meeting サービス会議を引き続きスケジュールする必要があるユーザーがいる場合があります。 この場合、両方のアドインを共存させることができます。

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>以前のクライアントを使用するフェデレーション組織との会議

会議が開催者によってロックされている場合、Microsoft Office Communicator 2007 を使用しているフェデレーション組織のユーザーは、組織内の Lync Server 2013 会議に参加できません。 フェデレーション参加者は、新しい https://会議 URL を使用して会議に参加するときに Lync Web App を使用できるように、Lync Server 2013 でこれらの会議をスケジュールし直す必要があります。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

