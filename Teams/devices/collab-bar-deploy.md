---
title: Android でMicrosoft Teams Roomsをデプロイする
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Android でのMicrosoft Teams Roomsのデプロイの詳細については、この記事を参照してください。
ms.openlocfilehash: 7b37f03bdecf0bb6b1d3f3545d096836aa81b805
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514518"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Android でMicrosoft Teams Roomsをデプロイする

Android でのMicrosoft Teams Roomsのデプロイは、次のフェーズに分けることができます。

- **サイトの準備状況** デプロイの場所 (ルーム) がデプロイ要件を満たしていることを確認します。
- **サービスの準備** リソース アカウントを作成し、デバイスに割り当てます ([「Microsoft 365 管理センターを使用したリソース アカウントの作成」を参照)。](resource-account-ui.md) 専用ルーム ライセンスを使用することをお勧めしますが、適切なライセンスを持つエンド ユーザー アカウントは Android でTeams Roomsにサインインすることもできます。
- **構成とデプロイ** Teams Roomsを設定し、必要な周辺機器を接続します (詳細については、製造元のドキュメントを参照してください)。

Teams Roomsを管理するには、グローバル管理者、Teams サービス管理者、またはデバイス管理者Teams必要があります。管理者ロールの詳細については、「[Microsoft Teams管理者ロールを使用してTeamsを管理する」を](../using-admin-roles.md)参照してください。

## <a name="site-readiness"></a>サイトの準備

順序付けられたデバイスが組織に配信されている間は、ネットワーク、施設、およびオーディオ ビジュアル チームと連携して、展開要件が満たされ、各サイトと部屋の電源、ネットワーク、表示の面で準備が整っていることを確認します。

コラボレーション バー サイトの推奨事項は次のとおりです。

- 最大 5 人の会議室
- 専用リソース アカウント
- タッチ対応ディスプレイ
- イーサネット ケーブル接続
- Microsoft Teams メディアのネットワークで有効になっているサービスの品質 (QoS)

物理的なインストールに関する考慮事項については、製造元のドキュメントを参照してください。また、ある場合は、画面をインストールしてマウントし、ケーブル接続を実行する前に、オーディオ ビジュアル チームのエクスペリエンスを活用してください。

