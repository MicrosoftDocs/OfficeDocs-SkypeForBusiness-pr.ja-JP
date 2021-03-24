---
title: Skype for Business Server での監視の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: '概要: Skype for Business Server で監視を展開する方法について学習します。'
ms.openlocfilehash: 1db32530546884735333554535ccb976a0c48810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101993"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Skype for Business Server での監視の展開

**概要:** Skype for Business Server で監視を展開する方法について学習します。

これらのタスクを実行する前に、「Skype for Business Server で監視を [計画する」を確認してください](../../plan-your-deployment/monitoring.md)。

通常、トポロジ内に監視サービスを実装するには、次の 2 つの手順を実行します。

1. 新しい Skype for Business Server プールをセットアップすると同時に監視を有効にします。 (Skype for Business Server では、プール単位で監視が有効または無効になっています)。実際に監視データを収集せずにプールの監視を有効にできる点に注意してください。このドキュメントの「通話の詳細記録と品質の設定の構成」セクションで説明するプロセスです。

2. 新しいプールに監視ストア (監視データベース) を関連付けます。1 つの監視ストアを複数のプールに関連付けることができます。レジストラー プールに所属しているユーザーの数によっては、プールごとに別個の監視データベースをセットアップする必要がない場合もあります。代わりに、複数のプールで 1 つの監視ストアを使用できます。

新しいプールを作成すると同時に監視を有効にした方が簡単ですが、監視が無効になっている新しいプールを作成する方法もあります。 その場合は、後でトポロジ ビルダーを使用してサービスを有効にできます。トポロジ ビルダーは、プールの監視を有効または無効にしたり、プールを別の監視ストアに関連付ける方法を提供します。 監視サーバーの役割がなくなった場合でも、監視サービスによって収集されたデータを格納するために使用される 1 つ以上の監視ストア (バック エンド データベース) を作成する必要があります。 これらのバック エンド データベースは、Microsoft SQL Server 2008 R2、Microsoft SQL Server 2012、Microsoft SQL Server 2014、または 2019 Microsoft SQL Serverを使用して作成できます。

> [!NOTE]
> プールの監視が有効になっている場合は、トポロジを変更せずに監視データを収集するプロセスを無効にできます。Skype for Business Server では、通話詳細記録 (CDR) または Quality of Experience (QoE) データ収集を無効にする (後で再び有効にする) 方法が用意されています。 詳細については、このドキュメントの「通話の詳細記録と品質の設定の構成」セクションを参照してください。

Skype for Business Server での監視のもう 1 つの重要な強化点は、Skype for Business Server 監視レポートで IPv6 がサポートされるという事実です。IP アドレス フィールドを使用するレポートでは、使用されている SQL クエリに応じて IPv4 または IPv6 アドレスが表示されます。および、2) IPv6 アドレスが監視データベースに格納される場所としない場所。

> [!NOTE]
> SQL Server エージェント サービスのスタートアップの種類が自動で、監視データベースを保持している SQL インスタンスに対して SQL Server エージェント サービスが実行され、既定の監視 SQL Server メンテナンス ジョブが SQL Server エージェント サービスの管理下でスケジュールされたベースで実行できるようにします。

このドキュメントでは、Skype for Business Server の監視レポートと監視レポートをインストールおよび構成するプロセスについて説明します。 このドキュメントでは、次の操作のステップバイステップの手順を示します。

- トポロジで監視を有効化し、監視ストアとフロントエンド プールを関連付けます。

- レポート SQL Server Skype for Business Server 監視レポートをインストールします。 監視レポートは、監視データベースに格納されている情報をさまざまなビューで表示する事前構成済みのレポートです。

- 通話詳細記録 (CDR) と QoE (Quality of Experience) データ収集を構成します。 通話の詳細記録は、VoIP (Voice over IP) 通話などの Skype for Business Server 機能の使用状況を追跡する方法を提供します。インスタント メッセージング (IM)。ファイル転送。音声/ビデオ (音声ビデオ) 会議。およびアプリケーション共有セッション。 QoE 指標は、損失ネットワーク パケット数、バックグラウンド ノイズ、および "ジッター" の大きさ (パケット遅延の差) など、組織で行われる音声通話やビデオ通話の品質を追跡します。

- 監視データベースから CDR や QoE のレコードを手動で削除します。

## <a name="deployment-checklist-for-monitoring"></a>監視用の展開チェックリスト

監視は各フロントエンド サーバーに既にインストールされ、アクティブ化されていますが、Skype for Business Server の監視データを実際に収集する前に、いくつかの手順を実行する必要があります。 これらの手順を以下のチェックリストで簡単に説明します。

