---
title: 監視をシステムに展開Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: '概要: 監視をサーバーに展開する方法についてSkype for Business Server。'
ms.openlocfilehash: cbb5fe0974e1b02ce5be472ba91d01221fb7df82
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764845"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>監視をシステムに展開Skype for Business Server

**概要:** 監視を展開する方法については、Skype for Business Server。

これらのタスクを実行する前に、「[監視を計画する」を参照Skype for Business Server。](../../plan-your-deployment/monitoring.md)

通常、トポロジ内に監視サービスを実装するには、次の 2 つの手順を実行します。

1. 新しいプールをセットアップすると同時に監視をSkype for Business Serverします。 (このSkype for Business Server、プール単位で監視が有効または無効になります)。実際に監視データを収集せずにプールの監視を有効にできる点に注意してください。このドキュメントの「通話の詳細記録と品質の設定」セクションで説明するプロセス設定説明します。

2. 新しいプールに監視ストア (監視データベース) を関連付けます。1 つの監視ストアを複数のプールに関連付けることができます。レジストラー プールに所属しているユーザーの数によっては、プールごとに別個の監視データベースをセットアップする必要がない場合もあります。代わりに、複数のプールで 1 つの監視ストアを使用できます。

新しいプールを作成すると同時に監視を有効にした方が簡単ですが、監視が無効になっている新しいプールを作成する方法もあります。 その場合は、後でトポロジ ビルダーを使用してサービスを有効にできます。トポロジ ビルダーは、プールの監視を有効または無効にしたり、プールを別の監視ストアに関連付ける方法を提供します。 監視サーバーの役割がなくなった場合でも、監視サービスによって収集されたデータを格納するために使用される 1 つ以上の監視ストア (バック エンド データベース) を作成する必要があります。 これらのバック エンド データベースは、Microsoft SQL Server R2、Microsoft SQL Server 2012、Microsoft SQL Server 2014、または Microsoft SQL Server 2019 を使用して作成できます。

> [!NOTE]
> プールで監視が有効になっている場合は、トポロジを変更せずに監視データを収集するプロセスを無効にできます。Skype for Business Server では、通話詳細記録 (CDR) または Quality of Experience (QoE) データ収集を無効にする (後で再び有効にする) 方法が提供されます。 詳細については、このドキュメントの「通話の詳細記録と品質の設定」設定を参照してください。

Skype for Business Server での監視のもう 1 つの重要な強化点は、Skype for Business Server 監視レポートで IPv6 がサポートされるという事実です。IP アドレス フィールドを使用するレポートには、使用されている SQL クエリに応じて IPv4 または IPv6 アドレスが表示されます。および、2) IPv6 アドレスが監視データベースに格納される場所としない場所。

> [!NOTE]
> SQL Server エージェント サービスの管理下で既定の監視 SQL Server メンテナンス ジョブをスケジュールに基づいて実行できるよう、監視データベースを保持している SQL インスタンスで SQL Server エージェント サービスが自動的に実行され、SQL Server エージェント サービスが実行されている必要があります。

このドキュメントでは、監視レポートと監視レポートをインストールおよび構成するプロセスをSkype for Business Server。 このドキュメントでは、次の操作のステップバイステップの手順を示します。

- トポロジで監視を有効化し、監視ストアとフロントエンド プールを関連付けます。

- 監視SQL Server Reporting Servicesと監視レポートSkype for Business Serverインストールします。 監視レポートは、監視データベースに格納されている情報をさまざまなビューで表示する事前構成済みのレポートです。

- 通話詳細記録 (CDR) と QoE (Quality of Experience) データ収集を構成します。 通話の詳細記録は、Voice over IP (VoIP) 電話Skype for Business Server機能の使用状況を追跡する方法を提供します。インスタント メッセージング (IM)。ファイル転送。音声/ビデオ (音声ビデオ) 会議。およびアプリケーション共有セッション。 QoE 指標は、損失ネットワーク パケット数、バックグラウンド ノイズ、および "ジッター" の大きさ (パケット遅延の差) など、組織で行われる音声通話やビデオ通話の品質を追跡します。

- 監視データベースから CDR や QoE のレコードを手動で削除します。

## <a name="deployment-checklist-for-monitoring"></a>監視用の展開チェックリスト

監視は各フロントエンド サーバーに既にインストールされ、アクティブ化されていますが、実際に監視データを収集する前に、いくつかの手順を実行する必要Skype for Business Server。 これらの手順を以下のチェックリストで簡単に説明します。

