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
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Lync Server 2013 での会議の移行に関する考慮事項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-10_

このセクションでは、次のトピックについて説明します。

  - Microsoft Lync Server 2013 での会議の変更点

  - 会議のニーズに基づいてユーザーを移行する

  - 既存の会議と会議コンテンツの移行

  - Lync Server 2010 の移行中のユーザーエクスペリエンス

  - Office Communications Server 2007 R2 の移行中のユーザーエクスペリエンス

  - Microsoft Lync 2013 以前のバージョンのサーバーの会議との互換性

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Lync Server 2013 での会議の変更点

**Lync Server 2013 の機能。**   Lync server 2013 には、アカウントを lync server 2013 に移行した後でユーザーが利用できる新しい会議機能が用意されています。また、lync 2013 クライアントでサインインします。 新しい機能については、「 [Lync server 2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)」と「 [lync server 2013 でのクライアントの新](lync-server-2013-what-s-new-for-clients.md)機能」で説明しています。

**会議の URL。**   Lync server 2010 の場合と同様に、lync server 2013 で新しくスケジュールされた会議には、HTTPS://の URL プレフィックスと、既存の会議がユーザーアカウントと共に移行されます。 ただし、Lync Server 2013 は、Office Communications Server 2007 R2 会議通話 (conf://URL プレフィックス) または web 会議 (meet://URL プレフィックス) をサポートしていません。 詳細については、このトピックの後半の「Office Communications Server 2007 R2 から会議を移行する」を参照してください。

**クライアントのサポート。**   Lync server 2010 とは異なり、lync server 2013 では、会議用の Office Communicator クライアントはサポートされていません。 Lync 2013 用のオンライン会議アドインによってスケジュールされた会議に、次のクライアントを使用して会議に参加することはできません。

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

Office Communicator 2007 R2 ユーザーは、移行中に Lync Web App 2013 を使って Lync Server 2013 会議に参加してから、顧客がアップグレードされるようにする必要があります。 Office Communicator 2007 R2 ユーザーは、プレゼンスおよび IM 機能については、引き続き Lync Server 2013 に対して既存のクライアントを使用できますが、会議機能はサポートされていません。

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>会議のニーズに基づいてユーザーを移行する

**会議の開催者の頻度。**   Lync server [2013 の新しい会議機能](lync-server-2013-new-conferencing-features.md)で示されている新しい Lync server 2013 および lync 2013 の機能を利用できるように、また、 [lync server 2013 でのクライアントの新](lync-server-2013-what-s-new-for-clients.md)機能を活用できるように、プロセスの早い段階で会議の開催者を頻繁に移行することを検討してください。

**Live Meeting ユーザー。**   Office Communications Server 2007 R2 から移行する場合、Live Meeting 固有の web 会議機能 (特に大規模な会議や休憩室のサポート) が必要なユーザーがいる場合は、次のオプションがあります。

  - 組織で利用できる場合は、Live Meeting サービスを使用するように開催者に通知します。

  - サーバーベースの Live Meeting web 会議のスケジュールを維持できるように、以前のバージョンの Office Communications Server の開催者をホームにしておきます。

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>既存の会議と会議コンテンツの移行

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Lync Server 2010 から会議を移行する

Lync Server 2010 から Lync Server 2013 にユーザーを移動すると、次の情報がユーザーのアカウントと共に移動します。

  - ユーザーが既にスケジュールした会議。 これには、会議ディレクトリと会議データが含まれます。

  - ユーザーの暗証番号 (PIN)。 ユーザーの現在の PIN は、有効期限が切れるか、ユーザーが新しい PIN を要求するまで、引き続き動作します。

ただし、次のユーザーアカウント情報は新しいサーバーに移動されません。

  - 会議コンテンツ (PowerPoint プレゼンテーション、ホワイトボードコンテンツ、投票データなど)

