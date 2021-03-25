---
title: Android に Microsoft Teams の会議室を展開する
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
description: この記事では、Android に Microsoft Teams Rooms を展開する方法について説明します。
ms.openlocfilehash: 3da0192ee3676f5ff7294ba719c778ea7b1cc7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120799"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Android に Microsoft Teams の会議室を展開する

Android での Microsoft Teams Rooms の展開は、次のフェーズに分けすることができます。

- **サイトの準備** 展開場所 (会議室) が展開要件を満たしていることを確認します。
- **サービスの準備** リソース アカウントを作成し、デバイスに割り当てる [(「Microsoft 365](resource-account-ui.md)管理センターを使用してリソース アカウントを作成する」を参照してください)。 専用ルーム ライセンスの使用をお勧めしますが、適切にライセンスを取得したエンド ユーザー アカウントは Android 版 Teams Rooms にサインインすることもできます。
- **構成と展開** Teams 会議室をセットアップし、必要な周辺機器を接続します (詳細については、製造元のドキュメントを参照してください)。

Teams 会議室を管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「Microsoft Teams 管理者ロールを使用して Teams を管理 [する」を参照してください](../using-admin-roles.md)。

## <a name="site-readiness"></a>サイトの準備

注文されたデバイスが組織に配信されている間は、ネットワーク、施設、およびオーディオ ビジュアル チームと共同で、展開要件が満たされ、各サイトと部屋が電源、ネットワーク、表示の面で準備が整っていることを確認します。

コラボレーション バー サイトに関する推奨事項は次のとおりです。

- 最大 5 名の会議室
- 専用リソース アカウント
- タッチ対応ディスプレイ
- イーサネット ケーブル
- Microsoft Teams メディアのネットワークで有効になっているサービスの品質 (QoS)

物理的なインストールに関する考慮事項については、製造元のマニュアルを参照し、お持ちである場合は、スクリーンをインストールしてマウントし、ケーブルを実行する前に、オーディオ ビジュアル チームのエクスペリエンスを活用してください。

