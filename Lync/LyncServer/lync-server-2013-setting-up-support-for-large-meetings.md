---
title: 'Lync Server 2013: 大規模な会議のサポートを設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03196c705253320e31e2483cc89b2aca386ff1af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Lync Server 2013 での大規模な会議のサポートの設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-12_

1000ユーザーの大きな会議をサポートするには、適切なトポロジを作成し、ハードウェアとソフトウェアの前提条件を満たし、環境を適切に構成する必要があります。

<div>

## <a name="topology-requirements"></a>トポロジ要件

1 つの大規模な会議には、少なくとも 1 つのフロントエンド サーバーと 1 つのバックエンド サーバーが必要です。 ただし、高可用性を実現するには、ミラーバックエンドサーバーを備えた2台のフロントエンドサーバープールをお勧めします。

大規模な会議をホストしているユーザーは、このプールに所属するユーザーアカウントを持っている必要があります。 ただし、このプールに他のユーザー アカウントをホストすることはお勧めしません。 代わりに、大規模な会議にのみ使用します。 ベスト プラクティスは、大規模な会議のホストにのみ使用する特殊なユーザー アカウントをこのプールに作成することです。 大規模な会議の設定はパフォーマンス用に最適化されているので、それを通常のユーザーとして使用すると、PSTN エンドポイントが関係する場合に P2P セッションを会議に昇格できないなどの問題が発生することがあります。

2 つのフロントエンド サーバーでプールを管理するには、特別な配慮が必要です。 詳細については、「 [Lync Server 2013 のフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント」を](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)参照してください。

また、オプションで大規模な会議に使用するプールの障害復旧バックアップおよびフェールオーバーを提供する場合は、これを異なるデータ センター内の同様に設定した専用プールと組み合わせることができます。 詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

![大規模な会議プールの構成](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "大規模な会議プールの構成")

トポロジについて次のような追加の注意事項があります。

  - 会議コンテンツを格納するため、また、アーカイブ サーバーが展開されて有効になっている場合はアーカイブ ファイルを格納するために、ファイル共有が必要です。 ファイル共有は、プール専用にすることも、プールが展開されているサイトの別のプールで使用されているのと同じファイル共有にすることもできます。 ファイル共有の構成の詳細については、「 [Lync Server 2013 用にファイルストレージを構成する](lync-server-2013-configure-dfs-file-storage.md)」を参照してください。

  - 大規模な会議で PowerPoint プレゼンテーション機能を有効にするには、Office Web Apps サーバーが必要です。 Office Web Apps サーバーは、大規模な会議プール専用にすることも、専用のプールが展開されているサイトの他のプールで使用する Office Web Apps サーバーと同じにすることもできます。

  - フロントエンド サーバーの負荷分散には、HTTP トラフィック (会議コンテンツのダウンロードなど) 用のハードウェア負荷分散が必要です。 SIP トラフィックには DNS 負荷分散をお勧めします。 詳細については、「 [Lync Server 2013 の負荷分散の要件」を](lync-server-2013-load-balancing-requirements.md)参照してください。

  - 専用の大規模な会議プール用に監視サーバーを使用する場合は、Lync Server の展開で監視サーバーとそのデータベースを使用することをお勧めします。

</div>

<div>

## <a name="hardware-and-software-requirements"></a>ハードウェアとソフトウェアの要件

専用の大規模な会議プールのサーバーのハードウェア要件は、他の Lync Server 2013 サーバーの場合と同じです。 ハードウェア要件の詳細については、「[Lync server 2013 用のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

専用の大規模な会議プール内のサーバーは、すべての Lync Server 2013 ソフトウェア要件を満たしている必要があります。 ソフトウェア要件の詳細については、次のドキュメントを参照してください。

  - [Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 でのデータベース ソフトウェアのサポート](lync-server-2013-database-software-support.md)

  - [Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)

さらに、Lync Server 2013 と Lync Server 2013 クライアントの両方に最新の更新プログラムがインストールされている必要があります。

</div>

<div>

## <a name="configuration-requirements"></a>構成要件

大規模な会議専用の新しい会議ポリシーを作成して、専用の大規模な会議プールをホームにしているユーザーに会議ポリシーを割り当てることをお勧めします。 電話会議ポリシーは次の設定を使用して構成します。

  - [ **Max会議サイズ**] オプションを [ **1000**] に設定します。 (既定値は**250**です)。

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
> Lync Server 2013 の1000ユーザーの大規模な会議のサポートでは、会議スケジューラの会議ポリシーで<STRONG>AllowLargeMeetings</STRONG>設定が true に設定されている必要があります。 この設定が true に設定されていると、ユーザーが会議に参加したときに、Lync エクスペリエンスが追加の大規模な会議に最適化されます。 特に、大規模な会議では、Lync には、クライアントと Lync Server 2013 両方のパフォーマンスのボトルネックである、完全な会議参加者リストの初回または更新プログラムは表示されません。 代わりに、ユーザーに関する情報と会議の発表者の一覧のみが表示されます。 Lync には、大規模な会議で利用可能な参加者の合計数が適切に表示されます。



</div>

大規模な会議で不要な会議機能を無効にするには、[**最大会議サイズ**] 設定を除き、ここで指定する他のすべての電話会議ポリシー設定が必要です。

さらに、専用の大規模な会議プールを構成する必要があります。これにより、プールをホームにしている各 Lync Server 2013 ユーザーに、適切なアクセス許可が付与されます。 これを行うには、次の操作を行います。

  - [**発表者として指定**] オプションを [**なし**] に設定します。通常は、大規模な会議のすべての参加者のうち 1 名または数名のユーザーが発表者であるため、参加者は大規模な会議で発表者として自動的には許可されないようにする必要があります。代わりに、発表者は会議のスケジュール時に明示的に指定するか、大規模な会議中に明示的に昇格する必要があります。

  - [**会議の種類が既定で割り当てら**れている] チェックボックスがオフになっていることを確認します。 この設定は、Lync 2013 用のオンライン会議アドインで常に開催者が割り当てた会議を使用して会議をスケジュールするかどうかを制御します。つまり、スケジュールされた会議の参加 URL と音声情報は同じであることを意味します。 小規模グループのコラボレーションシナリオでは、参加者全員が会議を担当しているため、そのような会議の種類を割り当てることができます。また、URL とオーディオ情報を定期的に参加させることにより、会議への参加が簡単になります。 ただし、大会議のシナリオでは、大規模な会議のサポートスタッフが、1セットのユーザー資格情報を使用して大規模な会議をスケジュールし、会議の出席依頼に、参加 Url とオーディオ情報を提供します。 この場合、各会議への参加に異なる URL を使用する方が適切に動作します。

  - 必要でない限り [**匿名ユーザーを既定で承認する**] チェック ボックスがオンになっていないことを確認します。 この設定は、割り当てられた会議を使用していないときに、Lync 2013 用のオンライン会議アドインによってスケジュールされた既定の会議アクセスの種類に影響します。 この設定の適切なオプションは、組織のニーズによって決まります。 組織のほとんどの大規模な会議が社内会議の場合は、このオプションを選択しないでください。 ほとんどの大規模な会議に外部ユーザーが参加できるようにする必要がある場合は、このオプションを選択します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

