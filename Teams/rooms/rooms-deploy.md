---
title: Microsoft Teams Rooms を展開する
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 展開フェーズを含む、Microsoft Teams Rooms の展開方法の詳細については、この記事を参照してください。
ms.openlocfilehash: 53c4c94717f10dadbad802cff3f233a3a771d166
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662252"
---
# <a name="deployment-overview"></a>展開の概要

Microsoft Teams Rooms の展開は、基本的に次のフェーズに分けられます。

- 展開場所 (会議室) が展開の依存関係を満たしていることを確認する
- Microsoft Teams または Skype for Business アカウントと、Exchange アカウントを作成し、それらをコンソール デバイスに割り当てる (「[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)」を参照してください)
- Microsoft Teams Rooms のコンソールとして機能するように Microsoft Surface タブレットを再設定する (「[Microsoft Teams Rooms のコンソールを構成する](console.md)」、または「[Microsoft Teams Rooms の一括配置ガイドを展開する](rooms-scale.md)」を参照してください)
- (オプション) 使用しているシステムに合わせて Microsoft Operations Management Suite をセットアップする ([ Azure Monitor を使用して Microsoft Teams Rooms 管理を展開する](azure-monitor-deploy.md)」を参照してください)
- 会議室にコンソールをセットアップし、必要な周辺機器を接続する (使用しているデバイスについては、OEM ドキュメントを参照してください)

最後のタスクには AV 技術者を利用できますが、組織の IT 部門はプロセスの他の部分を行う必要があります。 


## <a name="site-readiness"></a>サイトの準備 

注文したデバイスが組織に配送されている間に、ネットワーク、設備、AV チームと協力して、展開の依存関係が満たされ、各サイトと部屋の電力、ネットワーク、ディスプレイの準備ができていることを確認します。 また、物理的なインストール要件を満たしていることを確認します。 物理的なインストールの考慮事項については、製造元のサイトにアクセスして、スクリーンの設置と取り付け、およびケーブル接続を行うときは AV チームの経験を活用してください。

これらの依存関係の詳細については、以下の計画ガイダンスのリンクを参照してください。

