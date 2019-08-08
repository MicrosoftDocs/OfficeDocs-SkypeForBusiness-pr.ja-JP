---
title: Skype for Business Server で監視を展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: '概要: Skype for Business Server で監視を展開する方法について説明します。'
ms.openlocfilehash: 1eedcaaa30ecf464a5238e274e14de6770858290
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239953"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Skype for Business Server で監視を展開する

**概要:** Skype for Business Server で監視を展開する方法について説明します。

これらのタスクを実行する前に、「 [Skype For Business Server で監視計画を](../../plan-your-deployment/monitoring.md)確認する」を参照してください。

通常、次の 2 つの手順でトポロジ内に監視サービスを実装します。

1. 新しい Skype for Business Server プールをセットアップしたときに、同時に監視を有効にします。 (Skype for Business Server では、プール単位で監視が有効または無効になります)。このドキュメントの「通話の詳細の記録と品質の設定」セクションで説明したプロセスである、監視データを実際に収集することなく、プールの監視を有効にすることができます。

2. 監視ストア (監視データベース) と新しいプールを関連付けます。 1つの監視ストアを複数のプールに関連付けることができることに注意してください。 レジストラープールに所属しているユーザー数によっては、各プールに個別の監視データベースを設定する必要はありません。 代わりに、複数のプールで単一の監視ストアを使用できます。

新しいプールを作成するのと同時に監視を有効にする方が簡単ですが、監視を無効にして新しいプールを作成することもできます。 この操作を行う場合、後でトポロジビルダーを使用してサービスを有効にすることができます。 Topology Builder では、プールの監視を有効または無効にする方法、またはプールを異なる監視ストアに関連付ける方法が用意されています。 監視サーバーの役割がなくなった場合でも、1つ以上の監視ストアを作成する必要があります。バックエンドデータベースは、監視サービスによって収集されたデータを格納するために使用されます。 これらのバックエンドデータベースは、Microsoft SQL Server 2008 R2、Microsoft SQL Server 2012、または Microsoft SQL Server 2014 を使って作成できます。

> [!NOTE]
> プールに対して監視が有効になっている場合は、トポロジを変更せずに監視データの収集プロセスを無効にすることができます。 Skype for Business Server を使用すると、通話の詳細記録 (CDR) や音質を無効にすることができます。Experience (QoE) データの収集。 詳細については、このドキュメントの「通話の詳細の記録と音質の設定」を参照してください。

Skype for Business Server で監視するためのもう1つの重要な拡張機能として、Skype for Business Server Monitoring レポートが IPv6 をサポートしていることがあります。次のように、[IP Address] フィールドを使用するレポートには IPv4 アドレスまたは IPv6 アドレスが表示されます。 1) SQL クエリ使用されています。and, 2) IPv6 アドレスが監視データベースに格納されている場所。

> [!NOTE]
> SQL server エージェントサービスのスタートアップの種類が [自動] であり、監視データベースを保持している SQL インスタンスに対して SQL Server エージェントサービスが実行されていることを確認します。これにより、既定の監視対象の SQL Server メンテナンスジョブは、スケジュールされた基準で実行できるようになります。SQL Server エージェントサービスの制御下。

このドキュメントでは、Skype for Business Server の監視および監視レポートをインストールして構成するプロセスについて説明します。 このドキュメントでは、次の作業を行うための詳しい手順について説明します。

- トポロジで監視を有効にし、フロントエンドプールに監視ストアを関連付けます。

- SQL Server Reporting Services と Skype for Business Server Monitoring レポートをインストールします。 監視レポートは、監視データベースに格納されている情報のさまざまなビューを提供する事前構成済みレポートです。

- 通話の詳細記録 (CDR) と Quality of Experience (QoE) データの収集を構成します。 通話の詳細レコーディングは、ボイスオーバー IP (VoIP) 通話などの Skype for Business Server 機能の使用状況を追跡するための手段を提供します。インスタントメッセージング (IM);ファイルの転送音声/ビデオ (A/V) 会議アプリケーション共有セッション。 QoE メトリックは、組織内で行われた音声通話とビデオ通話の品質を管理します。たとえば、紛失したネットワークパケットの数、背景の雑音、"ジッター" の量 (パケット遅延の違い) などがあります。

- CDR または QoE レコードを監視データベースから手動で削除します。

## <a name="deployment-checklist-for-monitoring"></a>監視の展開チェックリスト

監視は既に各フロントエンドサーバーにインストールされていますが、Skype for Business Server の監視データを実際に収集する前に、いくつかの手順を実行する必要があります。 これらの手順については、次のチェックリストで説明します。

