---
title: Android にMicrosoft Teams Roomsをデプロイする
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Android にMicrosoft Teams Roomsをデプロイする方法については、こちらの記事を参照してください。
ms.openlocfilehash: 52b865879db3941b5631d7b22c25bd8f6e4d3ce6
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438415"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Android にMicrosoft Teams Roomsをデプロイする

Android でのMicrosoft Teams Roomsのデプロイは、次のフェーズに分けることができます。

- **サイトの準備** デプロイの場所 (会議室) がデプロイ要件を満たしていることを確認します。
- **サービスの準備** リソース アカウントを作成してデバイスに割り当てます ([「Microsoft 365 管理センターを使用してリソース アカウントを作成する」を参照してください](resource-account-ui.md))。 専用ルーム ライセンスを使用することをお勧めしますが、適切にライセンスが付与されたエンド ユーザー アカウントは、Android でTeams Roomsにサインインすることもできます。
- **構成とデプロイ** Teams Roomsを設定し、必要な周辺機器を接続します (詳細については、製造元のドキュメントを参照してください)。

Teams Roomsを管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「[Microsoft Teams 管理者ロールを使用して Teams を管理する」を](../using-admin-roles.md)参照してください。

## <a name="site-readiness"></a>サイトの準備

順序付けされたデバイスが組織に配信されている間は、ネットワーク、設備、およびオーディオ ビジュアル の各チームと協力して、展開要件が満たされ、各サイトと会議室が電源、ネットワーク、表示の観点から準備ができていることを確認します。

Android サイトでのTeams Roomsに関する推奨事項は次のとおりです。

- 最大5名まで宿泊できます。
- 専用リソース アカウント
- タッチ対応ディスプレイ
- イーサネット ケーブル
- Microsoft Teams メディアのネットワークで有効になっているサービス品質 (QoS)

物理的なインストールに関する考慮事項については、製造元のドキュメントを参照し、ある場合は、スクリーンをインストールしてマウントし、ケーブルを実行する前に、オーディオ ビジュアル チームのエクスペリエンスを活用してください。

