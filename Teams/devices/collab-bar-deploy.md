---
title: Android Microsoft Teams ミーティングをデプロイする
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: この記事では、Android にアプリをMicrosoft Teams ミーティング説明します。
ms.openlocfilehash: 3da0192ee3676f5ff7294ba719c778ea7b1cc7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120799"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Android Microsoft Teams ミーティングをデプロイする

Android でのMicrosoft Teams ミーティングの展開は、次のフェーズに分け可能です。

- **サイトの準備** デプロイの場所 (会議室) がデプロイ要件を満たしていることを確認します。
- **サービスの準備** リソース アカウントを作成し、デバイスに割り当てる (「管理センターでリソース アカウントを [作成するMicrosoft 365参照してください](resource-account-ui.md))。 専用ルーム ライセンスを使用することをお勧めしますが、適切にライセンスされたエンド ユーザー アカウントは、Android 上の Teams ミーティングサインインすることもできます。
- **構成とデプロイ** 必要なTeams ミーティングデバイスをセットアップして接続します (詳細については、製造元のドキュメントを参照してください)。

アカウントをTeams ミーティングするには、グローバル管理者、サービス管理者、Teamsデバイス管理者Teams必要があります。管理者ロールの詳細については、「管理者ロールを使用してMicrosoft Teams[を管理する」を](../using-admin-roles.md)Teams。

## <a name="site-readiness"></a>サイトの準備

注文されたデバイスが組織に配信されている間は、ネットワーク、施設、およびオーディオ ビジュアル チームと共同で、展開要件が満たされ、各サイトと部屋が電源、ネットワーク、表示の面で準備ができていることを確認します。

コラボレーション バー サイトに関する推奨事項は次のとおりです。

- 最大 5 名の会議室
- 専用リソース アカウント
- タッチ対応ディスプレイ
- イーサネット ケーブル接続
- ネットワーク上で有効になっているサービス品質 (QoS) が、Microsoft Teamsされます。

物理的なインストールに関する考慮事項については、製造元のドキュメントを参照してください。また、ある場合は、画面をインストールしてマウントし、ケーブル配線を実行する前に、オーディオ ビジュアル チームのエクスペリエンスを活用してください。

