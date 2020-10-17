---
title: 'Lync Server 2013: 大規模会議のサポートの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e7d7796a879398d5f73ebfc67cc6cc6a68b5b1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497584"
---
# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Lync Server 2013 での大規模会議のサポートの設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-12_

最大 1000 ユーザーの大規模な会議をサポートするには、適切なトポロジの作成、会議のハードウェアおよびソフトウェア前提条件、および環境の適切な構成が必要です。

<div>

## <a name="topology-requirements"></a>トポロジ要件

1つの大規模な会議には、少なくとも1台のフロントエンドサーバーと1台のバックエンドサーバーが必要です。 ただし、高可用性を実現するには、バックエンドサーバーがミラー化された2台のフロントエンドサーバープールを使用することをお勧めします。

大規模な会議を主催するユーザーには、このプールに所属するユーザー アカウントが必要です。 ただし、このプールに他のユーザー アカウントをホストすることはお勧めしません。 代わりに、大規模な会議にのみ使用します。 ベスト プラクティスは、大規模な会議のホストにのみ使用する特殊なユーザー アカウントをこのプールに作成することです。 大規模な会議の設定はパフォーマンスのために最適化されているため、通常のユーザーとして使用すると、PSTN エンドポイントが関与しているときに、P2P セッションを会議に昇格できないなどの問題が発生する可能性があります。

2 つのフロントエンド サーバーでプールを管理するには、特別な考慮が必要です。 詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。

さらに、大規模な会議に使用されているプールに対して、必要に応じて障害回復のバックアップとフェールオーバーを提供する場合は、別のデータセンターに専用プールを設定するのと同じように組み合わせることができます。 詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

![大規模な会議プールの構成](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "大規模な会議プールの構成")

トポロジについて次のような追加の注意事項があります。

  - アーカイブファイルを保存するために、アーカイブサーバーが展開されて有効になっている場合は、会議コンテンツを格納するためにファイル共有が必要です。 ファイル共有は、プール専用にすることも、プールが展開されているサイトの別のプールで使用されているのと同じファイル共有にすることもできます。 ファイル共有の構成の詳細については、「 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)」を参照してください。

  - 大規模な会議で PowerPoint プレゼンテーション機能を有効にするには、Office Web Apps サーバーが必要です。 Office Web Apps サーバーは、大規模な会議プール専用にすることも、専用プールを展開するサイトの他のプールで使用する Office Web Apps サーバーと同じにすることもできます。

  - フロントエンドサーバーの負荷分散では、HTTP トラフィック (会議コンテンツのダウンロードなど) にハードウェア負荷分散が必要になります。 SIP トラフィックには DNS 負荷分散をお勧めします。 詳細については、「 [Lync Server 2013 の負荷分散の要件」を](lync-server-2013-load-balancing-requirements.md)参照してください。

  - 専用の大規模会議プールに対して監視サーバーを使用する場合は、Lync Server 展開のすべてのフロントエンドサーバープール間で共有されている監視サーバーとデータベースを使用することをお勧めします。

</div>

<div>

## <a name="hardware-and-software-requirements"></a>ハードウェアとソフトウェアの要件

専用の大規模会議プールのサーバーのハードウェア要件は、他の Lync Server 2013 サーバーの場合と同じです。 ハードウェア要件の詳細については、「[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

専用の大規模会議プール内のサーバーは、すべての Lync Server 2013 ソフトウェア要件を満たす必要があります。 ソフトウェア要件の詳細については、次のドキュメントを参照してください。

  - [Lync Server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 でのデータベースソフトウェアのサポート](lync-server-2013-database-software-support.md)

  - [Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)

さらに、Lync Server 2013 と Lync Server 2013 クライアントの両方に最新の更新プログラムがインストールされている必要があります。

</div>

<div>

## <a name="configuration-requirements"></a>構成要件

大規模な会議専用に新しい電話会議ポリシーを作成し、専用の大規模会議プールに所属するユーザーに電話会議ポリシーを割り当てることをお勧めします。電話会議ポリシーは次の設定を使用して構成します。

  - **MaxMeetingSize** オプションを **1000** に設定します (既定は **250** です)。

  - **AllowLargeMeetings** オプションを **True** に設定します。

  - **EnableAppDesktopSharing** オプションを **None** に設定します。

  - **AllowUserToScheduleMeetingsWithAppSharing** オプションを **False** に設定します。

  - **AllowSharedNotes** オプションを **False** に設定します。

  - **AllowAnnotations** オプションを **False** に設定します。

  - **DisablePowerPointAnnotations** オプションを **True** に設定します。

  - **AllowMultiview** オプションを **False** に設定します。

  - **EnableMultiviewJoin** オプションを **False** に設定します。

<div>


> [!NOTE]  
> Lync Server 2013 で1000ユーザーの大規模な会議をサポートするには、会議ポリシーの <STRONG>AllowLargeMeetings</STRONG> 設定で、会議スケジューラを true に設定する必要があります。 この設定を true に設定すると、ユーザーが会議に参加するときに、Lync の使用状況が特大の会議に最適化されます。 特に、大規模な会議では、Lync は完全な会議参加者リストの初期または更新を表示しません。これは、クライアントと Lync Server 2013 の両方のパフォーマンスのボトルネックになります。 代わりに Lync では、ユーザーに関する情報と、会議の発表者の一覧のみが表示されます。 Lync は、大規模会議で利用可能な参加者の総数を適切に表示します。



</div>

大規模な会議で不要な会議機能を無効にするには、**[最大会議サイズ]** 設定を除き、ここで指定する他のすべての電話会議ポリシー設定が必要です。

さらに、専用の大規模会議プールを構成して、そのプールに所属し、会議スケジュールの管理を担当する各 Lync Server 2013 ユーザーが適切なアクセス許可を持つようにする必要があります。 これを行うには、次の操作を行います。

  - **[発表者として指定]** オプションを **[なし]** に設定します。通常は、大規模な会議のすべての参加者のうち 1 名または数名のユーザーが発表者であるため、参加者は大規模な会議で発表者として自動的には許可されないようにする必要があります。代わりに、発表者は会議のスケジュール時に明示的に指定するか、大規模な会議中に明示的に昇格する必要があります。

  - [ **割り当てられた電話会議の種類 (既定** )] チェックボックスがオフになっていることを確認します。 この設定では、Lync 2013 用のオンライン会議アドインが常に開催者が割り当てた会議を使用して会議をスケジュールするかどうかを制御します。つまり、予約された会議の参加 URL とオーディオ情報は同じになります。 小規模グループのグループ作業のシナリオでは、すべてのユーザーが自分の会議を割り当てられているため、そのような会議の種類が適切に機能します。定数参加 URL とオーディオ情報を使用すると、会議の参加が容易になります。 ただし、大規模な会議のシナリオでは、大規模会議サポートスタッフが1つのユーザー資格情報セットを使用して大規模な会議をスケジュールし、会議の出席者に対して参加 Url とオーディオ情報を提供します。 この場合、各会議への参加に異なる URL を使用する方が適しています。

  - 必要でない限り **[匿名ユーザーを既定で承認する]** チェック ボックスがオンになっていないことを確認します。 この設定は、割り当てられた会議を使用しない場合に、Lync 2013 用オンラインミーティングアドインによってスケジュールされる既定の会議アクセスの種類に影響します。 この設定の適切なオプションは、組織のニーズによって決まります。 組織のほとんどの大規模な会議が社内会議の場合は、このオプションを選択しないでください。 ほとんどの大規模な会議に外部ユーザーが参加できるようにする必要がある場合は、このオプションを選択します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

