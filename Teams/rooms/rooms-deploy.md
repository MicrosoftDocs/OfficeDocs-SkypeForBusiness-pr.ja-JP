---
title: Microsoft Teams Rooms を展開する
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 展開フェーズを含む、Microsoft Teams Rooms の展開方法の詳細については、この記事を参照してください。
ms.openlocfilehash: 61fce84f9f3737f771e0417443de566444cc2ca2
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839078"
---
# <a name="deployment-overview"></a>展開の概要

Microsoft Teams Rooms の展開は、基本的に次のフェーズに分けられます。

- デプロイの場所 (スペース) がデプロイの依存関係を満たしていることを確認する
- Microsoft TeamsまたはSkype for BusinessとExchangeアカウントの作成とTeams Roomsへの割り当て ([Microsoft Teams Roomsのアカウントの構成に関する](rooms-configure-accounts.md)ページを参照)
- (省略可能)システム用の Azure Monitor のセットアップ (Azure [Monitor を使用したMicrosoft Teams Rooms管理のデプロイ](azure-monitor-deploy.md)に関するページを参照してください)
- 会議スペースでTeams Roomsを設定し、必要な周辺機器を接続する (デバイスのセットの OEM ドキュメントを参照してください)

## <a name="site-readiness"></a>サイトの準備 

順序付けられたデバイスが組織に配信されている間は、ネットワーク、施設、AV チームと連携して、展開の依存関係が満たされ、各サイトとスペースが電源、ネットワーク、および表示の面で準備ができていることを確認します。 また、物理的なインストール要件を満たしていることを確認します。 物理的なインストールに関する考慮事項については、ベンダーに問い合わせて、画面のインストールと取り付け、ケーブル接続の実行に関する AV チームの経験を活用してください。

これらの依存関係の詳細については、以下の計画ガイダンスのリンクを参照してください。