|**フェーズ**|**手順**|**ロールとグループ メンバシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |監視用のバックエンド データ ストアとして機能するコンピューターに、サポートされているバージョンの Microsoft SQL Server をインストールします。  <br/> |ローカルの Administrators グループのメンバーでもあるドメイン ユーザー。  <br/> |[サポートされるハードウェア](/previous-versions/office/lync-server-2013/lync-server-2013-supported-hardware) <br/> [サーバーのソフトウェアおよびインフラストラクチャ サポート](/previous-versions/office/lync-server-2013/lync-server-2013-server-software-and-infrastructure-support) <br/> |
|**適切な内部トポロジを作成して監視をサポートする** <br/> |トポロジ Skype for Business Serverを使用して、監視データベースをトポロジに追加し、更新されたトポロジを公開します。  <br/> |トポロジを定義する場合は、ローカル ユーザー グループのメンバーであるユーザー。  <br/> トポロジを公開する場合は、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるユーザー。  <br/> |[監視ストアをサーバー内のフロントエンド プールに関連付Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**適切な監視設定を有効にする** <br/> |グローバル スコープまたはサイト スコープで通話詳細記録 (CDR) および QoE (QoE) 監視を有効にする。  <br/> |RTCUniversalServerAdmins グループのメンバーであるユーザー、または CsCdrConfiguration および CsQoEConfiguration コマンドレットにアクセスできる RBAC の役割が割り当てられたユーザー。  <br/> |[[通話の詳細の記録] と [エクスペリエンスの品質] の設定を構成Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>監視を有効にする

統合データ収集エージェントは、各フロント エンド サーバーに自動的にインストールおよびアクティブ化されますが、つまり、Skype for Business Server のインストールが完了した瞬間に監視データの収集が自動的に開始されるという意味ではありません。 代わりに、フロントエンド サーバー/フロントエンド プールを監視データベースに関連付け、グローバル スコープまたはサイト スコープで通話詳細記録 (CDR) または QoE (QoE) 監視を有効にする必要があります。

フロントエンド サーバーまたはフロントエンド プールを監視データベースに関連付ける手順については、「展開ガイド」の[「Skype for Business Server](associate-a-monitoring-store.md)のフロントエンド プールに監視ストアを関連付ける」を参照してください。 これらの関連付けを行った後、新しいトポロジSkype for Business Serverが公開された後も、監視データを収集できない状態が続く場合があります。 これは、既定では、CDR と QoE の両方のデータ収集が、インストール時に無効Skype for Business Server。

データ収集を開始するには、CDR 監視と QoE 監視のどちらかまたは両方を有効にする必要があります (CDR 監視と QoE 監視を両方とも有効にする必要はありません。 (CDR と QoE の両方の監視を有効にする必要はない点に注意してください。必要に応じて、もう一方の種類の監視を無効にした状態で有効にすることができます)。グローバル スコープで CDR 監視を有効にするには、次のコマンドを管理シェル内Skype for Business Server実行します。

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

または、コントロール パネル内から CDR 監視を有効Skype for Business Serverすることもできます。 [コントロール パネル] Skype for Business Serverで、次の手順を実行します。

1. [**監視**] をクリックします。

2. [**通話詳細記録**] タブで、[**グローバル**] 設定をダブルクリックします。

3. [**編集 通話詳細記録 (CDR) 設定**] ウィンドウで、[**CDR の監視を有効にする**] を選択し、[**コミット**] をクリックします。

グローバル スコープで QoE 監視を有効にするには、次のコマンドを管理シェル内Skype for Business Server実行します。

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

必要に応じて、コントロール パネル内から QoE Skype for Business Serverすることもできます。 コントロール パネル内で、次の手順を実行します。

1. [**監視**] をクリックします。

2. [**QoE データ**] タブで、[**グローバル**] 設定をダブルクリックします。

3. [**編集 Quality of Experience (QoE) 設定**] ウィンドウで、[**QoE データの監視を有効にする**] を選択し、[**コミット**] をクリックします。

上記の例では、グローバル スコープでの監視を有効にしています。つまり、組織全体で CDR と QoE の監視を有効にします。 または、サイト スコープで個別の CDR および QoE 構成設定を作成し、サイトごとに監視を選択的に有効または無効にすることもできます。 たとえば、Redmond サイトの CDR 監視を有効にし、ダブリン サイトの CDR 監視を無効にできます。 監視構成設定の管理の詳細については、「展開ガイド」のトピック「通話の詳細記録と品質の設定を構成する」を参照[Skype for Business Server。](call-detail-recording-and-qoe.md)

## <a name="see-also"></a>関連項目

[監視の計画を立Skype for Business Server](../../plan-your-deployment/monitoring.md)