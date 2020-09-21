---
title: Microsoft Teams のコラボレーションバーの展開
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
description: この記事では、Microsoft Teams のコラボレーションバーの展開について説明します。
ms.openlocfilehash: 41eb3335eef78f1da2c64b1df65443ba93d40159
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962908"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Microsoft Teams のコラボレーションバーの展開

Microsoft Teams のコラボレーションバーの展開は、次のフェーズに分けることができます。

- **サイトの準備** 展開場所 (会議室) が展開要件を満たしていることを確認します。
- **サービスの準備** リソースアカウントを作成してデバイスに割り当てる ([「Microsoft 365 管理センターを使用してリソースアカウントを作成する」を参照](resource-account-ui.md)してください)。 専用の room ライセンスを使用することをお勧めしますが、適切なライセンスのエンドユーザーアカウントでコラボレーションバーにサインインすることもできます。
- **構成と展開** 会議室でコラボレーションバーを設定し、必要な周辺機器を接続します (共同作業バーについては、製造元のマニュアルを参照してください)。

コラボレーションバーを管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「 [Microsoft teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」を参照してください。

## <a name="site-readiness"></a>サイトの準備

注文されたデバイスは組織に配信されますが、ネットワーク、設備、およびオーディオビジュアルチームと協力して、展開要件が満たされていることを確認し、各サイトと部屋の電力、ネットワーキング、ディスプレイの準備ができていることを確認します。

コラボレーションバーサイトについての推奨事項は次のとおりです。

- サイズが最大4人のルーム
- 専用リソースアカウント
- タッチ対応ディスプレイ
- イーサネット接続
- Microsoft Teams メディアのネットワークで有効になっている QoS (Quality of Service)

物理的なインストールの考慮事項については、製造元のマニュアルを参照してください。いずれかの場合は、画面をインストールして起動し、ケーブルを接続する前に、オーディオビジュアルチームのエクスペリエンスを活用してください。

> [!TIP]
> 必ず、「 [ネットワーク](../prepare-network.md) の帯域幅の計画」を確認して、リアルタイムトラフィックに対するネットワークの適合性を評価してください。
>
> Teams デバイスとインターネットの間にプロキシサーバーを配置することはお勧めしません。 プロキシサーバーと Teams の詳細については、「 [teams のプロキシサーバー](../proxy-servers-for-skype-for-business-online.md)」を参照してください。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトが Microsoft Teams のコラボレーションバーのサイト準備要件を満たしていることを確認します。</li><li>各サイトに十分な帯域幅があることを確認します。</li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>コラボレーションバーの展開と構成の計画を開始します。</li></ul>|

## <a name="service-readiness"></a>サービスの準備

コラボレーションバーを展開する前に、Microsoft 365 リソースアカウント、エンドユーザーアカウント、または両方を組み合わせて使用するかどうかを決定する必要があります。 Microsoft 365 リソースアカウントは、会議室、プロジェクターなどの特定のリソース専用のメールボックスおよび Teams アカウントです。 これらのリソースアカウントは、作成時に定義したルールを使って、会議出席依頼に自動的に応答できます。 プライベート使用のためにコラボレーションバーが特定の個人専用である場合を除き、Microsoft 365 リソースアカウントを設定することをお勧めします。

### <a name="using-a-resource-account"></a>リソースアカウントの使用

Microsoft 365 リソースアカウントを設定する場合は、会議室ライセンスを購入する必要があります。 会議室ライセンスには、組織内のユーザーが Outlook または Teams で会議室を予約できるようにするリソースメールボックスが含まれています。 このライセンスでは、会議参加者間でのビデオおよび音声会議や画面共有も可能です。

外部の電話番号に対して電話をかけたり、発信したりする必要がある場合は、通話プランまたは Microsoft 365 Business Voice [アドオンライセンス](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)が必要になることがあります。 組織で直接ルーティングを有効にしている場合は、会議室の SKU のみが必要になります。

リソースアカウントを作成するときに、アカウントに対して自動的に会議出席依頼を承諾または辞退するか、定期的な会議を許可するか、または他のユーザーがリソースを予約できるようにするかを指定できます。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Microsoft 365 リソースアカウントのコラボレーションバーの詳細については、「 [microsoft 365 管理センターを使用してリソースアカウントを作成](resource-account-ui.md)する」を参照してください。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>外部の電話を発信または受信するかどうかを決定し、リソースアカウントのライセンス要件を特定します。</li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>リソースアカウントを準備します。</li></ul>|

## <a name="configuration-and-deployment"></a>構成と展開

構成と展開を計画する主要分野は次のとおりです。

- リソースアカウントのプロビジョニング
- デバイスの展開
- Microsoft Teams アプリケーションと周辺機器構成のコラボレーションバー
- テスト
- 資産管理

### <a name="account-provisioning"></a>アカウントのプロビジョニング

Microsoft 365 リソースアカウントを使用して、ユーザーがコラボレーションバーを利用できるようにする場合は、「 [microsoft 365 管理センターを使用してリソースアカウントを作成](resource-account-ui.md) する」の手順に従って、1つのコラボレーションバーに対して microsoft 365 リソースアカウントを作成します。 また、組織が直接ルーティングを使用していない場合は、会議室のライセンスをリソースアカウントに追加する必要があります。また、外部電話番号への通話を発信または受信したい場合は、通話プランまたはビジネスボイスライセンスを追加する必要があります。

プライベートで使用するためにコラボレーションバーを個々のユーザーに割り当てる場合は、追加のアカウントを設定する必要はありません。 ユーザーは個人アカウントを使用してコラボレーションバーにサインインできます。

> [!TIP]
> Microsoft 365 リソースアカウントの表示名をわかりやすく簡単に理解できるようにします。 これらは、Microsoft Teams のコラボレーションバーを検索して追加するときにユーザーに表示される名前です。 *サイト* - *ルーム名*(*最大会議*室の容量) などの規則を使うことができます。たとえば、curie の4人の人物の会議室には、表示名として「LON-curie (4)」と表示されます。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>専用リソースアカウントの名前付け規則を決定します。</li><li>個別のアカウントを作成するか、一括プロビジョニングスクリプトを使用するかを決定します。</li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開の計画を開始します。</li></ul>|

### <a name="device-deployment"></a>デバイスの展開

次に、デバイスと割り当てられた周辺機器をルームに配信するための計画を作成してから、インストールと構成に進みます。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトごとの展開を管理するユーザーを決定します。</li><li> Microsoft Teams on the site のコラボレーションバーをインストールし、構成とテストに着手するリソースを特定します。</li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスのテストを開始します。</li></ul>|

### <a name="testing"></a>テスト

Microsoft Teams のコラボレーションバーが展開されたら、それをテストする必要があります。 デバイスにサインインし、展開されたデバイスで予期される機能が動作していることを確認します。 Microsoft Teams 管理センターの [**デバイス**] タブの [**コラボレーションバー** ] セクションに、デバイスが表示されていることを確認することを強くお勧めします。 また、さまざまなテスト通話と会議を行って、品質とパフォーマンスをチェックすることも重要です。

Microsoft Teams の一般的なロールアウトの一環として、通話品質ダッシュボードの構築ファイル (CQD) を構成し、品質の傾向を監視し、エクスペリエンスレビュープロセスに参加することをお勧めします。 詳細については、「 [エクスペリエンスの品質レビューガイド](https://aka.ms/qerguide)」を参照してください。

### <a name="asset-management"></a>資産管理

展開の一環として、ルーム名、サインインしたリソースアカウント、および割り当てられた周辺機器を使用して、資産登録を更新します。

## <a name="related-topics"></a>関連項目

[Microsoft Teams 管理センターを使用して Microsoft Teams のコラボレーションバーのアカウントを構成する](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