-   [ネットワークの可用性を確認する](rooms-prep.md#check-network-availability)
-   [証明書](rooms-prep.md#certificates)
-   [プロキシ](rooms-prep.md#proxy)

**Proヒント** - プロキシ サーバーを使用してTeamsへのアクセスを提供する必要がある場合は、まず [この記事を参照してください](../proxy-servers-for-skype-for-business-online.md)。 プロキシ サーバー経由のリアルタイム メディア トラフィックをMicrosoft Teamsする場合は、プロキシ サーバーを完全にバイパスすることをお勧めします。 Microsoft Teamsトラフィックは既に暗号化されているため、プロキシ サーバーはセキュリティを強化せず、リアルタイム トラフィックに待機時間を追加します。 広範囲の展開の一環として、「[Teams 用にネットワークを準備する](../prepare-network.md)」のガイダンスに従って、帯域幅の計画を行い、実際のトラフィックに対するネットワークの適合性を評価することをお勧めします。

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![サイトを確認します。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトが Microsoft Teams Rooms の重要な要件を満たしていることを確認します。</li><li>各サイトに十分な帯域幅があることを確認します。</li></ul>| 
| ![デバイスの展開を計画します。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>デバイスの展開と構成の計画を開始します。</li></ul>| 

## <a name="service-readiness"></a>サービスの準備

Microsoft Teams Rooms の展開を準備するには、次の主要な中心的タスクを実行します。

-   Microsoft Teams Roomsリソース アカウントを定義します。
-   Teams Room をAzure Active Directoryに参加させる場合は、動的メンバーシップを持つAzure AD グループを準備して、すべてのTeams Rooms リソース アカウントを保持します。 これにより、条件付きアクセス ポリシーの適用など、将来の管理が簡略化されます。 動的グループAzure AD最も簡単に活用するために、Teams Roomsリソース アカウントを一意に識別する名前付け規則を決定します。
-   Teams Room を Active Directory に参加させる場合は、Microsoft Teams Roomsマシンとリソース アカウントを保持する組織単位と Active Directory グループを準備し、必要に応じて powerShell リモート処理を有効にするためにグループ ポリシー オブジェクト (GPO) を準備します。

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>リソース アカウント機能Microsoft Teams Rooms定義する 

Microsoft Teams Roomsデプロイで有効にすることに決めたコラボレーション シナリオに応じて、有効にする各Microsoft Teams ルームに割り当てる機能と機能を決定する必要があります。

| **シナリオ** | **説明** | **Microsoft Teams Rooms のサービス アカウント機能** |
|---------- |------------- | --- |
| 対話型の会議            | 音声、ビデオ、画面共有を使用。Microsoft Teams Rooms を予約可能なリソースにする                     | Microsoft TeamsまたはSkype for Businessに対して有効;Exchangeに対して有効 (リソース メールボックス) |
| ダイヤルイン会議            | 本体で [新しい会議] をタップするときに電話会議の電話番号を取得する | 電話会議の有効化                                          |
| 発信/着信 PSTN 通話 | Microsoft Teams Rooms のコンソールで PSTN 通話を受信できるようにする                                         | 電話システムの有効化                                                |

Microsoft Teams Rooms のアカウントの詳細については、「[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)」を参照してください。


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![シナリオのサポート。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サポートするシナリオを決定し、Microsoft Teams Roomsリソース アカウントのライセンス要件を特定します。</li></ul>| 
| ![ホスト マシンを準備します。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>マシン アカウントとリソース アカウントをホストする準備をします。</li></ul>| 


_リソース アカウント計画テーブルMicrosoft Teams Rooms例_

| **サイト**  | **部屋の名前** | **部屋の種類** | **将来の部屋の機能**                                                 | **Microsoft Teams Rooms のアカウント機能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| ロンドン HQ | Curie         | 中        | 1 つのスクリーン、オーディオ、ビデオ、プレゼンテーション <br>ダイヤルイン会議アクセス<br> PSTN アクセス  | Exchangeに対して有効 (リソース メールボックス) <br>電話会議の有効化 <br>電話システムの有効化 |
| シドニー HQ | Hill          | 大         | 2 つのスクリーン、オーディオ、ビデオ、プレゼンテーション<br>ダイヤルイン会議アクセス<br> PSTN アクセス  | Skype for Businessに対して有効 <br>Exchangeに対して有効 (リソース メールボックス)<br> 電話会議の有効化 <br>電話システムの有効化 |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Microsoft Teams Roomsアカウントとリソース アカウントをホストする準備 (省略可能)

Microsoft Teams Roomsアカウントとリソース アカウントを管理およびレポートできるようにするには、オンプレミスの Active DirectoryまたはAzure Active Directory (Azure AD) を準備します。 

すべてのMicrosoft Teams Roomsリソース アカウントを追加するオンプレミスの Active DirectoryまたはAzure Active Directory グループを定義します。 Azure Active Directoryを使用する場合は、動的グループを使用して、リソース アカウントをグループに自動的に追加および削除することを検討してください。

オンプレミスの Active Directory階層に 1 つの組織単位を定義して、すべてのMicrosoft Teams Roomsコンピューター アカウントを保持します (ドメインに参加している場合)、すべてのMicrosoft Teams Rooms ユーザー アカウントを保持する 1 つの組織単位を定義します。 ドメインに参加しているMicrosoft Teams Roomsに適用するポリシーのみを適用するには、グループ ポリシー継承を無効にします。

Microsoft Teams Rooms のコンピューター アカウントが含まれている組織単位に割り当てられるグループ ポリシー オブジェクトを作成します。 これは次のように使用します。 

-   [電源とローカル アカウントの設定](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)を行います。
-   Windows Update を有効にします。
-   PowerShell のリモート処理を有効にします。 起動スクリプトを構成してスクリプトを実行できます:Enable-PSRemoting -Force

PowerShell を使用すると、構成情報の取得や設定など、いくつかのリモート管理アクティビティを実行できます。 Powershell のリモート処理は、PowerShell リモート管理を実施する *前に* 有効にしておく必要があり、展開プロセスの一部として見なすか、グループポリシーを使用して構成する必要があります。 これらの機能と有効化の詳細については、「[保守と運用](rooms-operations.md#remote-management-using-powershell)」を参照してください。 


## <a name="configuration-and-deployment"></a>構成と展開 

構成と展開を計画する主要分野は次のとおりです。

-   リソース アカウントのプロビジョニング
-   デバイス ソフトウェアのインストール
-   デバイスの展開
-   Microsoft Teams Rooms のアプリケーションと周辺機器の構成
-   テスト
-   資産管理

### <a name="resource-account-provisioning"></a>リソース アカウントのプロビジョニング 

各Microsoft Teams Rooms デバイスには、Microsoft TeamsまたはSkype for Business、およびExchangeの両方に対して有効にする必要がある専用の一意のリソース アカウントが必要です。 このアカウントには、Exchangeでホストされている会議室メールボックスが必要です。 デバイスが受信会議出席依頼を自動的に受け入れることができるように、予定表処理を構成する必要があります。 これらのアカウントの作成に関する詳細については、「[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)」を参照してください。 

**Pro のヒント** - 各Microsoft Teams Rooms は、ネットワーク上で有効な一意のコンピューター名が必要です。 多くの監視および警告システムでは、キー識別子としてコンピューター名が表示されるため、アクションが必要であるとフラグが付けられた Microsoft Teams Rooms をサポート担当者が簡単に見つけられるように、Microsoft Teams Rooms の展開用の命名規則を作成することが重要です。 例としては、MTR-*サイト*-*部屋の名前* (MTR-LON-CURIE) などのパターンが使用されることがあります。 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![名前付け規則を決定します。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft Teams Roomsリソース アカウントの名前付け規則を決定します。</li><li>個別のアカウントを作成するか、一括プロビジョニング スクリプトを使用するかを決定します。</li></ul>| 
| ![次の手順を実行します。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>デバイスの展開の計画を開始します。</li></ul>| 


### <a name="device-software-installation"></a>デバイス ソフトウェアのインストール 

Teams Roomsは、元の機器メーカー (OEM) によって事前にインストールされます。

[Microsoft Azure Monitor を](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)使用してMicrosoft Teams Rooms展開を監視し、可用性、ハードウェア/ソフトウェア エラー、およびアプリケーションバージョンMicrosoft Teams Rooms報告する方法に関するガイダンスを提供します。 Microsoft Operations Management Suite を使用する場合は、ソフトウェアのインストール プロセスの一環として Operations Management Suite エージェントをインストールし、ワークスペースに対してワークスペース接続情報を構成する必要があります。 

また、Microsoft Teams Rooms をドメインに参加させるかどうかも検討してください。 ドメイン参加の利点については、「[Microsoft Teams Roomsのグループ ポリシーの構成」を参照](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)してください。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![decision points デバイスの名前付け。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>デプロイ中に使用するMicrosoft Teams Roomsリソース アカウントの名前付け規則を決定します。</li><li>Microsoft Teams Roomsデバイスをドメインに参加させるかどうかを決定します。 </li><li>Azure Monitor を使用してMicrosoft Teams Roomsデプロイを監視するかどうかを決定します。</li> 
| ![次の手順では、デバイスを計画します。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>デバイスの展開手法の計画を開始します。</li></ul>| 


### <a name="device-deployment"></a>デバイスの展開

Microsoft Teams Roomsリソース アカウントを作成して管理する方法を決定したら、デバイスとその割り当てられた周辺機器を会議室に発送する計画を作成し、インストールと構成に進みます。


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![サイトごとの展開を管理します。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトごとの展開を管理するユーザーを決定します。</li><li> サイトにMicrosoft Teams Roomsをインストールし、構成とテストを行うリソースを特定します。</li></ul>| 
| ![デバイス テストを開始します。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>デバイスのテストを開始します。</li></ul>| 

_サンプル: 展開テーブル_

| **サイト**  | **部屋の名前** | **部屋の種類** | **Microsoft Teams Rooms システム**  | **周辺機器**  | **Microsoft Teams Rooms のコンピューター名**  | **Microsoft Teams Rooms のリソース アカウント**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| ロンドン HQ | Curie         | 中        |                                   |                  |                                          |                                             |
| シドニー HQ | Hill          | 大         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams Rooms のアプリケーションと周辺機器の構成 

各Microsoft Teams Rooms システムが物理的にデプロイされ、サポートされている周辺機器が接続されたら、Microsoft Teams Roomsリソース アカウントとパスワードを割り当てて有効にするために、Microsoft Teams Rooms アプリケーションを構成する必要があります。Microsoft TeamsまたはSkype for Businessにサインインし、Exchange Teams Rooms。

各Microsoft Teams Rooms システムは、手動で構成できます。 または、一元的に格納された Teams Rooms XML 構成ファイルを使用して、アプリケーション設定を管理することもできます。

XML 構成ファイルの使用方法の詳細については、「[XML 構成ファイルを使用して Microsoft Teams Rooms のコンソール設定をリモートで管理する](xml-config-file.md)」を参照してください。 

[リモート PowerShell](rooms-operations.md#remote-management-using-powershell) を使用して、レポートのニーズに合わせて Microsoft Teams Rooms の構成を取得できます。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![デシジョン ポイントの構成。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>各Microsoft Teams Rooms システムを手動で構成するか、一元管理された XML ファイル (Microsoft Teams Rooms デバイスごとに作成される 1 つのファイル) を使用するかを決定します。</li></ul>| 
| ![次の手順のリモート アプローチ。](../media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>リモート管理手法を定義します。</li></ul>| 

### <a name="testing"></a>テスト

Teams Roomsがデプロイされたら、テストする必要があります。 [Microsoft Teams Rooms ヘルプ](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us)に記載されている機能が、展開されたデバイスで機能していることを確認してください。 展開チームは、Microsoft Teams Roomsが管理センターに表示されていることを確認Teams高くお勧めします。 また、さまざまなテスト通話と会議を行って、品質をチェックすることも重要です。 詳細については、この「[便利な展開チェックリスト](console.md#microsoft-teams-rooms-deployment-checklist).」を参照してください。

一般的な Teams または Skype for Business のロールアウトの一環として、通話品質ダッシュボード (CQD) の構築ファイルを構成し、品質の傾向を監視し、Quality of Experience (QoE) レビューのプロセスに参加することをお勧めします。 詳細については、「[Teams の通話品質の向上と監視](../monitor-call-quality-qos.md)」を参照してください。 

### <a name="asset-management"></a>資産管理

デプロイの一環として、ルーム名、Microsoft Teams Rooms名、Microsoft Teams Roomsリソース アカウント、割り当てられた周辺機器で資産登録を更新する必要があります。 

_サンプル: 資産テーブル_

| **サイト**  | **部屋の名前** | **部屋の種類** | **Microsoft Teams Rooms のシリアル番号**  | **周辺機器/シリアル番号/ポート**  | **Microsoft Teams Rooms のコンピューター名**  | **Microsoft Teams Rooms のサービス アカウント**  | **展開日** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| ロンドン HQ | Curie         | 中        |                                          |                                          |                                          |                                            |                   |
| シドニー HQ | Hill          | 大         |                                          |                                          |                                          |                                            |                   |