> [!TIP]
> 「帯域幅の計画とリアルタイム トラフィックに対するネットワーク[の適合性の評価Teams](../prepare-network.md)ネットワークを準備する」を参照してください。
>
> 複数のデバイスとインターネットの間にプロキシ Teams配置はお勧めしません。 プロキシ サーバーとプロキシ サーバーの詳細については、Teams のプロキシ サーバーに関[するTeams。](../proxy-servers-for-skype-for-business-online.md)

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトがコラボレーション バーのサイト準備要件を満たしていることを確認Microsoft Teams。</li><li>各サイトに十分な帯域幅があることを確認します。</li></ul>|
| ![次の手順を示すアイコン](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>コラボレーション バーのデプロイと構成の計画を開始します。</li></ul>|

## <a name="service-readiness"></a>サービスの準備

アプリケーションをデプロイTeams ミーティング、リソース アカウント、エンド ユーザー アカウント、または両方をMicrosoft 365を使用するか判断する必要があります。 Microsoft 365アカウントは、会議室Teamsプロジェクターなど、特定のリソース専用のメールボックス アカウントとリソース アカウントです。 これらのリソース アカウントは、作成時に定義したルールを使用して、会議出席招待に自動的に応答できます。 特定のTeams ミーティング専用のリソース アカウントがない限り、リソース アカウントMicrosoft 365を設定することをお勧めします。

### <a name="using-a-resource-account"></a>リソース アカウントの使用

リソース アカウントを設定するMicrosoft 365、リソース アカウントのライセンスを購入ミーティング ルーム必要があります。 このミーティング ルームライセンスには、組織内のユーザーが会議や会議を通じて会議室を予約できるリソース メールボックスOutlook含Teams。 このライセンスでは、会議参加者間でのビデオ会議と電話会議と画面共有も可能です。

外部の電話番号との間で通話を受信または発信する必要がある場合は、通話プランまたはアドオン ライセンス Microsoft 365 Business Voice[必要な場合があります](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)。 組織で直接ルーティングを有効にしている場合は、その SKU ミーティング ルーム必要です。

リソース アカウントを作成するときに、アカウントで会議出席依頼を自動的に承諾または拒否するか、定期的な会議を許可するか、ユーザーがリソースを予約できる時間を事前に指定するかなどについて選択できます。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

リソース アカウントの詳細についてはMicrosoft 365管理センターを使用してリソース アカウント[を作成するMicrosoft 365参照してください](resource-account-ui.md)。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>外部の電話の送受信を行うかどうかを決定し、リソース アカウントのライセンス要件を特定します。</li></ul>|
| ![次の手順を示すアイコン](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>リソース アカウントを準備します。</li></ul>|

## <a name="configuration-and-deployment"></a>構成と展開

構成と展開を計画する主要分野は次のとおりです。

- リソース アカウントのプロビジョニング
- デバイスの展開
- Teams ミーティングおよび周辺機器の構成
- テスト
- 資産管理

### <a name="account-provisioning"></a>アカウントのプロビジョニング

Microsoft 365 リソース アカウントを使用してコラボレーション バーを予約する場合は[、「Microsoft 365](resource-account-ui.md)管理センターを使用してリソース アカウントを作成する」の手順に従って、必要なコラボレーション バーごとに Microsoft 365 リソース アカウントを作成します。 また、リソース アカウントに ミーティング ルーム ライセンスを追加する必要があります。また、組織が直接ルーティングを使用していない場合は、外部の電話番号との間で通話を発信または受信する場合は、通話プランまたは Business Voice ライセンスを追加する必要があります。

個々のユーザーにTeams ミーティングを割り当てる場合は、追加のアカウントを設定する必要はありません。 ユーザーは、個人用アカウントを使用してコラボレーション バーにサインインできます。

> [!TIP]
> リソース アカウントの表示名をわかりやすいMicrosoft 365わかりやすい名前にします。 これらは、ユーザーが会議を検索して会議に追加するときに表示Teams ミーティング名前です。 *サイト* ルーム名 ( 最大会議室の容量) などの規則を使用できます。そのため、たとえば、ロンドンの 4 人の会議室である Curie は、表示名 - LON-CURIE(4)を持つ場合があります。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>専用リソース アカウントの名前付け規則を決定します。</li><li>個々のアカウントを作成するか、一括プロビジョニング スクリプトを使用するか決定します。</li></ul>|
| ![次の手順を示すアイコン](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開の計画を開始します。</li></ul>|

### <a name="device-deployment"></a>デバイスの展開

次に、デバイスと割り当てられた周辺機器を会議室に配信する計画を作成し、インストールと構成に進む必要があります。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトごとの展開を管理するユーザーを決定します。</li><li> サイトにインストールするリソースTeams ミーティング、構成とテストを実行します。</li></ul>|
| ![次の手順を示すアイコン](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスのテストを開始します。</li></ul>|

### <a name="testing"></a>テスト

アプリケーションをデプロイした後Teams ミーティングテストする必要があります。 サインインして、Teams ミーティング機能が動作している必要があります。 管理センターの [デバイス] タブの [コラボレーションバー] セクションに表示Microsoft Teams強くお勧めします。 また、品質とパフォーマンスを確認するために、テスト通話や会議を多数行う必要があります。

Microsoft Teams の一般的なロールアウトの一環として、通話品質ダッシュボード (CQD) のファイルの作成、品質の傾向の監視、およびエクスペリエンスの品質レビュー プロセスへの参加を構成することをお勧めします。 詳細については、「エクスペリエンスの品質 [レビュー ガイド」を参照してください](../quality-of-experience-review-guide.md)。

### <a name="asset-management"></a>資産管理

デプロイの一環として、ルーム名、サインイン済みリソース アカウント、および割り当てられた周辺機器を使用してアセット レジスタを更新する必要があります。

## <a name="related-topics"></a>関連トピック

[管理センターを使用Microsoft Teams ミーティングアカウントMicrosoft Teams構成する](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->