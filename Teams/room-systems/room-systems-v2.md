---
title: Microsoft Teams ルームの展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Microsoft Teams ルームの展開については、この記事を参照してください。
ms.openlocfilehash: c60d9a1ff3c00c62a14573b8b7e1d26b92e865d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305394"
---
# <a name="deployment-overview"></a>展開の概要

Microsoft Teams の会議室の展開は、基本的にフェーズに分けて分割します。

- 展開場所 (会議室) が展開の依存関係を満たしていることを確認する
- Microsoft Teams または Skype for Business および Exchange アカウントを作成し、それらをコンソールデバイスに割り当てる (「 [Microsoft Teams ルームのアカウントを構成](room-systems-v2-configure-accounts.md)する」を参照)
- Microsoft Teams のルームコンソールとして動作するように Microsoft Surface タブレットを再設定する (「 [Microsoft Teams ルーム本体を構成](console.md)する」または「 [microsoft teams ルーム](room-systems-scale.md)の展開ガイドを展開する」を参照してください)
- 省略システム用に Microsoft Operations Management Suite を設定する (「 [Azure モニターを使用して Microsoft Teams ルーム管理を展開](azure-monitor-deploy.md)する」を参照してください。
- 会議室で本体を設定し、必要な周辺機器を接続します (お使いのデバイスの OEM マニュアルを参照してください)。

最後のタスクには AV techs を使用できますが、組織の IT 部門は、プロセスの他の部分を行う必要があります。 


## <a name="site-readiness"></a>サイトの準備 

注文されたデバイスは組織に配信されますが、ネットワークと設備、および AV teams を使用して、展開の依存関係が満たされていることを確認し、各サイトと部屋の電力、ネットワーキング、表示の準備を行うことができます。 さらに、物理的なインストールの要件が満たされていることを確認してください。 物理的なインストールに関する考慮事項については、ベンダーのサイトにアクセスして、画面をインストールして接続するときに、AV チームのエクスペリエンスを活用してください。

これらの依存関係の詳細については、以下の計画ガイダンスのリンクを参照してください。

-   [ネットワークの状態をチェックする](srs-v2-prep.md#check-network-availability) 
-   [証明書](srs-v2-prep.md#certificates)
-   [プロキシ](srs-v2-prep.md#proxy)

**Pro ヒント**-プロキシサーバーを使用して Microsoft Teams または Skype For business Online へのアクセスを提供する場合は、まず[この記事を確認](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)してください。 プロキシサーバー経由の Skype for Business トラフィックについては、プロキシサーバーを完全にバイパスすることをお勧めします。 Skype for Business トラフィックは既に暗号化されているため、プロキシサーバーのセキュリティが強化されることはありません。 広い範囲に展開する場合は、「帯域幅計画の環境を[評価](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness)する」のガイダンスに従って、リアルタイムトラフィックに対するネットワークの適合性を評価することをお勧めします。 すべての帯域幅の計画については、 [Myadvisor ネットワークプランナー](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)を使用します。 ([ビデオ]、[画面の共有]、[オーディオ])、および microsoft teams の会議室の使用状況 (各サイトへの展開対象) に一致するユーザーを割り当てるには、Microsoft Teams の会議室のペルソナを作成することをお勧めします。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>サイトが Microsoft Teams のルームの重要な要件を満たしていることを確認します。</li><li>各サイトに十分な帯域幅が用意されていることを確認します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>まず、デバイスの展開と構成を計画します。</li></ul>| 

**Pro ヒント-** サイトごとの計画の観点から見ると、次のアセットが役に立つ場合があります。 Microsoft Teams のルームだけではなく、Skype for Business Online の完全なロールアウトでも利用できます。

-   [サイトのロールアウト/移行計画の配布ガイド](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_24)

-   [サイトのロールアウトと移行の計画-プレイブック](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_16)

    > [!NOTE]
    > プレイブックで、Microsoft Teams 室のデバイスの展開を計画している各サイトの "4.3 – > 会議室" のセクションにあるタスクを実行します。 これにより、プロセスの後半で一括アカウントプロビジョニングスクリプトを使用できるようになります。 

## <a name="service-readiness"></a>サービスの準備状況

Microsoft Teams ルームの展開を準備するには、次の主要なタスクを実行します。

-   Microsoft Teams のルームサービスアカウント機能を定義します。
-   Microsoft Teams のルームのコンピューターとサービスのアカウントを保持するために、組織単位と Active Directory グループを準備します。必要に応じて、グループポリシーオブジェクト (Gpo) を準備して、PowerShell のリモート処理を有効にします。

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Microsoft Teams のルームサービスアカウント機能の定義 

Microsoft Teams ルームの展開で有効にすることにしたコラボレーションシナリオに応じて、有効にする Microsoft Teams の各会議サービスアカウントに割り当てる機能を決定する必要があります。

| **シナリオ** | **説明** | **Microsoft Teams 室サービスアカウント機能** |
|---------- |------------- | --- |
| 対話型の会議            | 音声、ビデオ、画面共有を使用するMicrosoft Teams の会議リソースを作成する                     | Skype for Business で有効、Exchange (リソースメールボックス) を有効にします。 |
| ダイヤルイン会議            | ダイヤルイン会議の座標を使用して、Microsoft Teams の会議室コンソールから*直接*会議を開始できるようにする | 電話会議に対応                                          |
| 送信/受信 PSTN 通話 | Microsoft Teams のルームコンソールを有効にして、PSTN 通話の発信と受信を行う                                         | 電話システムに対応                                                |

Microsoft Teams のルームアカウントの詳細については、「 [Microsoft teams のルームのアカウントを構成する](room-systems-v2-configure-accounts.md)」を参照してください。


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>サポートするシナリオを決定し、Microsoft Teams の会議サービスアカウントのライセンス要件を特定します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>マシンアカウントとサービスアカウントをホストするための準備を行います。</li></ul>| 


_Microsoft Teams 室のサンプルサービスアカウントの計画テーブル_

| **サイト**  | **会議室名** | **会議室の種類** | **今後の room 機能**                                                 | **Microsoft Teams ルームのアカウント機能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 本部 | Curie         | 中        | 1画面、オーディオ、ビデオ plus プレゼンテーション <br>ダイヤルイン会議アクセス<br> PSTN アクセス  | Skype for Business で有効、Exchange (リソースメールボックス) を有効にします。 <br>電話会議に対応 <br>電話システムに対応 |
| シドニー | 丘          | さまざま         | 2画面、オーディオ、ビデオ、プレゼンテーション<br>ダイヤルイン会議アクセス<br> PSTN アクセス  | Skype for Business で有効、Exchange (リソースメールボックス) を有効にします。<br> 電話会議に対応 <br>電話システムに対応 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Microsoft Teams の会議室のコンピューターとサービスのアカウントをホストするための準備をする (オプション)

Microsoft Teams のルームのコンピューターおよびサービスアカウントを管理して報告できるようにするには、オンプレミスの Active Directory または Azure Active Directory (Azure AD) を準備します。 

オンプレミスの Active Directory または Azure AD グループを定義して、Microsoft teams のすべての会議サービス (ユーザー) アカウントを追加した後、Microsoft Teams のルーム展開で CSUserSession PowerShell コマンドレットを使用して利用状況レポートを作成します。 たとえば、SkypeRoomSystemsv2 という名前のグループを作成します。 


Microsoft Teams のすべてのコンピューターアカウント (ドメインに参加している場合)、および Microsoft Teams のすべてのユーザーアカウントを保持する組織単位を保持するには、オンプレミスの Active Directory または Azure AD 階層に1つの組織単位を定義します。 Microsoft Teams のルームマシンアカウントの組織単位を作成する場合は、継承を無効にして、ドメインに参加した Microsoft Teams ルームに適用するポリシーのみを適用することを検討してください。 

Microsoft Teams 室のコンピューターアカウントが含まれている組織単位に割り当てられたグループポリシーオブジェクトを作成します。 使用する操作 

-   [Power アカウントとローカルアカウントの設定](room-systems-v2-operations.md#configuring-group-policy-for-microsoft-teams-rooms)を行います。
-   Windows Update を有効にします。
-   PowerShell リモート処理を有効にします。 簡単なスクリプトを実行するように起動スクリプトを構成することができます。 PSRemoting-Force

PowerShell を使用して、構成情報の取得や設定など、多くのリモート管理操作を実行できます。 Powershell リモート処理を有効*にするに*は、powershell リモート管理を有効にする必要があります。また、展開プロセスの一部として、またはグループポリシーを使って構成する必要があります。 これらの機能の詳細と有効化については、「[メンテナンスと操作](room-systems-v2-operations.md#remote-management-using-powershell)」をご覧ください。 


## <a name="configuration-and-deployment"></a>構成と展開 

構成と展開の計画は、次の主要領域で構成されています。

-   アカウントプロビジョニング
-   デバイスソフトウェアのインストール
-   デバイスの展開
-   Microsoft Teams のルームアプリケーションと周辺機器構成
-    試験
-   資産管理

### <a name="account-provisioning"></a>アカウントプロビジョニング 

Microsoft Teams の各ルームデバイスには、専用の固有のリソースアカウントが必要です。このアカウントは、Microsoft Teams と Skype for Business および Exchange の両方で有効にする必要があります。 このアカウントには、Exchange でホストされている room メールボックスが必要です。また、Teams または Skype for Business の展開で会議室として有効にする必要があります。 Exchange 側では、デバイスが着信した会議出席依頼を自動的に受け入れるように、予定表の処理が構成されている必要があります。 これらのアカウントの作成方法の詳細については、「 [Microsoft Teams のルームのアカウントを構成する](room-systems-v2-configure-accounts.md)」を参照してください。 

**Pro ヒント**: これらのアカウントの表示名をわかりやすくわかりやすいものにします。 これらは、Microsoft Teams のルームシステムを検索して会議に追加するときにユーザーに表示される名前です。 組織によっては、*サイト*-*ルーム名*(*最大会議*室)-rs などの規則を使用しているため、たとえば、curie では、たとえば、London の12人の会議室で表示名が LON-curie (12) になります。 

組織に複数のプロビジョニングされたアカウントを必要とする多数の会議室がある場合、 [Skype Room Systems アカウントプロビジョニングスクリプト](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_4,5_2_0_5)を使用して、複数のサービスアカウントを自動で一括プロビジョニングすることができます。


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>Microsoft Teams のルームアカウントの名前付け規則を決定します。</li><li>個別のアカウントを作成するか、一括プロビジョニングスクリプトを使用するかを決定します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>まず、デバイスの展開を計画します。</li></ul>| 


### <a name="device-software-installation"></a>デバイスソフトウェアのインストール 

Microsoft Teams のルームの展開を計画するときに、必要なソフトウェアをインストールするために考慮する必要のあるオプションがいくつかあります。 一般的なシナリオとアプローチについては、次の表を参照してください。 

| **シナリオ**            | **やり**         |
|-------------------------|-----------------------|   
|少数の Microsoft Teams ルームデバイス (<10) を展開する。 | Surface Pro ベースの Microsoft Teams ルームを使用している場合は、[デバイスごとのインストールのインストール手順](console.md)に従ってください。 [このビデオでは、プロセスについて説明します。](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 統合ソリューションを使用している場合は、ベンダーのイメージを使用してを展開し、必要に応じて設定を構成します。 |
| 1つのベンダーから10台以上の50デバイスを展開する。     | WIM ベースの画像を作成し、[ガイダンスの手順 6](console.md)の後に一時停止し、複製配布技術で使用する配布イメージをキャプチャします。    |
| 50を超える Microsoft Teams を展開することで、複数のベンダーからデバイスを展開したり、展開の一部として組織固有のエージェントを要求したりすることができます。 | [System Center Configuration Manager](room-systems-scale.md)などの、タスク sequencer ベースのソフトウェアビルドと配布プラットフォームを使用します。  |

**Pro ヒント**-Microsoft Teams の各ルームには、ネットワーク上に有効で一意のコンピューター名が必要です。 多くの監視および警告システムでは、コンピューター名がキー識別子として表示されるため、サポート担当者は、フラグが付けられている Microsoft Teams の会議室を簡単に見つけることができるように、Microsoft Teams 室の展開に対して名前付け規則を開発することが重要です。操作が必要な場合。 例としては、MTR*サイト*-*ルーム名*のパターン (MTR-LON-curie) が使用されている場合があります。 

展開の一環として、Microsoft Teams のルームアプリケーションインストーラーによって作成される[ローカルアカウント](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts)を管理および構成するための戦略も検討する必要があります。

Microsoft [Azure モニター](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)を使用して microsoft Teams の会議室の展開を監視し、可用性、ハードウェア/ソフトウェアのエラー、Microsoft Teams の会議のバージョンに関するレポートを作成する方法についてのガイダンスを提供します。 Microsoft Operations Management Suite を使用する場合は、ソフトウェアのインストールプロセスの一環として Operations Management Suite エージェントをインストールして、ワークスペースの接続情報をワークスペースに対して構成する必要があります。 

追加で考慮する必要があるのは、Microsoft Teams のルームがドメインに参加しているかどうかです。 ドメイン参加の利点については、「 [Skype Room System ドメイン](domain-joining-considerations.md)への参加に関する考慮事項」をご覧ください。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>展開時に使用する Microsoft Teams 室のデバイスの名前付け規則を決定します。</li><li>Microsoft Teams 室のデバイスをドメインに参加するかどうか、およびローカルアカウントを管理して構成する方法を決定します。 </li><li>Operations Management Suite を使用して Microsoft Teams ルームの展開を監視するかどうかを決定します。</li><li>デバイスの展開の準備として、ソフトウェアとエージェントを Microsoft Teams のルームシステムに展開するために使用する方法を決定します。 </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイス展開のアプローチの計画を開始します。</li></ul>| 


### <a name="device-deployment"></a>デバイスの展開

Microsoft Teams のルームユニットにソフトウェアを展開した後、デバイスと割り当てられた周辺機器をルームに発送するためのプランを作成してから、インストールと構成に進みます。 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>サイトごとの展開を管理するユーザーを決定する。</li><li> サイトに Microsoft Teams の会議室デバイスをインストールし、構成とテストに着手するリソースを特定します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>デバイスのテストを開始します。</li></ul>| 

_展開テーブルの例_

| **サイト**  | **会議室名** | **会議室の種類** | **Microsoft Teams のルームシステム**  | **周辺機器**  | **Microsoft Teams 室のコンピューター名**  | **Microsoft Teams 会議室リソースアカウント**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 本部 | Curie         | 中        |                                   |                  |                                          |                                             |
| シドニー | 丘          | さまざま         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams のルームアプリケーションと周辺機器構成 

Microsoft Teams の各会議室のシステムが物理的に展開され、サポートされている周辺機器が接続された後、microsoft teams の会議アプリケーションを構成して、Microsoft Teams の会議室のリソースアカウントとパスワードを割り当てる必要があります。microsoft Teams のルームシステムで Microsoft Teams または Skype for Business および Exchange にサインインできるようにします。 ドキュメント内の他の場所にリンクされている認定 USB オーディオおよびビデオ周辺機器を活用することが重要です。 そうしないと、予期しない動作が発生する可能性があります。 

Microsoft Teams の各会議室システムを手動で構成することができます。 または、一元保存された、Microsoft Teams の会議室の XML 構成ファイルを使用して、アプリケーションの設定を管理し、Microsoft Teams の会議室のシステムが起動するたびに、必要な構成を再適用することができます。 

XML 構成ファイルの使用方法の詳細については、「 [Microsoft Teams のコンソール設定を xml 構成ファイルを使ってリモートで管理](xml-config-file.md)する」を参照してください。 

[リモート PowerShell](room-systems-v2-operations.md#remote-management-using-powershell)を使用して、レポートのニーズに合わせて Microsoft Teams 室の構成を取得できます。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>Microsoft Teams の各会議室システムを手動で構成するのか、一元管理の XML ファイルを使用するのか (Microsoft Teams のルームデバイスごとに1つ) を決定します。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>リモート管理アプローチを定義します。</li></ul>| 

### <a name="testing"></a> 試験

Microsoft Teams の会議室のシステムが展開されたら、それをテストする必要があります。 [Microsoft Teams のルーム](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)に表示される機能が、展開されたデバイスで機能していることを確認します。 Microsoft Teams のルームが Microsoft Operations Management Suite (使用されている場合) にログに記録されることを展開チームが確認することを強くお勧めします。 また、さまざまなテスト通話と会議を行って品質をチェックすることも重要です。 詳細については、この[便利な展開チェックリスト](console.md#microsoft-teams-rooms-deployment-checklist)を参照してください。

一般的なチームまたは Skype for Business のロールアウトの一環として、通話品質ダッシュボードの構築ファイル (CQD) を構成し、品質の傾向を監視して、エクスペリエンスレビュープロセスに参加することをお勧めします。 詳細については、「[エクスペリエンスの品質レビューガイド](https://aka.ms/qerguide)」を参照してください。 

**Pro ヒント**–テストマトリックスには、 [myadvisor](https://myadvisor.fasttrack.microsoft.com/)から利用可能な[テストマトリックス](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21)に、テストの一部として確認する必要がある Microsoft Teams 室のテストが多数含まれています。 

### <a name="asset-management"></a>資産管理 

展開の一環として、会議室名、Microsoft Teams 室のデバイス名、サインインされた Microsoft Teams 室リソースアカウント、および割り当てられている周辺機器 (および使用している USB ポート) を使って、資産登録を更新します。 

_サンプルアセットテーブル_

| **サイト**  | **会議室名** | **会議室の種類** | **Microsoft Teams ルームのシリアル番号**  | **周辺機器/シリアル nos./ポート**  | **Microsoft Teams 室のコンピューター名**  | **Microsoft Teams 室サービスアカウント**  | **展開日** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 本部 | Curie         | 中        |                                          |                                          |                                          |                                            |                   |
| シドニー | 丘          | さまざま         |                                          |                                          |                                          |                                            |                   |