|**段階**|**手順**|**役割とグループのメンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|**必要なハードウェアとソフトウェアのインストール** <br/> |監視用のバックエンドデータストアとして機能する、サポートされているバージョンの Microsoft SQL Server をコンピューターにインストールします。  <br/> |ローカル管理者グループのメンバーでもあるドメインユーザー。  <br/> |[サポートされているハードウェア](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [サーバーソフトウェアとインフラストラクチャのサポート](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**監視をサポートする適切な内部トポロジを作成する** <br/> |Skype for Business Server トポロジビルダーを使用して、監視データベースをトポロジに追加した後、更新されたトポロジを公開しました。  <br/> |トポロジ (ローカルユーザーグループのメンバーであるユーザー) を定義するには、[] を選びます。  <br/> トポロジを公開するには、ドメイン管理者グループと RTCUniversalServerAdmins グループのメンバーであるユーザー。  <br/> |[Skype for Business Server で監視ストアをフロントエンドプールに関連付ける](associate-a-monitoring-store.md) <br/> |
|**適切な監視設定を有効にする** <br/> |グローバルまたはサイトのスコープで、通話の詳細記録 (CDR) と Quality of Experience (QoE) 監視を有効にします。  <br/> |RTCUniversalServerAdmins グループのメンバーであるか、CsCdrConfiguration と CsQoEConfiguration コマンドレットへのアクセスを提供する RBAC の役割が割り当てられているユーザー。  <br/> |[Skype for Business Server で通話の記録と音質の設定を構成する](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>監視を有効にする

統合データ収集エージェントは、各フロントエンドサーバーに自動的にインストールされ、アクティブ化されますが、Skype for Business Server のインストールが完了した時点で自動的に監視データの収集が開始されるとは限りません。 代わりに、フロントエンドサーバー/フロントエンドプールを監視データベースに関連付ける必要があります。また、グローバルスコープまたはサイトの範囲で、通話の詳細記録 (CDR) および品質のエクスペリエンス (QoE) の監視を有効にする必要があります。

フロントエンドサーバーまたはフロントエンドプールと監視データベースの関連付けの詳細な手順については、展開ガイドの「 [Skype For Business Server のフロントエンドプールに監視ストアを関連付ける](associate-a-monitoring-store.md)」を参照してください。 この関連付けが行われた後、新しい Skype for Business Server のトポロジが公開された後でも、監視データを収集することはできません。 これは、Skype for Business Server をインストールするときに、既定では CDR と QoE のデータ収集が無効になるためです。

データの収集を開始するには、CDR または QoE の監視を有効にする必要があります。 (CDR と QoE の両方の監視を有効にする必要はありません。必要に応じて、他の種類を無効のままにして、1つの種類の監視を有効にすることができます)。グローバルスコープで CDR 監視を有効にするには、Skype for Business Server 管理シェルで次のコマンドを実行します。

```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

または、Skype for Business Server のコントロールパネルで CDR の監視を有効にすることもできます。 Skype for Business Server コントロールパネルで、次の手順を実行します。

1. [**モニタリング**] をクリックします。

2. [**通話の詳細記録**] タブで、[**グローバル**設定] をダブルクリックします。

3. [**通話の詳細記録 (CDR) の設定**] ウィンドウで、[ **CDRs の監視を有効にする**] を選び、[**コミット**] をクリックします。

グローバルスコープで QoE の監視を有効にするには、Skype for Business Server 管理シェルで次のコマンドを実行します。

```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

必要に応じて、Skype for Business Server コントロールパネル内から QoE の監視を有効にすることもできます。 コントロールパネルで、次の手順を実行します。

1. [**モニタリング**] をクリックします。

2. [**エクスペリエンスの品質データ**] タブで、[**グローバル**設定] をダブルクリックします。

3. [ **Quality Of Experience (qoe) の設定**] ウィンドウで、[ **qoe データの監視を有効にする**] を選び、[**コミット**] をクリックします。

既に説明したように、上の例ではグローバルスコープで監視を有効にします。つまり、ユーザーは組織全体で CDR と QoE の監視を行うことができます。 または、サイトのスコープで個別の CDR と QoE の構成設定を作成して、各サイトの監視を個別に有効または無効にすることもできます。 たとえば、Redmond サイトで CDR の監視を有効にしていても、ダブリンサイトの CDR 監視を無効にすることができます。 監視構成の設定を管理する方法の詳細については、展開ガイドのトピック「 [Skype For Business Server での通話の詳細の記録と音質の設定を構成](call-detail-recording-and-qoe.md)する」を参照してください。

## <a name="see-also"></a>関連項目

[Skype for Business Server で監視を計画する](../../plan-your-deployment/monitoring.md)