> [!TIP]
> 帯域幅の計画とリアルタイム トラフィックに対するネットワークの適合性の評価[のために、ネットワークをTeamsに準備](../prepare-network.md)する方法を確認してください。
>
> Teams デバイスとインターネットの間にプロキシ サーバーを配置することはお勧めしません。 プロキシ サーバーとTeamsの詳細については、[Teams用のプロキシ サーバーを](../proxy-servers-for-skype-for-business-online.md)確認してください。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトが、Microsoft Teamsのコラボレーション バーのサイト準備要件を満たしていることを確認します。</li><li>各サイトに十分な帯域幅があることを確認します。</li></ul>|
| ![次の手順を示すアイコン。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>コラボレーション バーの展開と構成の計画を開始します。</li></ul>|

## <a name="service-readiness"></a>サービスの準備

Teams Roomsをデプロイする前に、Microsoft 365リソース アカウント、エンド ユーザー アカウント、またはその両方を使用するかどうかを決定する必要があります。 Microsoft 365リソース アカウントは、会議室、プロジェクターなどの特定のリソース専用のメールボックスとTeams アカウントです。 これらのリソース アカウントは、作成時に定義したルールを使用して会議出席依頼に自動的に応答できます。 Teams Roomsがプライベート使用のために特定の個人専用である場合を除き、Microsoft 365リソース アカウントを設定することをお勧めします。

### <a name="using-a-resource-account"></a>リソース アカウントの使用

Microsoft 365 リソース アカウントを設定する場合は、ミーティング ルーム ライセンスを購入する必要があります。 ミーティング ルーム ライセンスには、組織内のユーザーがOutlookまたはTeamsを介して会議室を予約できるようにするリソース メールボックスが含まれています。 また、このライセンスにより、会議参加者間でのビデオ会議と電話会議と画面共有も可能になります。

外部の電話番号との間で通話を受信または発信する必要がある場合は、通話プランまたはアドオン [ライセンス](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)Microsoft 365 Business Voice必要な場合があります。 組織でダイレクト ルーティングを有効にしている場合は、ミーティング ルーム SKU のみが必要です。

リソース アカウントを作成するときに、アカウントが会議出席依頼を自動的に受け入れるか拒否するかを選択したり、定期的な会議を許可したり、リソースを事前に予約できる距離を指定したりすることができます。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Microsoft 365リソース アカウントの詳細については、「[Microsoft 365 管理センターを使用したリソース アカウントの作成」を](resource-account-ui.md)参照してください。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>外部の電話を発信するか受信するかを決定し、リソース アカウントのライセンス要件を特定します。</li></ul>|
| ![次の手順を示すアイコン。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>リソース アカウントを準備します。</li></ul>|

## <a name="configuration-and-deployment"></a>構成と展開

構成と展開を計画する主要分野は次のとおりです。

- リソース アカウントのプロビジョニング
- デバイスの展開
- Teams Rooms アプリケーションと周辺機器の構成
- テスト
- 資産管理

### <a name="account-provisioning"></a>アカウントのプロビジョニング

Microsoft 365 リソース アカウントを使用してユーザーがコラボレーション バーを予約できるようにする場合は、「Microsoft 365 管理センター[を使用してリソース アカウントを作成](resource-account-ui.md)する」の手順に従って、必要なコラボレーション バーごとにMicrosoft 365リソース アカウントを作成します。 また、リソース アカウントにミーティング ルーム ライセンスを追加する必要があります。また、組織がダイレクト ルーティングを使用していない場合は、外部電話番号との間で通話を発信または受信する場合は通話プランまたは Business Voice ライセンスを追加する必要があります。

プライベート使用のためにTeams Roomsを個々のユーザーに割り当てる場合は、追加のアカウントを設定する必要はありません。 ユーザーは、個人用アカウントを使用してコラボレーション バーにサインインできます。

> [!TIP]
> Microsoft 365 リソース アカウントの表示名をわかりやすく説明します。 これらは、会議にTeams Roomsを検索して追加するときにユーザーに表示される名前です。 *SiteRoom*- *Name*(*Max Room Capacity*) のような規則を使用できます。そのため、たとえば、ロンドンの 4 人用会議室である Curie に表示名 LON-CURIE(4) を付けることができます。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>専用リソース アカウントの名前付け規則を決定します。</li><li>個々のアカウントを作成するか、一括プロビジョニング スクリプトを使用するかを決定します。</li></ul>|
| ![次の手順を示すアイコン。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開の計画を開始します。</li></ul>|

### <a name="device-deployment"></a>デバイスの展開

次に、デバイスとその割り当てられた周辺機器を会議室に配信する計画を作成し、インストールと構成を続行する必要があります。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトごとの展開を管理するユーザーを決定します。</li><li> サイトにTeams Roomsをインストールし、構成とテストを行うリソースを特定します。</li></ul>|
| ![次の手順を示すアイコン。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスのテストを開始します。</li></ul>|

### <a name="testing"></a>テスト

Teams Roomsをデプロイしたら、それらをテストする必要があります。 Teams Roomsにサインインし、期待される機能が動作していることを確認します。 管理センターの [**Teams デバイス**] タブの [**コラボレーション バー**] セクションに表示されていることを確認Microsoft Teams、お勧めします。 また、品質とパフォーマンスを確認するために、多数のテスト呼び出しと会議を行うことも重要です。

一般的なMicrosoft Teamsロールアウトの一環として、通話品質ダッシュボード (CQD) のビルド ファイルを構成し、品質の傾向を監視し、Quality of Experience Review プロセスに参加することをお勧めします。 詳細については、「 [Quality of Experience Review Guide](../quality-of-experience-review-guide.md)」を参照してください。

### <a name="asset-management"></a>資産管理

デプロイの一環として、ルーム名、サインインしているリソース アカウント、割り当てられた周辺機器で資産登録を更新する必要があります。

## <a name="related-topics"></a>関連項目

[会議室と共有Teamsデバイスのリソース アカウントを作成する](../rooms/with-office-365.md)