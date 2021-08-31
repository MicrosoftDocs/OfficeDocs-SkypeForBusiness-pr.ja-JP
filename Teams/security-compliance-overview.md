---
title: セキュリティとコンプライアンスの概要
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: プライバシーと暗号化Microsoft Teams監査とレポートなど、セキュリティとコンプライアンスの機能の概要。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61a6cba9ff05e6ee088c96231e8eb947e5d56fed
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733166"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams のセキュリティとコンプライアンス

> [!IMPORTANT]
> **COVID-19** の発生中に全員が自宅で作業している間にセキュリティを最適に確保する方法については、次の記事を参照してください。
>  - [Top 12 tasks for security teams to support working from home](/microsoft-365/security/top-security-tasks-for-remote-work) (在宅勤務をサポートするためにセキュリティ チームが行う 12 の主なタスク)
>  - [VPN スプリット トンネリングを使用してリモート ユーザーの Microsoft 365 または Office 365 の接続を最適化する](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 更新日: 2020 年 4 月 2 日: [Teams セキュリティ ガイド](teams-security-guide.md)


Microsoft Teamsは、Microsoft 365 および Office 365 ハイパースケールのエンタープライズ レベルのクラウド上に構築され、お客様が期待する高度なセキュリティとコンプライアンス機能を提供します。 セキュリティロードマップは、Microsoft 365またはOffice 365計画の詳細について説明します。 [](/microsoft-365/security/office-365-security/security-roadmap) Microsoft 365 または Office 365 でのコンプライアンスの計画の詳細については、「セキュリティとコンプライアンスの計画[」&できます](/microsoft-365/compliance/plan-for-security-and-compliance)。


この記事では、Teams 固有のセキュリティとコンプライアンスについて詳しく説明します。 セキュリティとコンプライアンスに関する以下の Microsoft Mechanics ビデオをお見逃しなく。

- [IT 担当者向けの Microsoft Teams の基礎](https://youtu.be/91lHNKVVvQ4) (12 分 42 秒)
- [Microsoft Teams でのセキュリティとコンプライアンスに関する扱い](https://www.youtube.com/watch?v=Km4T4hMM__k) (10 分 54 秒)

> [!IMPORTANT]
> お客様は、Microsoft 365またはOffice 365データを所有および制御します。 Microsoft は、お客様が登録したサービスを提供する以外の目的で、お客様のデータを使用することはありません。 サービス プロバイダーとして、広告のため、またはサービスに関連しない用途のために、メール、ドキュメント、チームをスキャンすることはありません。 Microsoft は、アップロードされたコンテンツにアクセスできません。 テナントOneDriveのSharePointとMicrosoft 365、顧客データはテナント内に残されます。 信頼およびセキュリティに関連する情報の詳細については、[Microsoft Trust Center](https://microsoft.com/trustcenter) で確認できます。 Teams は Microsoft Trust Center と同じガイダンスと原則に従っています。

## <a name="security"></a>セキュリティ

Teams では、チーム全体および組織全体の 2 要素認証、Active Directory を介したシングル サインオン、転送中のデータと保存データの暗号化が適用されます。 ファイルは SharePoint に格納され、SharePoint 暗号化が適用されます。 メモは OneNote に格納され、OneNote 暗号化が適用されます。 OneNote データはチームの SharePoint サイトに格納されます。 Wiki タブを使用してノートを取ることもできます。また、その内容もチームの SharePoint サイトに格納されます。

認証と Teams の詳細については、「[ID モデルと認証](identify-models-authentication.md)」を参照してください。先進認証については、「[先進認証のしくみ](sign-in-teams.md)」が特に役立ちます。

Teams SharePoint、OneNote、Exchange などと連携して機能する場合は、Microsoft 365 または Office 365 でセキュリティを管理する必要があります。 詳細については、セキュリティを強化[するために組織のMicrosoft 365構成Office 365を参照してください](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 現時点では、[プライベート チャネル](private-channels.md)でサポートされるセキュリティとコンプライアンス機能は制限されています。 プライベート チャネルにおけるすべてのセキュリティ機能とコンプライアンス機能のサポートは、近日中に行われる予定です。

### <a name="advanced-threat-protection-atp"></a>Advanced Threat Protection (ATP)

Advanced Threat Protection (ATP) は、Microsoft Teams および SharePoint および OneDrive、コンテンツ管理のために Teams と統合されたアプリケーションで使用できます。 ATP を使用すると、これらのアプリケーションのコンテンツが悪意のあるものであるかどうかを判断し、ユーザーのアクセスからこのコンテンツをブロックすることができます。

検出後の影響を受けるコンテンツの管理方法は、Microsoft 365 または Office 365 で選択した設定に基Office 365。 ATP の構成に関しては、すべてのアプリケーションを検討することを強く推奨します。さらに詳しい情報を読むには[、SharePoint、OneDrive、Microsoft Teams](/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)の ATP の使用を開始する方法に関する詳細情報が表示されます。

### <a name="safe-links"></a>安全なリンク

現時点では、Advanced Threat Protection (ATP) の安全なリンクは Microsoft Teams では利用できませんが、現在[](/microsoft-365/security/office-365-security/atp-safe-links-for-teams)はテクノロジ導入プログラム (TAP) を通じてパブリック プレビューに含まれるので、一般公開のリリース日は設定されていないのに、その時刻が来た時点でこの記事を更新します。 一方、リンクの詳細Microsoft 365または Office 365 セーフについては、「ATP セーフ リンク」[を参照してください](/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)。 ATP セーフリンクは[、ATP プラン 1 と ATP プラン 2 の両方で利用できます](/microsoft-365/security/office-365-security/office-365-atp)。

### <a name="safe-attachments"></a>セーフ添付ファイル

セーフは、悪意のある添付ファイルを確認して検出することで、ユーザーのセキュリティを強化するように設計された機能です。 グローバル管理者またはセキュリティ管理者は、[](/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies)これらの疑いのある悪意のある添付ファイルを処理するポリシーを作成して、ユーザーへの送信、クリック、操作を防止します。 セーフの保護は SharePoint、OneDrive、Microsoft Teams で使用できます。Microsoft 365 または Office 365 [Advanced Threat Protection プラン 1](/microsoft-365/security/office-365-security/office-365-atp)と 2 にはこの機能があります。 詳細については、「添付ファイルセーフMicrosoft Defender の添付ファイル」で組織を保護する方法セーフを[参照](/microsoft-365/security/office-365-security/atp-safe-attachments)Office 365。

### <a name="secure-score"></a>セキュリティ スコア

Microsoft Secure Score は組織のセキュリティ体制の測定で、より多くの改善アクションが実行されたことを示す数値が高くなります。 これは、セキュリティ センター の[Microsoft 365にあります](https://security.microsoft.com/securescore)。 セキュリティ スコアの推奨事項に従って、組織を脅威から保護できます。 Microsoft 365 セキュリティ センターの一元的なダッシュボードから、組織は ID、アプリ、およびデバイスのセキュリティを監視Microsoft 365作業できます。 Microsoft Teamsスコアに関する推奨事項が表示され、管理者はプラットフォーム上でセキュリティの姿勢を監視する必要があります。

セキュリティ スコアは、組織に役立ちます。
- 組織のセキュリティ体制の現在の状態を報告します。
- 検出可能性、可視性、ガイダンス、および制御を提供することで、セキュリティ対策を強化します。
- ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。


### <a name="how-conditional-access-policies-work-for-teams"></a>Teams での条件付きアクセス ポリシーの仕組み

Microsoft Teams、Exchange Online、SharePoint、Skype for Business Online は、会議、予定表、相互運用チャット、ファイル共有など、主要な生産性シナリオに大きく依存しています。 これらのクラウド アプリ向けに設定された条件付きアクセス ポリシーは、任意のクライアントの Microsoft Teams にユーザーが直接サインインするときに適用されます。

Microsoft Teams は、Azure Active Directory の条件付きアクセス ポリシーのクラウド アプリとして個別にサポートされています。 Microsoft Teams クラウド アプリ向けに設定されている条件付きアクセス ポリシーは、ユーザーがサインインするときに Microsoft Teams に適用されます。 ただし、Exchange Online や SharePoint などの他のアプリに対する適切なポリシーがない場合でも、ユーザーはそれらのリソースに直接アクセスできる場合があります。 Azure Portal での条件付きアクセス ポリシーの設定の詳細については、「クイック スタート」をAzure Active Directory[してください](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)。

Windows および Mac 版の Microsoft Teams デスクトップ クライアントは先進認証をサポートしています。 先進認証により、Azure Active Directory 認証ライブラリ (ADAL) に基づくサインインが、あらゆるプラットフォームの Microsoft Office クライアント アプリケーションに導入されています。

Microsoft Teams デスクトップ アプリケーションは、AppLocker をサポートしています。  AppLocker の前提条件の詳細については、「[AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker) を使用するための要件」をご覧ください。

## <a name="compliance"></a>コンプライアンス

Teams には、チャネル、チャット、添付ファイルの通信コンプライアンス、保持ポリシー、データ損失防止 (DLP)、チャネルの電子情報開示と法的ホールド、チャットとファイル、監査ログ検索、Microsoft Intune を使用したモバイル アプリケーション管理など、コンプライアンス領域に役立つさまざまな情報があります。 以下のすべてのトピックに関する情報が提供されています。これらの設定を管理するには、Microsoft 365 コンプライアンス センター[にアクセス](https://compliance.microsoft.com)してください。

### <a name="information-barriers"></a>情報バリア

情報バリアとは、Teams 管理者が、ユーザーやグループが連絡を取り合う必要がない場合 (ビジネス上の必要がない場合、またはブロックする規制上の理由がある場合)、ルックアップや電子情報開示などのポリシーを設定するポリシー (以下で説明) を行うポリシーです。 これらのポリシーは、1 対 1 のチャット、グループ チャット、またはチーム レベルのユーザーに影響を与える可能性があります。 Information Barrier 機能はパブリック クラウドで利用できます。2021 年 1 月から、この機能はクラウドの GCCされています。

このトピックの詳細については、「情報バリア」を参照[Microsoft Teams。](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>通信コンプライアンス

Microsoft 365 のコミュニケーション コンプライアンスを使用すると、ユーザーをスコープ内ポリシーに追加できます。このポリシーは、Microsoft Teams 通信で不快な言語、機密情報、および内部および規制基準に関連する情報を調べるために構成できます。 パブリックおよびプライベート Teams チャネル、個々のチャット、添付ファイルの両方のチャット通信と関連する添付ファイルをスキャンして、組織内の通信リスクを最小限に抑えるのに役立ちます。 不適切な通信 Teamsの検出、キャプチャ、アクションの実行に役立つポリシーを構成する方法の詳細については、「Microsoft 365 での通信コンプライアンス」を参照[してください](/microsoft-365/compliance/communication-compliance)。

### <a name="retention-policies"></a>アイテム保持ポリシー

Microsoft Teams のアイテム保持ポリシーを使用すると、規制、法的、ビジネス、その他の理由で、組織が所有する必要がある重要なデータを保持することができます。また、保持する必要がないコンテンツや通信を削除することもできます。 アイテム保持ポリシーを使用して、データを一定期間保管してから削除することもできます。 詳細については、 のアイテム保持[ポリシーに関するMicrosoft Teams。](retention-policies.md)

## <a name="sensitivity-labels"></a>秘密度ラベル

機密 [ラベルを適用して](/microsoft-365/compliance/sensitivity-labels) 、チーム内での共同作業中に作成された機密性の高い組織のコンテンツへのアクセスを保護し、規制します。 たとえば、チームのプライバシー (パブリックまたはプライベート) を構成し、ゲスト アクセスと外部共有を制御し、非管理対象デバイスからのアクセスを管理するラベルを適用します。 詳細については、 の[「感度ラベル」をMicrosoft Teams。](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>データ損失防止 (DLP)

Microsoft Teams のデータ損失防止 (DLP) と、Microsoft 365 または Office 365 の大規模な DLP ストーリーは、機密性の高いドキュメントとデータの保護に関するビジネスの準備を中心に展開されます。 メッセージやドキュメントの機密情報に関する懸念がある場合、DLP ポリシーを使用すれば、ユーザーがその機密データを不適切な人々と共有しないようにすることができます。

Teams でのデータ損失防止の詳細については、「[Microsoft Teams 向け DLP](/microsoft-365/compliance/dlp-microsoft-teams)」を参照してください。 O365 DLP に関する問題に関する良い記事は、 [データ損失防止の概要です](/microsoft-365/compliance/data-loss-prevention-policies)。

### <a name="ediscovery"></a>電子情報開示

電子情報開示 (eDiscovery) とは、訴訟または調査における開示要求に対応するための電子保持情報 (ESI) の電子的な特定、収集、生成です。 これらの機能には、Teams データのケース管理、保持、検索、分析、エクスポートが含まれています。 チャット、メッセージング、ファイル、会議と通話の概要も含まれています。 Teams の会議と通話では、会議と通話で発生したイベントの概要が作成され、電子情報開示で利用可能な状態になります。

セキュリティ センターとコンプライアンス センターで Microsoft 365 または Office 365 電子情報開示を実行し、Teams コンテンツのコンプライアンス コンテンツ検索を実行する方法の詳細については、次のリンクを参照してください。

 - [電子情報開示](/microsoft-365/compliance/manage-legal-investigations)

 - [コンテンツ検索](/microsoft-365/compliance/search-for-content)

[ゲスト間のチャットの電子情報開示](eDiscovery-investigation.md)についての Teams 固有の記事もあります。

顧客は、要件に従って電子[情報開示Advanced eDiscovery](/microsoft-365/compliance/office-365-advanced-ediscovery)を利用できます。 次の表で、これらの 2 つの違いについて説明します。

|&nbsp; |電子情報開示  |Advanced eDiscovery  |
|---------|---------|---------|
|ケース管理     |X        |X         |
|アクセス制御  |X         |X         |
|コンテンツ検索     |X         | X        |
|保持   |X         | X        |
|エクスポート     |X         |X         |
|重複検出     |-         |X         |
|機会学習を使用した関連性検索    |-         |X         |
|非構造化データ分析      |-         |X         |

### <a name="legal-hold"></a>"Legal Hold/法的情報保留"

訴訟中、裁判での証拠として使用できるように、ユーザー (管理人) または Teams に関連付けられているすべてのデータを変更不可として保持する必要がある場合があります。 この要求に対応するには、ユーザー (ユーザー メールボックス) または Teams を訴訟ホールドにします。 チームの訴訟ホールドの場合、チームのメールボックスを次のホールドに含めることができます。

- インプレース ホールド (対象のクエリまたはフィルター処理されたコンテンツを使用した、メールボックスまたはサイト コレクションのサブセットがホールドになります)、あるいは
- 訴訟ホールド (メールボックスまたはサイト コレクション全体がホールドになります)。

どちらの場合でも、ホールドに設定されれば、エンド ユーザーがグループのメールボックス内のチャネル メッセージを削除または編集しても、そのコンテンツの不変のコピーが維持され、電子情報開示の検索で利用できるようになります。 訴訟ホールドは、通常、電子情報開示ケースのコンテキスト内で適用されます。

アイテム保持[ポリシーの概要に関するページ](/microsoft-365/compliance/retention-policies)を参照して、保持と保持の詳細については、Microsoft 365 コンプライアンス センター。 法的ホールドTeamsに関する詳細については、詳細を確認するために、Microsoft Teams[](legal-hold.md)ユーザーまたはチームを法的ホールドに配置する方法も用意しています。

### <a name="compliance-content-search"></a>コンプライアンスのコンテンツ検索

コンテンツ検索では、豊富なフィルター機能を活用してすべてのチーム データを検索することができます。 結果として得られるデータは、特定のコンテナにエクスポートでき、コンプライアンスおよび訴訟のサポートとして用いることができます。 この操作は電子情報開示ケースの有無に関わらず実行できます。 これにより、コンプライアンス管理者は、すべてのユーザーにわたる Teams データを収集し、そのデータをレビューして、さらに処理するためにエクスポートできるようになります。 Microsoft Teams および[](/microsoft-365/compliance/content-search)Microsoft Teams 内の他の Microsoft 365 または Office 365 コンテンツのコンプライアンス コンテンツ検索を実行する方法の詳細については、「コンテンツ検索」を参照Microsoft 365 コンプライアンス センター。

> [!TIP]
> コンテンツ検索を使用すると、チャット、チャネル メッセージ、会議、通話など、Microsoft Teams のみのコンテンツへの絞り込みを必要に応じて行うことができます。

コンテンツ検索の構成に関するTeams詳細については、 のコンテンツ検索に関するページ[をMicrosoft Teams。](content-search.md)

### <a name="auditing-and-reporting"></a>監査と報告

監査ログ検索は Microsoft 365 コンプライアンス センター に接続され、無制限の監査タイムラインで管理者が使用および調査するワークロード固有または汎用イベント セットのエクスポートを許可することで、アラートを設定したり、監査イベントに関するレポートを作成したりすることができます。 Microsoft 365 コンプライアンス センター 内のすべての監査ログ データのアラートを設定し、このデータをフィルター処理してエクスポートして詳細な分析を行います。 監査ログまたは[監査ログの監査ログ](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)検索を実行する方法の詳細については、「監査ログを検索するMicrosoft 365参照Office 365。 Microsoft 365 コンプライアンス センター で Microsoft Teams イベントを検索する方法の詳細については、「Teams で監査を有効[](audit-log-events.md)にする」を参照してください。

## <a name="customer-key"></a>顧客キー

Microsoft 365コンテンツのサービス暗号化に加え、暗号化の追加レイヤーが提供されます。 指定したキーを使用して、顧客キーは複数の異なる種類のデータを暗号化Microsoft Teams。 アプリケーション レベルで顧客キーを使用すると、顧客キーは Teams Online に格納されているSharePoint暗号化します。 詳細については、「顧客キーを [使用したサービス暗号化」を参照してください](/microsoft-365/compliance/customer-key-overview)。 

顧客キーをテナント レベルで使用すると、顧客キーは次の情報を暗号化します。
- Teams (1 対 1 のチャット、グループ チャット、会議チャット、チャネル会話)
- Teams メッセージ (画像、コード スニペット、ビデオ、Wiki 画像)
- Teamsストレージに保存されている通話と会議のTeams記録
- Teams通知を送信する
- Teamsによるチャットの提案Cortana
- Teams状態メッセージの詳細については、テナント レベルでの[Microsoft 365](/microsoft-365/compliance/customer-key-tenant-level)のカスタマー キーの概要に関するページを参照し、パブリック プレビューで現在の Microsoft Teams のカスタマー キー のサポートに関する Microsoft Teams ブログを参照[してください。](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893) テナント レベルで顧客Microsoft Information Protectionが含まれている Microsoft Information Protection リリースの詳細については、機密データを知り、保護するための新しい Microsoft Information Protection 機能の発表に関する記事[を参照してください](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)。

## <a name="privacy"></a>プライバシー

Microsoft では、データの保護が最優先事項です。 プライバシーに関するプラクティスについては、以下を参照してください。  

- [Microsoft のプライバシー](https://www.microsoft.com/trust-center/privacy)
- [プライバシーとセキュリティに関する当社の取り組Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [IT プロフェッショナル向け: Microsoft Teams のプライバシーとセキュリティ](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>情報保護アーキテクチャ

次の図は、Teams のファイルやメッセージに対応する、Exchange と SharePoint の両方への Teams データの取り込みフローを示しています。

> [!div class="mx-imgBorder"]
> ![データをデータにTeamsするワークフロー Exchange図SharePoint。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

次の図は、Teams 会議および通話データの Exchange への取り込みフローを示しています。

> [!div class="mx-imgBorder"]
> ![会議を開始し、Teamsを呼び出すワークフローのExchange。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Teams のコンテンツの開示には最大で 24 時間の遅延が発生する場合があります。

## <a name="licensing"></a>ライセンス

情報保護機能に関しては、Microsoft 365 サブスクリプション、Office 365 サブスクリプション、および関連付けられているスタンドアロン ライセンスによって、使用可能な機能セットが決定されます。

セキュリティとコンプライアンスの機能を実装するために必要なライセンスの決定については、セキュリティとコンプライアンスの[](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)機能に関するライセンス要件を確認してください。

> [!NOTE]
> コンテンツ検索と電子情報開示を機能させるために、セキュリティ/コンプライアンス センター内で有効にする操作は不要です。

## <a name="location-of-data-in-teams"></a>Teams のデータの場所

Teams のデータはご利用の Microsoft 365 または Office 365 の組織に関連付けられている地理的領域内に存在します。 現在サポートされている地域を確認するには、「[Microsoft Teams のデータの場所](location-of-data-in-teams.md)」を参照してください。

ご利用のテナントのデータがどの地域で格納されるかを確認するには、[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home)  >  **[設定]**  >  **[組織プロファイル]** に移動してください。 下にスクロールして **[データの場所]** に移動します。

> [!div class="mx-imgBorder"]
> ![管理センターのデータの場所Teamsのスクリーンショット。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>コンプライアンス基準

Teamsでは[、ISO 27001、ISO](/microsoft-365/compliance/offering-iso-27001) [27018、SSAE18](/microsoft-365/compliance/offering-iso-27018) [SOC 1 および SOC 2、HIPAA、EU](/microsoft-365/compliance/offering-soc)モデル条項[(EUMC)](/microsoft-365/compliance/offering-eu-model-clauses)の標準を使用します。 [](/microsoft-365/compliance/offering-hipaa-hitech) Microsoft のコンプライアンス フレームワークでは、アプリケーションとサービスMicrosoft 365およびOffice 365 4 つのカテゴリに分類されます。 各カテゴリは、Microsoft 365 または Office 365 サービス、または関連する Microsoft サービスをそのカテゴリに一覧表示するために満たされる必要がある特定のコンプライアンスコミットメントによって定義されます。

詳細については、「データ保護リソース [」を参照してください](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)。 Teams Cloud Security Alliance のコンプライアンスもサポートしています。

## <a name="related-topics"></a>関連項目

[Microsoft 365セキュリティ](/microsoft-365/security/)

[Microsoft 365コンプライアンス](/microsoft-365/compliance/)

[Microsoft のコンプライアンスオファリング](/microsoft-365/compliance/offering-home)