会議で共有されているコンテンツを移動するには、移動-CsUser コマンドレットの MoveMeetingContent パラメーターを使用します。 このコマンドレットの使い方の詳細については、「Lync Server 2013 コマンドレットのドキュメントでの[移動-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 」を参照してください。

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Office Communications Server 2007 R2 から会議を移行する

Office Communications Server 2007 R2 会議は、会議通話 (conf://URL プレフィックス) または web 会議 (meet://URL プレフィックス) のいずれかです。 Lync Server 2013 では、これらの以前の conf://と meet://の会議はサポートされておらず、ユーザーアカウントと共に移行されることはありません。 移行後は、スケジュールしたオンライン会議のリンクを更新するようにユーザーに指示する必要があります。 この操作を行うには、スケジュールされた会議出席依頼を開き、会議の URL を更新し、参加者に招待状を再送信して、Lync 2013 クライアントをインストールします。

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Lync Server 2010 の移行中のユーザーエクスペリエンス

このセクションでは、Lync 2010 から移行する場合のユーザーの会議エクスペリエンスの概要について説明します。 Lync Server 2013 クライアントで、以前のクライアントとサーバーのバージョンを共存して操作する方法の詳細については、「 [lync 2013 でのクライアントの相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」を参照してください。

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Lync 2013 クライアントを使って Lync Server 2010 会議に参加する

Lync Server 2010 からの移行中に、ユーザーが lync 2013 クライアントを使って Lync Server 2010 会議に参加すると、共存期間が延長される場合があります。 これらのユーザーは、次の例外を除き、Lync 2013 クライアント機能にアクセスできます。

  - [会議] ウィンドウの [連絡先] アイコンをポイントしてアクセスできる**参加者**の管理オプションでは、[**会議 IM**を使わない] オプションは機能しません。

  - ギャラリービューは、ビデオ会議では機能しません。 ユーザーは、すべてのスピーカーではなく、アクティブなスピーカーのみを表示します。 [**レイアウトの選択**] オプションの一覧で、**ギャラリービュー**を使用できない

  - 参加者リストは、ビデオ会議の既定で表示されます。

  - [参加者] リストでユーザーを右クリックすると、[**ビデオスポットライトをロック**する] と [**ギャラリーに参加するための Pin** ] オプションは使用できません。

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Office Communications Server 2007 R2 の移行中のユーザーエクスペリエンス

このセクションでは、Lync 2013 がインストールされている前と後の両方で、Office Communications Server 2007 R2 から移行するユーザーの会議エクスペリエンスの概要について説明します。 Lync Server 2013 クライアントで、以前のクライアントとサーバーのバージョンを共存して操作する方法の詳細については、「 [lync 2013 でのクライアントの相互運用性](lync-server-2013-client-interoperability-in-lync-2013.md)」を参照してください。

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>ユーザーアカウントが移行された後、Lync 2013 がインストールされる前

ユーザーが Lync Server 2013 サーバーに移行された後、新しいクライアントがインストールされる前に、Office Communicator 2007 R2 ユーザーは、プレゼンスおよび IM 機能のために、Lync Server 2013 に対して既存のクライアントを引き続き使用できますが、会議機能は使用できません。サポートされ.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>ユーザーアカウントが移行された後、Lync 2013 をインストールした後

移行したユーザーが Lync 2013 をインストールすると、Lync 2013 用のオンライン会議アドインもインストールされます。 これには、次のような効果があります。

  - 以降のスケジュールされた会議では、新しい会議の形式が使用されます。これにより、従来の meet://Live Meeting のアドレスではなく、https://の住所が使用されます。

  - Lync 2013 の IT 管理展開では、管理者は Microsoft Office Outlook 用の会議アドインをアンインストールすることができます。これは、Live Meeting server とサービスベースの会議をスケジュールするために使用されます。 ただし、Live Meeting サービス会議を継続してスケジュールする必要があるユーザーがいる場合があります。 この場合は、両方のアドインを共存させることができます。

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>以前のクライアントを使用するフェデレーション組織との会議

Microsoft Office Communicator 2007 を使用しているフェデレーション組織のユーザーは、会議が開催者によってロックされている場合、組織内の Lync Server 2013 会議に参加することはできません。 会議の出席者が新しい https://会議の URL を使って会議に参加するときに、lync Web App を使うことができるように、Lync Server 2013 でこれらの会議のスケジュールを再設定する必要があります。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

