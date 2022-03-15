---
title: Android Microsoft Teams会議室を展開する
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
description: この記事では、Android 上の会議室Microsoft Teamsについて説明します。
ms.openlocfilehash: 55e410b1863effd671f08cba663211b78f76e30f
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503544"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Android Microsoft Teams会議室を展開する

Android Microsoft Teams Rooms のデプロイは、次のフェーズに分け可能です。

- **サイトの準備** デプロイの場所 (会議室) がデプロイ要件を満たしていることを確認します。
- **サービスの準備** リソース アカウントを作成し、デバイスに割り当てる (「リソース アカウントを使用してリソース アカウントを作成する」[Microsoft 365 管理センター](resource-account-ui.md))。 専用ルーム ライセンスを使用することをお勧めしますが、適切にライセンスされたエンド ユーザー アカウントは、Android 上の Teams にサインインすることもできます。
- **構成とデプロイ** 会議室をTeamsし、必要な周辺機器を接続します (詳細については、製造元のドキュメントを参照してください)。

会議室をTeamsするには、グローバル管理者、サービス管理者、Teamsデバイス管理者Teams必要があります。管理者ロールの詳細については、「管理者ロールを使用して管理者[ロールMicrosoft Teams管理する」を](../using-admin-roles.md)参照Teams。

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
> 「帯域幅の計画とリアルタイム トラフィックに対するネットワーク[の適合性の評価](../prepare-network.md)Teamsネットワークを準備する」を参照してください。
>
> 複数のデバイスとインターネットの間にプロキシ Teams配置はお勧めしません。 プロキシ サーバーとプロキシ サーバーの詳細については、「Teams プロキシ [サーバー」を参照Teams](../proxy-servers-for-skype-for-business-online.md)。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトがコラボレーション バーのサイト準備要件を満たしていることを確認Microsoft Teams。</li><li>各サイトに十分な帯域幅があることを確認します。</li></ul>|
| ![次のステップを示すアイコン。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>コラボレーション バーのデプロイと構成の計画を開始します。</li></ul>|

## <a name="service-readiness"></a>サービスの準備

Teams Rooms をデプロイする前に、Microsoft 365 リソース アカウント、エンド ユーザー アカウント、または両方を使用するか決定する必要があります。 Microsoft 365アカウントは、会議室Teamsプロジェクターなど、特定のリソース専用のメールボックス アカウントとリソース アカウントです。 これらのリソース アカウントは、作成時に定義したルールを使用して、会議出席招待に自動的に応答できます。 会議室Teams特定の個人専用でプライベート使用を行う場合を限り、Microsoft 365 リソース アカウントを設定することをお勧めします。

### <a name="using-a-resource-account"></a>リソース アカウントの使用

リソース アカウントを設定するMicrosoft 365、リソース アカウントのライセンスを購入ミーティング ルーム必要があります。 このミーティング ルームには、組織内のユーザーが会議室または会議室を通じて会議室を予約できるリソース メールボックスOutlook含Teams。 このライセンスでは、会議参加者間でのビデオ会議と電話会議と画面共有も可能です。

外部の電話番号との間で通話を受信または発信する必要がある場合は、通話プランまたはアドオン ライセンスMicrosoft 365 Business Voice[必要な場合があります](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)。 組織で直接ルーティングを有効にしている場合は、SKU のミーティング ルームします。

リソース アカウントを作成するときに、アカウントで会議出席依頼を自動的に承諾または拒否するか、定期的な会議を許可するか、ユーザーがリソースを予約できる時間を事前に指定するかなどについて選択できます。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

リソース アカウントの詳細についてはMicrosoft 365リソース アカウントを使用してリソース アカウントを作成[するMicrosoft 365 管理センター](resource-account-ui.md)。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>外部の電話の送受信を行うかどうかを決定し、リソース アカウントのライセンス要件を特定します。</li></ul>|
| ![次のステップを示すアイコン。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>リソース アカウントを準備します。</li></ul>|

## <a name="configuration-and-deployment"></a>構成と展開

構成と展開を計画する主要分野は次のとおりです。

- リソース アカウントのプロビジョニング
- デバイスの展開
- Teams 会議室のアプリケーションと周辺機器の構成
- テスト
- 資産管理

### <a name="account-provisioning"></a>アカウントのプロビジョニング

Microsoft 365 リソース アカウントを使用してコラボレーション バーを予約する場合は、「[Microsoft 365 管理センター](resource-account-ui.md) を使用してリソース アカウントを作成する」の手順に従って、必要なコラボレーション バーごとに Microsoft 365 リソース アカウントを作成します。 また、リソース アカウントに ミーティング ルーム ライセンスを追加する必要があります。また、外部の電話番号との間で通話を発信または受信する場合は、組織が直接ルーティングを使用していない場合は、通話プランまたは Business Voice ライセンスを追加する必要があります。

プライベート使用のために Teamsルームを個々のユーザーに割り当てる場合は、追加のアカウントを設定する必要はありません。 ユーザーは、個人用アカウントを使用してコラボレーション バーにサインインできます。

> [!TIP]
> リソース アカウントの表示名をMicrosoft 365わかりやすい名前にします。 これらは、会議室を検索して会議に追加するときにTeams表示される名前です。 *SiteRoom*- *Name*(*Max Room Capacity*) のような規則を使用できます。そのため、たとえば、ロンドンの 4 人の会議室である Curie には、表示名 LON-CURIE(4) が付く場合があります。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>専用リソース アカウントの名前付け規則を決定します。</li><li>個々のアカウントを作成するか、一括プロビジョニング スクリプトを使用するか決定します。</li></ul>|
| ![次のステップを示すアイコン。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開の計画を開始します。</li></ul>|

### <a name="device-deployment"></a>デバイスの展開

次に、デバイスと割り当てられた周辺機器を会議室に配信する計画を作成し、インストールと構成に進む必要があります。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトごとの展開を管理するユーザーを決定します。</li><li> 会議室をサイトにインストールしTeams構成とテストを実行するリソースを特定します。</li></ul>|
| ![次のステップを示すアイコン。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスのテストを開始します。</li></ul>|

### <a name="testing"></a>テスト

会議室をデプロイしたTeamsテストする必要があります。 Teams 会議室にサインインし、期待される機能が機能している必要があります。 管理センターの [Teams デバイス] タブの [コラボレーション バー]  セクションに表示Microsoft Teams強くお勧めします。 また、品質とパフォーマンスを確認するために、テスト通話や会議を多数行う必要があります。

一般的な Microsoft Teams ロールアウトの一環として、通話品質ダッシュボード (CQD) のファイルの作成、品質の傾向の監視、およびエクスペリエンスの品質レビュー プロセスへの参加を構成することをお勧めします。 詳細については、「エクスペリエンスの品質 [レビュー ガイド」を参照してください](../quality-of-experience-review-guide.md)。

### <a name="asset-management"></a>資産管理

デプロイの一環として、ルーム名、サインイン済みリソース アカウント、および割り当てられた周辺機器を使用してアセット レジスタを更新する必要があります。

## <a name="related-topics"></a>関連項目

[管理センターを使用Microsoft Teams会議室のアカウントMicrosoft Teams構成する](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->