-   [ネットワークの可用性を確認する](rooms-prep.md#check-network-availability)
-   [証明書](rooms-prep.md#certificates)
-   [プロキシ](rooms-prep.md#proxy)

**プロのヒント** - プロキシ サーバーを使用して Teams または Skype for Business Online へのアクセスを提供する場合は、まず、[この記事](../proxy-servers-for-skype-for-business-online.md)を参照してください。 プロキシ サーバー経由の Skype for Business トラフィックについては、プロキシ サーバーをすべてバイパスすることをお勧めします。 Skype for Business トラフィックは既に暗号化されているため、プロキシ サーバーによってセキュリティが強化されることはありません。 広範囲の展開の一環として、「[Teams 用にネットワークを準備する](../prepare-network.md)」のガイダンスに従って、帯域幅の計画を行い、実際のトラフィックに対するネットワークの適合性を評価することをお勧めします。

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトが Microsoft Teams Rooms の重要な要件を満たしていることを確認します。</li><li>各サイトに十分な帯域幅があることを確認します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開と構成の計画を開始します。</li></ul>| 

## <a name="service-readiness"></a>サービスの準備

Microsoft Teams Rooms の展開を準備するには、次の主要な中心的タスクを実行します。

-   Microsoft Teams Rooms のサービス アカウント機能を定義します。
-   Microsoft Teams Rooms のコンピューター アカウントとサービスアカウントを保持するために、組織単位と Active Directory グループを準備します。また、必要に応じて、PowerShell のリモート処理を有効にするためにグループ ポリシー オブジェクト (GPO) を準備します。

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Microsoft Teams Rooms のサービス アカウント機能を定義する 

Microsoft Teams Rooms の展開で有効にすることにしたコラボレーション シナリオに応じて、有効にする Microsoft Teams Rooms の各サービス アカウントに割り当てる機能と能力を決定する必要があります。

| **シナリオ** | **説明** | **Microsoft Teams Rooms のサービス アカウント機能** |
|---------- |------------- | --- |
| 対話型の会議            | 音声、ビデオ、画面共有を使用。Microsoft Teams Rooms を予約可能なリソースにする                     | Skype for Business の有効化、Exchange の有効化 (リソース メールボックス) |
| ダイヤルイン会議            | ダイヤルイン会議の調整を使用して、Microsoft Teams Rooms のコンソールから会議を *直接* 開始できるようにする | 電話会議の有効化                                          |
| 発信/着信 PSTN 通話 | Microsoft Teams Rooms のコンソールで PSTN 通話を受信できるようにする                                         | 電話システムの有効化                                                |

Microsoft Teams Rooms のアカウントの詳細については、「[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)」を参照してください。


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サポートするシナリオを決定し、Microsoft Teams Rooms のサービス アカウントのライセンス要件を特定します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>コンピューター アカウントとサービス アカウントをホストするための準備を行います。</li></ul>| 


_サンプル: Microsoft Teams Rooms のサービス アカウントの計画テーブル_

| **サイト**  | **部屋の名前** | **部屋の種類** | **将来の部屋の機能**                                                 | **Microsoft Teams Rooms のアカウント機能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| ロンドン HQ | Curie         | 中        | 1 つのスクリーン、オーディオ、ビデオ、プレゼンテーション <br>ダイヤルイン会議アクセス<br> PSTN アクセス  | Skype for Business の有効化、Exchange の有効化 (リソース メールボックス) <br>電話会議の有効化 <br>電話システムの有効化 |
| シドニー HQ | Hill          | 大         | 2 つのスクリーン、オーディオ、ビデオ、プレゼンテーション<br>ダイヤルイン会議アクセス<br> PSTN アクセス  | Skype for Business の有効化、Exchange の有効化 (リソース メールボックス)<br> 電話会議の有効化 <br>電話システムの有効化 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Microsoft Teams Rooms のコンピューター アカウントとサービス アカウントをホストするための準備をする (オプション)

Microsoft Teams Rooms のコンピューター アカウントとサービス アカウントを管理してレポートを作成できるようにするには、オンプレミスの Active Directory または Azure Active Directory (Azure AD) を準備します。 

オンプレミスの Active Directory または Azure AD グループを定義して、Microsoft Teams Rooms のすべてのサービス (ユーザー) アカウントを追加してから、Microsoft Teams Rooms の展開で CSUserSession PowerShell コマンドレットを使用して使用状況レポートを作成します。 たとえば、SkypeRoomSystemsv2-Service-Accounts という名前のグループを作成します。 


オンプレミスの Active Directory または Azure AD の階層に 1 つの組織単位を定義して、Microsoft Teams Rooms のすべてのコンピューター アカウント (ドメインに参加している場合) を保持します。また、Microsoft Teams Rooms のすべてのユーザー アカウントを保持するために 1 つの組織単位を定義します。 Microsoft Teams Roomsのコンピューター アカウント用の組織単位を作成する場合は、継承を無効にして、ドメインに参加している Microsoft Teams Rooms に適用するポリシーだけを適用することを検討してください。 

Microsoft Teams Rooms のコンピューター アカウントが含まれている組織単位に割り当てられるグループ ポリシー オブジェクトを作成します。 これは次のように使用します。 

-   [電源とローカル アカウントの設定](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)を行います。
-   Windows Update を有効にします。
-   PowerShell のリモート処理を有効にします。 次の簡単なスクリプトを実行するように、スタートアップ スクリプトを構成することができます。 Enable-PSRemoting -Force

PowerShell を使用して、構成情報の取得や設定を含む、多くのリモート管理操作を実行できます。 Powershell のリモート処理は、PowerShell リモート管理を実施する *前に* 有効にしておく必要があり、展開プロセスの一部として見なすか、グループポリシーを使用して構成する必要があります。 これらの機能と有効化の詳細については、「[保守と運用](rooms-operations.md#remote-management-using-powershell)」を参照してください。 


## <a name="configuration-and-deployment"></a>構成と展開 

構成と展開を計画する主要分野は次のとおりです。

-   アカウントのプロビジョニング
-   デバイス ソフトウェアのインストール
-   デバイスの展開
-   Microsoft Teams Rooms のアプリケーションと周辺機器の構成
-   テスト
-   資産管理

### <a name="account-provisioning"></a>アカウントのプロビジョニング 

Microsoft Teams Rooms の各デバイスには、固有の一意のリソース アカウントが必要です。このアカウントは、Microsoft Teams または Skype for Business、Exchange の両方で有効にする必要があります。 このアカウントには、Exchange でホストされている会議室メールボックスが必要です。また、Teams または Skype for Business を使用している場合は、会議室として有効化する必要があります。 Exchange 側では、デバイスが受信した会議出席依頼を自動的に受け入れるように、予定表の処理を構成する必要があります。 これらのアカウントの作成に関する詳細については、「[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)」を参照してください。 

**プロのヒント** – これらのアカウントの表示名は、説明的でわかりやすいものにします。 これらは、ユーザーが Microsoft Teams Rooms システムを検索したり会議を追加したりするときに表示される名前です。 組織によっては、"*サイト*-*部屋の名前*(*最大収容人数*)-RS" などの命名規則を使用しています。この場合、たとえば、Curie (ロンドンの 12 人用会議室) は、"LON-CURIE (12)-RS" という表示名になります。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>Microsoft Teams Rooms のアカウントの命名規則を決定します。</li><li>個別のアカウントを作成するか、一括プロビジョニング スクリプトを使用するかを決定します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開の計画を開始します。</li></ul>| 


### <a name="device-software-installation"></a>デバイス ソフトウェアのインストール 

Microsoft Teams Rooms の展開を計画する場合、必要なソフトウェアをインストールするために考慮すべきオプションがいくつかあります。 一般的なシナリオと手法を次の表に示します。 

| **シナリオ**            | **手法**         |
|-------------------------|-----------------------|   
|少数の Microsoft Teams Rooms デバイス (< 10) を展開する。 | Surface Pro ベースの Microsoft Teams Rooms を使用している場合は、「[デバイスごとのインストールのインストール手順l](console.md)」に従います。 [このプロセスを紹介する動画を参照してください。](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 統合ソリューションを使用している場合は、ベンダーのイメージを使用して展開し、必要に応じて設定を構成します。 |
| 1 つのベンダーから 10 台以上 50 台以下のデバイスを展開する。     | WIM ベースのイメージを作成し、[ガイダンスの手順 6 ](console.md)の後に一時停止して、複製配布技術で使用する配布イメージをキャプチャします。    |
| 50 台を超える Microsoft Teams Rooms デバイスを展開する。複数のベンダーからデバイスを展開する。または、展開の一部として組織固有のエージェントを要求する。 | [Microsoft Endpoint Configuration Manager](rooms-scale.md) などのタスク シーケンサー ベースのソフトウェアのビルドおよび配布プラットフォームを使用します。  |


**Pro のヒント** - 各Microsoft Teams Rooms は、ネットワーク上で有効な一意のコンピューター名が必要です。 多くの監視および警告システムでは、キー識別子としてコンピューター名が表示されるため、アクションが必要であるとフラグが付けられた Microsoft Teams Rooms をサポート担当者が簡単に見つけられるように、Microsoft Teams Rooms の展開用の命名規則を作成することが重要です。 例としては、MTR-*サイト*-*部屋の名前* (MTR-LON-CURIE) などのパターンが使用されることがあります。 

また、展開の一環として、Microsoft Teams Rooms のアプリケーションインストーラーによって作成される[ローカル アカウント](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts)を管理および構成するための戦略についても考慮する必要があります。

[Microsoft Azure Monitor](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) を使用して、Microsoft Teams Rooms の展開を監視し、可用性、ハードウェア/ソフトウェアのエラー、Microsoft Teams Roomsのアプリケーション バージョンなどの情報を報告する方法についてのガイダンスを提供します。 Microsoft Operations Management Suite を使用する場合は、ソフトウェアのインストール プロセスの一環として Operations Management Suite エージェントをインストールし、ワークスペースに対してワークスペース接続情報を構成する必要があります。 

また、Microsoft Teams Rooms をドメインに参加させるかどうかも検討してください。 ドメイン参加の利点については、「[Skype Room System のドメイン参加に関する考慮事項](domain-joining-considerations.md)」を参照してください。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>展開中に使用する Microsoft Teams Rooms のデバイス命名規則を決定します。</li><li>Microsoft Teams Rooms デバイスをドメインに追加するかどうか、およびローカル アカウントを管理および構成する方法を決定します。 </li><li>Operations Management Suite を使って Microsoft Teams Rooms の展開を監視するかどうかを決定します。</li><li>デバイスの展開の準備として、Microsoft Teams Rooms システムにソフトウェアとエージェントを展開するために使用する方法を決定します。 </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスの展開手法の計画を開始します。</li></ul>| 


### <a name="device-deployment"></a>デバイスの展開

Microsoft Teams Rooms ユニットにソフトウェアを展開した後、デバイスと割り当てられた周辺機器を会議室に発送するための計画を作成し、インストールと構成に進みます。 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>サイトごとの展開を管理するユーザーを決定します。</li><li> サイトに Microsoft Teams Rooms デバイスをインストールし、構成とテストに着手するリソースを特定します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスのテストを開始します。</li></ul>| 

_サンプル: 展開テーブル_

| **サイト**  | **部屋の名前** | **部屋の種類** | **Microsoft Teams Rooms システム**  | **周辺機器**  | **Microsoft Teams Rooms のコンピューター名**  | **Microsoft Teams Rooms のリソース アカウント**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| ロンドン HQ | Curie         | 中        |                                   |                  |                                          |                                             |
| シドニー HQ | Hill          | 大         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams Rooms のアプリケーションと周辺機器の構成 

各Microsoft Teams Rooms システムが物理的に展開され、サポートされている周辺機器が接続された後、Microsoft Teams Rooms のアプリケーションを構成して、作成済みの Microsoft Teams Roomsのリソース アカウントとパスワードを割り当てて、Microsoft Teams Rooms のユーザーが Microsoft Teams または Skype for Business、Exchange にサインインできるようにする必要があります。 ドキュメント内の他の場所にリンクされている認定 USB オーディオおよびビデオ周辺機器を活用することが重要です。 そうしないと、予期しない動作が発生する可能性があります。 

各Microsoft Teams Rooms システムは、手動で構成できます。 または、一元的に格納されている Microsoft Teams Rooms ごとの XML 構成ファイルを使用してアプリケーション設定を管理し、スタートアップ GPO スクリプトを利用して、Microsoft Teams Rooms システムが起動するたびに必要な構成を再適用することもできます。 

XML 構成ファイルの使用方法の詳細については、「[XML 構成ファイルを使用して Microsoft Teams Rooms のコンソール設定をリモートで管理する](xml-config-file.md)」を参照してください。 

[リモート PowerShell](rooms-operations.md#remote-management-using-powershell) を使用して、レポートのニーズに合わせて Microsoft Teams Rooms の構成を取得できます。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>各Microsoft Teams Rooms システムを手動で構成するか、一元管理された XML ファイル (Microsoft Teams Rooms デバイスごとに作成される 1 つのファイル) を使用するかを決定します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>リモート管理手法を定義します。</li></ul>| 

### <a name="testing"></a>テスト

Microsoft Teams Rooms システムが展開されたら、それをテストする必要があります。 [Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)に記載されている機能が、展開されたデバイスで機能していることを確認してください。 Microsoft Teams Rooms が Microsoft Operations Management Suite (使用されている場合) にログインしていることを、展開チームが検証することを強くお勧めします。 また、さまざまなテスト通話と会議を行って、品質をチェックすることも重要です。 詳細については、この「[便利な展開チェックリスト](console.md#microsoft-teams-rooms-deployment-checklist).」を参照してください。

一般的な Teams または Skype for Business のロールアウトの一環として、通話品質ダッシュボード (CQD) の構築ファイルを構成し、品質の傾向を監視し、Quality of Experience (QoE) レビューのプロセスに参加することをお勧めします。 詳細については、「[Teams の通話品質の向上と監視](../monitor-call-quality-qos.md)」を参照してください。 

### <a name="asset-management"></a>資産管理

展開の一環として、会議室名、Microsoft Teams Rooms のデバイス名、サインインした Microsoft Teams Rooms のリソース アカウント、割り当てられている周辺機器 (および使用している USB ポート) を使って、資産登録を更新します。 

_サンプル: 資産テーブル_

| **サイト**  | **部屋の名前** | **部屋の種類** | **Microsoft Teams Rooms のシリアル番号**  | **周辺機器/シリアル番号/ポート**  | **Microsoft Teams Rooms のコンピューター名**  | **Microsoft Teams Rooms のサービス アカウント**  | **展開日** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| ロンドン HQ | Curie         | 中        |                                          |                                          |                                          |                                            |                   |
| シドニー HQ | Hill          | 大         |                                          |                                          |                                          |                                            |                   |