> [!TIP]
> 帯域幅計画およびリアルタイム トラフィックに対するネットワークの適性の評価のために [、Teams](../prepare-network.md) 用のネットワークを準備する方法を確認してください。
>
> Teams デバイスとインターネットの間にプロキシ サーバーを配置はお勧めしません。 プロキシ サーバーと Teams の詳細については、Teams の [プロキシ サーバーを確認してください](../proxy-servers-for-skype-for-business-online.md)。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトが Microsoft Teams のコラボレーション バーのサイト準備要件を満たしていることを確認します。</li><li>各サイトに十分な帯域幅があることを確認します。</li></ul>|
| ![次の手順を表すアイコン](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>コラボレーション バーの展開と構成の計画を開始します。</li></ul>|

## <a name="service-readiness"></a>サービスの準備

Teams 会議室を展開する前に、それらのユーザーが Microsoft 365 リソース アカウント、エンド ユーザー アカウント、または両方の組み合わを使用するか決定する必要があります。 Microsoft 365 リソース アカウントは、会議室、プロジェクターなどの特定のリソース専用のメールボックスアカウントと Teams アカウントです。 これらのリソース アカウントは、作成時に定義したルールを使用して会議出席招待に自動的に応答できます。 Teams Rooms が個人のプライベート使用のために特定の個人専用である場合を限り、Microsoft 365 リソース アカウントをセットアップすることをお勧めします。

### <a name="using-a-resource-account"></a>リソース アカウントを使用する

Microsoft 365 リソース アカウントをセットアップする場合は、その会議室のライセンスを購入する必要があります。 会議室ライセンスには、組織内のユーザーが Outlook または Teams を介して会議室を予約できるリソース メールボックスが含まれています。 また、このライセンスでは、会議の参加者間でビデオ会議、電話会議、画面共有も有効にできます。

外部の電話番号との間で通話を受信または発信する必要がある場合は、通話プランまたは Microsoft 365 Business Voice アドオン ライセンス [が必要な場合があります](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)。 組織で直接ルーティングを有効にしている場合は、会議室 SKU だけが必要です。

リソース アカウントを作成するときに、アカウントで会議出席依頼を自動的に承諾するか辞退するか、定期的な会議を許可するか、ユーザーがリソースを予約できる事前の数を指定するかなど、選択できます。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Microsoft 365 リソース アカウントの詳細については [、「Microsoft 365](resource-account-ui.md)管理センターを使用してリソース アカウントを作成する」を参照してください。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>外部電話の送受信を行うかどうかを決定し、リソース アカウントのライセンス要件を特定します。</li></ul>|
| ![次の手順を表すアイコン](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>リソース アカウントを準備します。</li></ul>|

## <a name="configuration-and-deployment"></a>構成と展開

構成と展開を計画する主要分野は次のとおりです。

- リソース アカウントのプロビジョニング
- デバイスの展開
- Teams Rooms アプリケーションと周辺機器の構成
- テスト
- 資産管理

### <a name="account-provisioning"></a>アカウントのプロビジョニング

Microsoft 365 リソース アカウントを使用してユーザーがコラボレーション バーを予約する場合は [、「Microsoft 365](resource-account-ui.md) 管理センターを使用してリソース アカウントを作成する」の手順に従って、必要なコラボレーション バーごとに Microsoft 365 リソース アカウントを作成します。 また、この場所では、リソース アカウントに会議室ライセンスを追加する必要があります。また、組織が直接ルーティングを使用していない場合に、外部の電話番号との間で通話を発信または受信する場合は、通話プランまたは Business Voice ライセンスを追加する必要があります。

個人使用のために Teams 会議室を個々のユーザーに割り当てる場合は、追加のアカウントを設定する必要はありません。 ユーザーは、個人用アカウントを使用してコラボレーション バーにサインインできます。

> [!TIP]
> Microsoft 365 リソース アカウントの表示名をわかりやすいわかりやすい名前にします。 Teams 会議室を検索して会議に追加するときに表示される名前は次のとおりです。 サイト ルーム名 (最大会議室容量) などの規則を使用できます。たとえば、ロンドンの 4 人用会議室である Curie には - 、LON-CURIE(4)という表示名を付けます。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>専用リソース アカウントの名前付け規則を決定します。</li><li>個々のアカウントを作成するか、一括プロビジョニング スクリプトを使用するか決定します。</li></ul>|
| ![次の手順を表すアイコン](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開の計画を開始します。</li></ul>|

### <a name="device-deployment"></a>デバイスの展開

次に、デバイスと割り当てられた周辺機器を会議室に配信する計画を作成し、インストールと構成に進む必要があります。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトごとの展開を管理するユーザーを決定します。</li><li> Teams Rooms をサイトにインストールし、構成とテストを実行するリソースを特定します。</li></ul>|
| ![次の手順を表すアイコン](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスのテストを開始します。</li></ul>|

### <a name="testing"></a>テスト

Teams 会議室を展開した後は、それらをテストする必要があります。 Teams の会議室にサインインし、期待される機能が機能しているのを確認します。 Microsoft Teams 管理センターの [デバイス] タブの [コラボレーションバー] セクションに表示されるのを確認することを強くお勧めします。 また、品質とパフォーマンスをチェックするために、テスト通話や会議を多数行う必要があります。

Microsoft Teams の一般的なロールアウトの一環として、通話品質ダッシュボード (CQD) のファイルの作成、品質の傾向の監視、品質レビュー プロセスへの参加を行う必要があります。 詳細については、「エクスペリエンスの品質 [レビュー ガイド」を参照してください](../quality-of-experience-review-guide.md)。

### <a name="asset-management"></a>資産管理

展開の一環として、ルーム名、サインイン済みリソース アカウント、および割り当てられた周辺機器を使用して資産登録を更新する必要があります。

## <a name="related-topics"></a>関連項目

[Microsoft Teams 管理センターを使用して Microsoft Teams 会議室のアカウントを構成する](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->