|**フェーズ**|**手順**|**ロールとグループ メンバシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |監視用のバックエンド データ ストアとして機能するコンピューターに、サポートされているバージョンの Microsoft SQL Server をインストールします。  <br/> |ローカルの Administrators グループのメンバーでもあるドメイン ユーザー。  <br/> |[サポートされるハードウェア](/previous-versions/office/lync-server-2013/lync-server-2013-supported-hardware) <br/> [サーバーのソフトウェアおよびインフラストラクチャ サポート](/previous-versions/office/lync-server-2013/lync-server-2013-server-software-and-infrastructure-support) <br/> |
|**適切な内部トポロジを作成して監視をサポートする** <br/> |Skype for Business Server トポロジ ビルダーを使用して、監視データベースをトポロジに追加し、更新されたトポロジを公開します。  <br/> |トポロジを定義する場合は、ローカル ユーザー グループのメンバーであるユーザー。  <br/> トポロジを公開する場合は、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるユーザー。  <br/> |[Skype for Business Server のフロントエンド プールに監視ストアを関連付ける](associate-a-monitoring-store.md) <br/> |
|**適切な監視設定を有効にする** <br/> |グローバル スコープまたはサイト スコープで通話詳細記録 (CDR) および QoE (QoE) 監視を有効にする。  <br/> |RTCUniversalServerAdmins グループのメンバーであるユーザー、または CsCdrConfiguration および CsQoEConfiguration コマンドレットにアクセスできる RBAC の役割が割り当てられたユーザー。  <br/> |[Skype for Business Server で通話の詳細記録と品質の設定を構成する](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>監視を有効にする

統合データ収集エージェントは各フロントエンド サーバーに自動的にインストールおよびアクティブ化されますが、Skype for Business Server のインストールが完了した瞬間に監視データの収集を自動的に開始するという意味ではありません。 代わりに、フロントエンド サーバー/フロントエンド プールを監視データベースに関連付け、グローバル スコープまたはサイト スコープで通話詳細記録 (CDR) または QoE (QoE) 監視を有効にする必要があります。

フロントエンド サーバーまたはフロントエンド プールを監視データベースに関連付ける手順については、「展開ガイド」のトピック [「Skype for Business Server](associate-a-monitoring-store.md) のフロントエンド プールに監視ストアを関連付ける」を参照してください。 これらの関連付けを行った後、新しい Skype for Business Server トポロジが公開された後も、監視データを収集できません。 これは、Skype for Business Server をインストールすると、既定では CDR と QoE の両方のデータ収集が無効になっているためです。

データ収集を開始するには、CDR 監視と QoE 監視のどちらかまたは両方を有効にする必要があります (CDR 監視と QoE 監視を両方とも有効にする必要はありません。 (CDR と QoE の両方の監視を有効にする必要はない点に注意してください。必要に応じて、もう一方の種類の監視を無効にした状態で有効にすることができます)。グローバル スコープで CDR 監視を有効にするには、Skype for Business Server 管理シェル内から次のコマンドを実行します。

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

または、Skype for Business Server コントロール パネル内から CDR 監視を有効にすることもできます。 Skype for Business Server コントロール パネル内で、次の手順を実行します。

1. [**監視**] をクリックします。

2. [**通話詳細記録**] タブで、[**グローバル**] 設定をダブルクリックします。

3. [**編集 通話詳細記録 (CDR) 設定**] ウィンドウで、[**CDR の監視を有効にする**] を選択し、[**コミット**] をクリックします。

グローバル スコープで QoE 監視を有効にするには、Skype for Business Server 管理シェル内から次のコマンドを実行します。

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

必要に応じて、Skype for Business Server コントロール パネル内から QoE 監視を有効にすることもできます。 コントロール パネル内で、次の手順を実行します。

1. [**監視**] をクリックします。

2. [**QoE データ**] タブで、[**グローバル**] 設定をダブルクリックします。

3. [**編集 Quality of Experience (QoE) 設定**] ウィンドウで、[**QoE データの監視を有効にする**] を選択し、[**コミット**] をクリックします。

上記の例では、グローバル スコープでの監視を有効にしています。つまり、組織全体で CDR と QoE の監視を有効にします。 または、サイト スコープで個別の CDR および QoE 構成設定を作成し、サイトごとに監視を選択的に有効または無効にすることもできます。 たとえば、Redmond サイトの CDR 監視を有効にし、ダブリン サイトの CDR 監視を無効にできます。 監視構成設定の管理の詳細については、「展開ガイド」のトピック「Skype for Business Server での通話の詳細記録と品質設定の構成 [」を参照してください](call-detail-recording-and-qoe.md)。

## <a name="see-also"></a>関連項目

[Skype for Business Server での監視の計画](../../plan-your-deployment/monitoring.md)