> [!TIP]
> 帯域幅の計画とリアルタイム トラフィックに [対するネットワーク](../prepare-network.md) の適合性の評価については、「Teams 用のネットワークを準備する」をご覧ください。
>
> Teams デバイスとインターネットの間にプロキシ サーバーを配置することはお勧めしません。 プロキシ サーバーと Teams の詳細については、「Teams [のプロキシ サーバー](../proxy-servers-for-skype-for-business-online.md)」を参照してください。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトが Android 上のTeams Roomsのサイトの準備要件を満たしていることを確認します。</li><li>各サイトに十分な帯域幅があることを確認します。</li></ul>|
| ![次の手順を示すアイコン。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>Android のデプロイと構成に関するTeams Roomsの計画を開始します。</li></ul>|

## <a name="service-readiness"></a>サービスの準備

Teams Roomsをデプロイする前に、365 Microsoftリソース アカウント、エンド ユーザー アカウント、またはその両方の組み合わせを使用するかどうかを決定する必要があります。 Microsoft 365 リソース アカウントは、会議室、プロジェクターなど、特定のリソース専用のメールボックスと Teams アカウントです。 これらのリソース アカウントは、作成時に定義したルールを使用して、会議出席依頼に自動的に応答できます。 Teams Rooms個人のプライベート使用専用でない限り、Microsoft 365 リソース アカウントを設定することをお勧めします。

### <a name="using-a-resource-account"></a>リソース アカウントの使用

Microsoft 365 リソース アカウントを設定する場合は、会議室ライセンスを購入する必要があります。 会議室ライセンスには、組織内のユーザーが Outlook または Teams を使用して会議室を予約できるようにするリソース メールボックスが含まれています。 また、このライセンスにより、会議参加者間のビデオ会議と電話会議と画面共有も可能になります。

外部電話番号との間で通話を受信または発信する必要がある場合は、通話プランまたは[アドオン ライセンス](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)Microsoft 365 Business Voice必要になる場合があります。 組織でダイレクト ルーティングが有効になっている場合は、ミーティング ルーム SKU のみが必要です。

リソース アカウントを作成するときに、アカウントが自動的に会議出席依頼を受け入れるか辞退するか、定期的な会議を許可するか、事前にリソースを予約できる範囲を指定するかを選択できます。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Microsoft 365 リソース アカウントの詳細については、「[Microsoft 365 管理センターを使用してリソース アカウントを作成する](resource-account-ui.md)」を参照してください。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>外部通話を発信または受信するかどうかを決定し、リソース アカウントのライセンス要件を特定します。</li></ul>|
| ![次の手順を示すアイコン。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>リソース アカウントを準備します。</li></ul>|

## <a name="configuration-and-deployment"></a>構成と展開

構成と展開を計画する主要分野は次のとおりです。

- リソース アカウントのプロビジョニング
- デバイスの展開
- Teams Roomsアプリケーションと周辺機器の構成
- テスト
- 資産管理

### <a name="account-provisioning"></a>アカウントのプロビジョニング

Microsoft 365 リソース アカウントを使用して、ユーザーが Android デバイスでTeams Roomsを予約できるようにする場合は、「[Microsoft 365 管理センターを使用してリソース アカウントを作成](resource-account-ui.md)する」の手順に従って、Teams Roomsごとに Microsoft 365 リソース アカウントを作成します。 1 つを必要とする Android デバイス上。 また、これは、リソース アカウントに会議室ライセンスを追加する必要があり、外部の電話番号との間で通話を発信または受信する場合は、組織が直接ルーティングを使用していない場合は通話プランまたは Business Voice ライセンスを追加する必要があります。

個人ユーザーにプライベート使用のためにTeams Roomsを割り当てる場合は、追加のアカウントを設定する必要はありません。 ユーザーは、個人用アカウントを使用して Android デバイスでTeams Roomsにサインインできます。

> [!TIP]
> Microsoft 365 リソース アカウントの表示名をわかりやすいものにします。 これらは、Teams Roomsを検索して会議に追加するときにユーザーに表示される名前です。 *サイト*-*ルーム名* (*最大会議室容量*) などの規則を使用できます。そのため、たとえば、ロンドンの 4 人用ミーティング ルームである Curie には、表示名 LON-CURIE(4) が付いている場合があります。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>専用リソース アカウントの名前付け規則を決定します。</li><li>個々のアカウントを作成するか、一括プロビジョニング スクリプトを使用するかを決定します。</li></ul>|
| ![次の手順を示すアイコン。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>デバイスの展開の計画を開始します。</li></ul>|

### <a name="device-deployment"></a>デバイスの展開

次に、デバイスとその割り当てられた周辺機器を会議室に配信する計画を作成し、インストールと構成に進む必要があります。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![判断ポイントを表すアイコン。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトごとの展開を管理するユーザーを決定します。</li><li> サイトにTeams Roomsをインストールし、構成とテストを行うリソースを特定します。</li></ul>|
| ![次の手順を示すアイコン。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>デバイスのテストを開始します。</li></ul>|

### <a name="testing"></a>テスト

Teams Roomsをデプロイしたら、テストする必要があります。 Teams Roomsにサインインし、期待される機能が機能していることを確認します。 Microsoft Teams 管理センターの [**Teams デバイス**] タブの [**Android のTeams Rooms**] セクションに表示されることを強くお勧めします。 また、品質とパフォーマンスを確認するために、多数のテスト通話や会議を行うことも重要です。

一般的なMicrosoft Teams ロールアウトの一環として、通話品質ダッシュボード (CQD) のビルド ファイルを構成し、品質の傾向を監視し、品質レビュー プロセスに参加することをお勧めします。 詳細については、「 [品質のエクスペリエンス レビュー ガイド](../quality-of-experience-review-guide.md)」を参照してください。

### <a name="asset-management"></a>資産管理

デプロイの一環として、会議室名、サインインしたリソース アカウント、割り当てられた周辺機器で資産レジスタを更新します。

## <a name="related-topics"></a>関連項目

[会議室と共有 Teams デバイスのリソース アカウントを作成する](../rooms/with-office-365.md)