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
ms.openlocfilehash: 8240eaff652a0ff465c9eb06242075b0d6baeba8
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503684"
---
# <a name="deployment-overview"></a>展開の概要

Microsoft Teams Rooms の展開は、基本的に次のフェーズに分けられます。

- デプロイの場所 (スペース) がデプロイの依存関係を満たした確認
- アカウントMicrosoft TeamsまたはSkype for Business作成Exchangeし、Teams 会議室に割り当てる (「Microsoft Teams 会議室のアカウントを構成する」[を参照](rooms-configure-accounts.md)してください)
- (省略可能)システム用に Azure Monitor を設定する (「Azure [Monitor を使用Microsoft Teams Rooms 管理をデプロイする」を参照してください。](azure-monitor-deploy.md)
- 会議室Teamsのセットアップと必要な周辺機器の接続 (一連のデバイスの OEM ドキュメントを参照)

## <a name="site-readiness"></a>サイトの準備 

注文されたデバイスが組織に配信されている間は、ネットワーク、施設、AV チームと共同で、展開の依存関係が満たされ、各サイトとスペースが電源、ネットワーク、表示の面で準備ができていることを確認します。 また、物理的なインストール要件を満たしていることを確認します。 物理的なインストールに関する考慮事項については、ベンダーに相談し、画面のインストールとマウント、ケーブル配線の実行時に AV チームのエクスペリエンスを活用してください。

これらの依存関係の詳細については、以下の計画ガイダンスのリンクを参照してください。

-   [ネットワークの可用性を確認する](rooms-prep.md#check-network-availability)
-   [証明書](rooms-prep.md#certificates)
-   [プロキシ](rooms-prep.md#proxy)

**Proヒント** - プロキシ サーバーを使用してアプリケーションへのアクセスを提供する必要Teams、この記事 [を最初に確認してください](../proxy-servers-for-skype-for-business-online.md)。 プロキシ サーバーを使用Microsoft Teamsリアルタイム メディア トラフィックを処理する場合は、プロキシ サーバーを完全にバイパスすることをお勧めします。 Microsoft Teamsは既に暗号化されています。そのため、プロキシ サーバーはセキュリティを高めず、リアルタイム トラフィックに待機時間を追加します。 広範囲の展開の一環として、「[Teams 用にネットワークを準備する](../prepare-network.md)」のガイダンスに従って、帯域幅の計画を行い、実際のトラフィックに対するネットワークの適合性を評価することをお勧めします。

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![サイトを確認します。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトが Microsoft Teams Rooms の重要な要件を満たしていることを確認します。</li><li>各サイトに十分な帯域幅があることを確認します。</li></ul>| 
| ![デバイスのデプロイを計画します。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開と構成の計画を開始します。</li></ul>| 

## <a name="service-readiness"></a>サービスの準備

Microsoft Teams Rooms の展開を準備するには、次の主要な中心的タスクを実行します。

-   Rooms リソース Microsoft Teamsを定義します。
-   会議室にTeams参加Azure Active Directory、Azure AD Rooms のすべてのリソース アカウントを保持する動的メンバーシップを持つ Teams グループを準備します。 これにより、条件付きアクセス ポリシーの適用など、将来の管理が簡略化されます。 動的グループを最も簡単に利用Azure AD、会議室のリソース アカウントを一意に識別する名前付け規則Teams決定します。
-   Teams Room を Active Directory に参加する場合は、組織単位と Active Directory グループを準備し、Microsoft Teams Rooms のマシンアカウントとリソース アカウントを保持し、必要に応じてグループ ポリシー オブジェクト (GPO) を準備して PowerShell リモート処理を有効にします。

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>会議室Microsoft Teamsのリソース アカウント機能を定義する 

Microsoft Teams Rooms の展開で有効にしたコラボレーションシナリオに応じて、有効にする各 Microsoft Teams Room に割り当てる機能を決定する必要があります。

| **シナリオ** | **説明** | **Microsoft Teams Rooms のサービス アカウント機能** |
|---------- |------------- | --- |
| 対話型の会議            | 音声、ビデオ、画面共有を使用。Microsoft Teams Rooms を予約可能なリソースにする                     | ユーザーまたはMicrosoft Teamsに対Skype for Business有効、Exchange (リソース メールボックス) に対して有効 |
| ダイヤルイン会議            | 本体で [新しい会議] をタップするときに電話会議の電話番号を持っている | 電話会議の有効化                                          |
| 発信/着信 PSTN 通話 | Microsoft Teams Rooms のコンソールで PSTN 通話を受信できるようにする                                         | 電話システムの有効化                                                |

Microsoft Teams Rooms のアカウントの詳細については、「[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)」を参照してください。


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![シナリオのサポート。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サポートするシナリオを決定し、Microsoft Teams Rooms リソース アカウントのライセンス要件を特定します。</li></ul>| 
| ![ホスト コンピューターを準備します。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>マシンアカウントとリソース アカウントをホストする準備をします。</li></ul>| 


_会議室Microsoft Teamsリソース アカウント計画テーブルのサンプル_

| **サイト**  | **部屋の名前** | **部屋の種類** | **将来の部屋の機能**                                                 | **Microsoft Teams Rooms のアカウント機能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| ロンドン HQ | Curie         | 中        | 1 つのスクリーン、オーディオ、ビデオ、プレゼンテーション <br>ダイヤルイン会議アクセス<br> PSTN アクセス  | [リソースExchange (リソース メールボックス) に対して有効 <br>電話会議の有効化 <br>電話システムの有効化 |
| シドニー HQ | Hill          | 大         | 2 つのスクリーン、オーディオ、ビデオ、プレゼンテーション<br>ダイヤルイン会議アクセス<br> PSTN アクセス  | 有効なSkype for Business <br>[リソースExchange (リソース メールボックス) に対して有効<br> 電話会議の有効化 <br>電話システムの有効化 |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>会議室とリソース アカウントMicrosoft Teamsホストする準備をする (省略可能)

Microsoft Teams 会議室とリソース アカウントの管理とレポートを作成するには、オンプレミスの Active Directory または Azure Active Directory (Azure AD) を準備します。 

すべての会議室リソース アカウントを追加Azure Active Directoryオンプレミスの Active Directory または Microsoft Teams グループを定義します。 リソース アカウントをAzure Active Directory、動的グループを使用して、グループのリソース アカウントを自動的に追加および削除します。

すべての Microsoft Teams Rooms コンピューター アカウント (ドメインに参加している場合) と 1 つの組織単位を保持し、すべての Microsoft Teams Rooms ユーザー アカウントを保持するために、オンプレミスの Active Directory 階層に 1 つの組織単位を定義します。 グループ ポリシーの継承を無効にして、ドメインに参加している会議室に適用するポリシーのみを適用Microsoft Teamsします。

Microsoft Teams Rooms のコンピューター アカウントが含まれている組織単位に割り当てられるグループ ポリシー オブジェクトを作成します。 これは次のように使用します。 

-   [電源とローカル アカウントの設定](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)を行います。
-   Windows Update を有効にします。
-   PowerShell のリモート処理を有効にします。 スクリプトを実行する起動スクリプトを構成できます:Enable-PSRemoting -Force

PowerShell を使用して、構成情報の取得や設定など、複数のリモート管理アクティビティを実行できます。 Powershell のリモート処理は、PowerShell リモート管理を実施する *前に* 有効にしておく必要があり、展開プロセスの一部として見なすか、グループポリシーを使用して構成する必要があります。 これらの機能と有効化の詳細については、「[保守と運用](rooms-operations.md#remote-management-using-powershell)」を参照してください。 


## <a name="configuration-and-deployment"></a>構成と展開 

構成と展開を計画する主要分野は次のとおりです。

-   リソース アカウントのプロビジョニング
-   デバイス ソフトウェアのインストール
-   デバイスの展開
-   Microsoft Teams Rooms のアプリケーションと周辺機器の構成
-   テスト
-   資産管理

### <a name="resource-account-provisioning"></a>リソース アカウントのプロビジョニング 

各 Microsoft Teams Rooms デバイスには専用の一意のリソース アカウントが必要です。このアカウントは、Microsoft Teams と Skype for Business、Exchange。 このアカウントには、そのアカウントでホストされているルーム メールボックスExchange。 デバイスが着信会議出席依頼を自動的に受け入れできるよう、予定表の処理を構成する必要があります。 これらのアカウントの作成に関する詳細については、「[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)」を参照してください。 

**Pro のヒント** - 各Microsoft Teams Rooms は、ネットワーク上で有効な一意のコンピューター名が必要です。 多くの監視および警告システムでは、キー識別子としてコンピューター名が表示されるため、アクションが必要であるとフラグが付けられた Microsoft Teams Rooms をサポート担当者が簡単に見つけられるように、Microsoft Teams Rooms の展開用の命名規則を作成することが重要です。 例としては、MTR-*サイト*-*部屋の名前* (MTR-LON-CURIE) などのパターンが使用されることがあります。 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![名前付け規則を決定します。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft Teams Rooms リソース アカウントの名前付け規則を決定します。</li><li>個別のアカウントを作成するか、一括プロビジョニング スクリプトを使用するかを決定します。</li></ul>| 
| ![次の手順に進みます。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開の計画を開始します。</li></ul>| 


### <a name="device-software-installation"></a>デバイス ソフトウェアのインストール 

Teams会議室は、OEM (元の機器メーカー) によってプレインストールされています。

[Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) を使用して Microsoft Teams Rooms のデプロイを監視し、可用性、ハードウェア/ソフトウェア エラー、Microsoft Teams Rooms アプリケーション バージョンを報告する方法に関するガイダンスを提供します。 Microsoft Operations Management Suite を使用する場合は、ソフトウェアのインストール プロセスの一環として Operations Management Suite エージェントをインストールし、ワークスペースに対してワークスペース接続情報を構成する必要があります。 

また、Microsoft Teams Rooms をドメインに参加させるかどうかも検討してください。 ドメイン参加の利点については、「Microsoft Teams Rooms のグループ ポリシーの構成[」を参照してください](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![決定ポイントのデバイスの名前付け。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>デプロイ時Microsoft Teams使用する Rooms リソース アカウントの名前付け規則を決定します。</li><li>自分のドメインに会議室デバイスMicrosoft Teams参加するかどうかを決定します。 </li><li>Azure Monitor を使用して会議室のデプロイを監視Microsoft Teams決定します。</li> 
| ![次の手順でデバイスを計画します。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開手法の計画を開始します。</li></ul>| 


### <a name="device-deployment"></a>デバイスの展開

Microsoft Teams Rooms リソース アカウントを作成して管理する方法を決定したら、デバイスとその割り当てられた周辺機器を会議室に発送する計画を作成し、インストールと構成に進みます。


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![サイト別のデプロイを管理します。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトごとの展開を管理するユーザーを決定します。</li><li> Microsoft Teams Rooms をサイトにインストールし、構成とテストを実行するリソースを特定します。</li></ul>| 
| ![デバイステストを開始します。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスのテストを開始します。</li></ul>| 

_サンプル: 展開テーブル_

| **サイト**  | **部屋の名前** | **部屋の種類** | **Microsoft Teams Rooms システム**  | **周辺機器**  | **Microsoft Teams Rooms のコンピューター名**  | **Microsoft Teams Rooms のリソース アカウント**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| ロンドン HQ | Curie         | 中        |                                   |                  |                                          |                                             |
| シドニー HQ | Hill          | 大         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams Rooms のアプリケーションと周辺機器の構成 

各 Microsoft Teams Rooms システムが物理的に展開され、サポートされている周辺機器が接続された後、Microsoft Teams Rooms アプリケーションを構成して Microsoft Teams Rooms リソース アカウントとパスワードを割り当て、Teams Rooms がサインインを有効にする必要があります。Microsoft TeamsまたはSkype for Business、およびExchange。

各Microsoft Teams Rooms システムは、手動で構成できます。 または、Rooms XML 構成ファイルを 1 Teamsに格納してアプリケーション設定を管理することもできます。

XML 構成ファイルの使用方法の詳細については、「[XML 構成ファイルを使用して Microsoft Teams Rooms のコンソール設定をリモートで管理する](xml-config-file.md)」を参照してください。 

[リモート PowerShell](rooms-operations.md#remote-management-using-powershell) を使用して、レポートのニーズに合わせて Microsoft Teams Rooms の構成を取得できます。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![決定ポイントの構成。](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>各Microsoft Teams Rooms システムを手動で構成するか、一元管理された XML ファイル (Microsoft Teams Rooms デバイスごとに作成される 1 つのファイル) を使用するかを決定します。</li></ul>| 
| ![次の手順はリモート アプローチです。](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>リモート管理手法を定義します。</li></ul>| 

### <a name="testing"></a>テスト

会議室Teams後、テストする必要があります。 [Microsoft Teams Rooms ヘルプ](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us)に記載されている機能が、展開されたデバイスで機能していることを確認してください。 展開チームは、管理センターで Microsoft Teams会議室が表示Teamsすることを強くお勧めします。 また、さまざまなテスト通話と会議を行って、品質をチェックすることも重要です。 詳細については、この「[便利な展開チェックリスト](console.md#microsoft-teams-rooms-deployment-checklist).」を参照してください。

一般的な Teams または Skype for Business のロールアウトの一環として、通話品質ダッシュボード (CQD) の構築ファイルを構成し、品質の傾向を監視し、Quality of Experience (QoE) レビューのプロセスに参加することをお勧めします。 詳細については、「[Teams の通話品質の向上と監視](../monitor-call-quality-qos.md)」を参照してください。 

### <a name="asset-management"></a>資産管理

デプロイの一環として、ルーム名、Microsoft Teams 会議室名、Microsoft Teams 会議室リソース アカウント、割り当てられた周辺機器を使用して資産登録を更新する必要があります。 

_サンプル: 資産テーブル_

| **サイト**  | **部屋の名前** | **部屋の種類** | **Microsoft Teams Rooms のシリアル番号**  | **周辺機器/シリアル番号/ポート**  | **Microsoft Teams Rooms のコンピューター名**  | **Microsoft Teams Rooms のサービス アカウント**  | **展開日** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| ロンドン HQ | Curie         | 中        |                                          |                                          |                                          |                                            |                   |
| シドニー HQ | Hill          | 大         |                                          |                                          |                                          |                                            |                   |
