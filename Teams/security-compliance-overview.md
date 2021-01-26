---
title: セキュリティとコンプライアンスの概要
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: プライバシーと暗号化、監査とレポートなど、Microsoft Teams のセキュリティとコンプライアンス機能の概要。
localization_priority: Normal
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
ms.openlocfilehash: cfbf0ededcb1a5f3037bfb896242902daaa2a79b
ms.sourcegitcommit: d6e97621b1bfe9c3fbd8bc41b30a94bafd17b28f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49973081"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams のセキュリティとコンプライアンス

> [!IMPORTANT]
> **COVID-19** の発生中に全員が在宅勤務中にセキュリティを最適に確保する方法については、次の記事を参照してください。
>  - [Top 12 tasks for security teams to support working from home](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work) (在宅勤務をサポートするためにセキュリティ チームが行う 12 の主なタスク)
>  - [VPN スプリット トンネリングを使用してリモート ユーザーの Microsoft 365 または Office 365 の接続を最適化する](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 更新日: 2020 年 4 月 2 日: [Teams のセキュリティ ガイド](teams-security-guide.md)


Microsoft Teams は、Microsoft 365 および Office 365 ハイパースケールのエンタープライズ レベルのクラウド上に構築され、お客様が期待する高度なセキュリティとコンプライアンス機能を提供します。 Microsoft 365 または Office 365 でのセキュリティ計画の詳細については、[](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)最初にセキュリティ ロードマップを作成してください。 Microsoft 365 または Office 365 でのコンプライアンスの計画の詳細については、セキュリティコンプライアンスの計画を& [できます](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)。


この記事では、Teams 固有のセキュリティとコンプライアンスについて詳しく説明します。 セキュリティとコンプライアンスに関する以下の Microsoft Mechanics ビデオをお見逃しなく。

- [IT 担当者向けの Microsoft Teams の基礎](https://youtu.be/91lHNKVVvQ4) (12 分 42 秒)
- [Microsoft Teams でのセキュリティとコンプライアンスに関する扱い](https://www.youtube.com/watch?v=Km4T4hMM__k) (10 分 54 秒)

> [!IMPORTANT]
> Microsoft 365 または Office 365 のお客様は、データを所有し、管理します。 Microsoft は、お客様が登録したサービスを提供する以外の目的で、お客様のデータを使用することはありません。 サービス プロバイダーとして、広告のため、またはサービスに関連しない用途のために、メール、ドキュメント、チームをスキャンすることはありません。 Microsoft はアップロードされたコンテンツにアクセスできません。 Microsoft 365 の OneDrive や SharePoint と同様に、顧客データはテナント内に残されます。 信頼およびセキュリティに関連する情報の詳細については、[Microsoft Trust Center](https://microsoft.com/trustcenter) で確認できます。 Teams は Microsoft Trust Center と同じガイダンスと原則に従っています。

## <a name="security"></a>セキュリティ

Teams では、チーム全体および組織全体の 2 要素認証、Active Directory を介したシングル サインオン、転送中のデータと保存データの暗号化が適用されます。 ファイルは SharePoint に格納され、SharePoint 暗号化が適用されます。 メモは OneNote に格納され、OneNote 暗号化が適用されます。 OneNote データはチームの SharePoint サイトに格納されます。 Wiki タブを使用してノートを取ることもできます。また、その内容もチームの SharePoint サイトに格納されます。

認証と Teams の詳細については、「[ID モデルと認証](identify-models-authentication.md)」を参照してください。先進認証については、「[先進認証のしくみ](sign-in-teams.md)」が特に役立ちます。

Teams は SharePoint、OneNote、Exchange などと連携して動作しますので、Microsoft 365 または Office 365 全体のセキュリティの管理に快適に取り組む必要があります。 詳細については、セキュリティを強化するために [Microsoft 365 または Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)組織を構成する方法を参照してください。

> [!NOTE]
> 現時点では、[プライベート チャネル](private-channels.md)でサポートされるセキュリティとコンプライアンス機能は制限されています。 プライベート チャネルにおけるすべてのセキュリティ機能とコンプライアンス機能のサポートは、近日中に行われる予定です。

### <a name="advanced-threat-protection-atp"></a>Advanced Threat Protection (ATP)

Advanced Threat protection (ATP) は、Microsoft Teams および SharePoint および OneDrive (コンテンツ管理用の Teams と統合されるアプリケーション) で利用できます。 ATP を使用すると、これらのアプリケーションのコンテンツが悪意のあるものであるかどうかを判断し、ユーザーのアクセスからこのコンテンツをブロックすることができます。

検出後の影響を受けるコンテンツの管理方法は、Microsoft 365 または Office 365 で選択した設定に基きます。 ATP の構成に関しては、すべてのアプリケーションを検討することを強く推奨し、詳細については [、SharePoint、OneDrive、Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) の ATP の使用を開始する方法の詳細について説明します。

### <a name="safe-links"></a>安全なリンク

現時点では、Advanced Threat Protection (ATP) の安全なリンクは Microsoft Teams では利用[](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide)できませんが、現在はテクノロジ導入プログラム (TAP) を通じてパブリック プレビューに表示されます。一般提供のリリース日が設定されていない間は、この時点でこの記事を更新します。 一方、Microsoft 365 または Office 365 の安全なリンクについては、ATP の安全なリンク [を確認してください](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)。 ATP の安全なリンクは [、ATP プラン 1 と ATP プラン 2 の両方で利用できます](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)。

### <a name="safe-attachments"></a>安全な添付ファイル

安全な添付ファイルは、悪意のある添付ファイルを確認し、検出して、ユーザーのセキュリティを強化するように設計された機能です。 グローバル管理者またはセキュリティ管理者は、[](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide)これらの悪意のある添付ファイルがユーザーに送信、クリック、操作されるのを防ぐためのポリシーを作成します。 SharePoint、OneDrive、Microsoft Teams では安全な添付ファイル保護を利用できます。Microsoft 365 または Office 365 [Advanced Threat Protection プラン 1](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) と 2 には、この機能があります。 Microsoft [Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)の安全な添付ファイルで、安全な添付ファイルを使用して組織を保護する方法について説明します。

### <a name="secure-score"></a>Secure Score

Microsoft Secure Score は、組織のセキュリティの姿勢を表す測定値で、より多くの改善アクションが実行されたことを示す数値が高くなります。 これは [、Microsoft 365](https://security.microsoft.com/securescore)セキュリティ センターにあります。 セキュリティ スコアの推奨事項に従って、脅威から組織を保護できます。 Microsoft 365 セキュリティ センターの一元管理ダッシュボードから、組織は Microsoft 365 ID、アプリ、デバイスのセキュリティを監視し、作業できます。 Microsoft Teams にはセキュリティ スコアに関する推奨事項が追加されました。管理者はプラットフォーム上でセキュリティに関する姿勢を監視する必要があります。

セキュリティ スコアは、組織を支援します。
- 組織のセキュリティの姿勢の現在の状態を報告します。
- 見やすさ、可視性、ガイダンス、制御を提供することで、セキュリティの姿勢を改善します。
- ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。


### <a name="how-conditional-access-policies-work-for-teams"></a>Teams での条件付きアクセス ポリシーの仕組み

Microsoft Teams は、会議、予定表、相互運用チャット、ファイル共有など、主要な生産性シナリオについて Exchange Online、SharePoint、Skype for Business Online に大きく依存しています。 これらのクラウド アプリ向けに設定された条件付きアクセス ポリシーは、任意のクライアントの Microsoft Teams にユーザーが直接サインインするときに適用されます。

Microsoft Teams は、Azure Active Directory の条件付きアクセス ポリシーのクラウド アプリとして個別にサポートされています。 Microsoft Teams クラウド アプリ向けに設定されている条件付きアクセス ポリシーは、ユーザーがサインインするときに Microsoft Teams に適用されます。 ただし、Exchange Online や SharePoint などの他のアプリの適切なポリシーがない場合でも、ユーザーは引き続きこれらのリソースに直接アクセスできます。 Azure Portal で条件付きアクセス ポリシーを設定する方法の詳細については、Azure Active Directory クイック [スタートを参照してください](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)。

Windows および Mac 版の Microsoft Teams デスクトップ クライアントは先進認証をサポートしています。 先進認証により、Azure Active Directory 認証ライブラリ (ADAL) に基づくサインインが、あらゆるプラットフォームの Microsoft Office クライアント アプリケーションに導入されています。

Microsoft Teams デスクトップ アプリケーションは、AppLocker をサポートしています。  AppLocker の前提条件の詳細については、「[AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker) を使用するための要件」をご覧ください。

## <a name="compliance"></a>コンプライアンス

Teams には、チャネル、チャット、添付ファイルの通信コンプライアンス、アイテム保持ポリシー、データ損失防止 (DLP)、チャネル、チャットとファイルの電子情報開示と法的ホールド、監査ログの検索、Microsoft Intune でのモバイル アプリケーション管理など、コンプライアンス領域に役立つさまざまな情報があります。 以下のすべてのトピックに関する情報を提供しています。これらの設定を管理するには [、Microsoft 365](https://compliance.microsoft.com) コンプライアンス センターにアクセスしてください。

### <a name="information-barriers"></a>情報バリア

情報バリアとは、Teams 管理者がユーザーやグループが通信し合う必要がない場合 (ビジネス上の必要がない場合や、ブロックする規制上の理由がある場合) などの操作を行うポリシーです。また、ルックアップや電子情報開示などのポリシーを設定することもできます (以下で説明します)。 これらのポリシーは、1 対 1 のチャット、グループ チャット、またはチーム レベルのユーザーに影響を与える可能性があります。

このトピックの詳細については [、Microsoft Teams の情報バリアに関するページを参照してください](information-barriers-in-teams.md)。

### <a name="communication-compliance"></a>コミュニケーションのコンプライアンス

Microsoft 365 のコミュニケーション コンプライアンスを使用すると、ユーザーを範囲内のポリシーに追加して、Microsoft Teams の通信を調べて、不快な言葉、機密情報、内部および規制基準に関連する情報を確認できます。 パブリックとプライベートの Teams チャネル、個々のチャット、添付ファイルの両方のチャット通信および関連する添付ファイルをスキャンして、組織内のコミュニケーションのリスクを最小限に抑えるのに役立ちます。 不適切な Teams 通信の検出、キャプチャ、アクションの実行に役立つポリシーを構成する方法の詳細については [、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)のコミュニケーション コンプライアンスを参照してください。

### <a name="retention-policies"></a>アイテム保持ポリシー

Microsoft Teams のアイテム保持ポリシーを使用すると、規制、法的、ビジネス、その他の理由で、組織が所有する必要がある重要なデータを保持することができます。また、保持する必要がないコンテンツや通信を削除することもできます。 アイテム保持ポリシーを使用して、データを一定期間保管してから削除することもできます。 詳細については [、Microsoft Teams のアイテム保持ポリシーを参照してください](retention-policies.md)。

## <a name="sensitivity-labels"></a>感度ラベル

機密 [ラベルを適用して、](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) チーム内での共同作業中に作成された機密性の高い組織コンテンツへのアクセスを保護し、規制します。 たとえば、チームのプライバシー (パブリックまたはプライベート) を構成するラベルを適用し、ゲスト アクセスと外部共有を制御し、非管理対象デバイスからのアクセスを管理します。 詳細については、Microsoft Teams の [[感度] ラベルを参照してください](sensitivity-labels.md)。

### <a name="data-loss-prevention-dlp"></a>データ損失防止 (DLP)

Microsoft Teams のデータ損失防止 (DLP) と、Microsoft 365 または Office 365 の大規模な DLP の話は、機密性の高いドキュメントとデータを保護する場合のビジネスの準備を中心に展開します。 メッセージやドキュメントの機密情報に関する懸念がある場合、DLP ポリシーを使用すれば、ユーザーがその機密データを不適切な人々と共有しないようにすることができます。

Teams でのデータ損失防止の詳細については、「[Microsoft Teams 向け DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)」を参照してください。 O365 DLP の問題に関する良い記事は、 [データ損失防止の概要です](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。

### <a name="ediscovery"></a>電子情報開示

電子情報開示 (eDiscovery) とは、訴訟または調査における開示要求に対応するための電子保持情報 (ESI) の電子的な特定、収集、生成です。 これらの機能には、Teams データのケース管理、保持、検索、分析、エクスポートが含まれています。 チャット、メッセージング、ファイル、会議と通話の概要も含まれています。 Teams の会議と通話では、会議と通話で発生したイベントの概要が作成され、電子情報開示で利用可能な状態になります。

セキュリティ センターとコンプライアンス センターで Microsoft 365 または Office 365 電子情報開示を実行し、Teams コンテンツのコンプライアンス コンテンツ検索を実行する方法の詳細については、以下のリンクを参照してください。

 - [電子情報開示](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

 - [コンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

[ゲスト間のチャットの電子情報開示](eDiscovery-investigation.md)についての Teams 固有の記事もあります。

お客様は、要件に応じて [電子情報開示または Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) を利用できます。 次の表で、これらの 2 つの違いについて説明します。

| |電子情報開示  |Advanced eDiscovery  |
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

Microsoft [](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 365 コンプライアンス センターでの保持と保持の詳細については、アイテム保持ポリシーの概要を参照してください。 Teams 固有の法的ホールドに関するその他の情報については [、Microsoft Teams](legal-hold.md) のユーザーまたはチームを法的な保留にし、詳細を確認します。

### <a name="compliance-content-search"></a>コンプライアンスのコンテンツ検索

コンテンツ検索では、豊富なフィルター機能を活用してすべてのチーム データを検索することができます。 結果として得られるデータは、特定のコンテナにエクスポートでき、コンプライアンスおよび訴訟のサポートとして用いることができます。 この操作は電子情報開示ケースの有無に関わらず実行できます。 これにより、コンプライアンス管理者は、すべてのユーザーにわたる Teams データを収集し、そのデータをレビューして、さらに処理するためにエクスポートできるようになります。 Microsoft 365 コンプライアンス センターで Microsoft Teams および他の Microsoft 365 または Office 365 コンテンツのコンプライアンス コンテンツ検索を実行する方法の詳細については、コンテンツ検索を参照してください。 [](https://docs.microsoft.com/microsoft-365/compliance/content-search)

> [!TIP]
> コンテンツ検索を使用すると、チャット、チャネル メッセージ、会議、通話など、Microsoft Teams のみのコンテンツへの絞り込みを必要に応じて行うことができます。

コンテンツ検索の構成に関する Teams 固有の情報をさらに表示する場合は [、Microsoft Teams のコンテンツ検索を確認します](content-search.md)。

### <a name="auditing-and-reporting"></a>監査と報告

監査ログの検索は、Microsoft 365 コンプライアンス センターに接続され、無制限の監査タイムラインで管理者が使用および調査するためにワークロード固有または汎用のイベント セットをエクスポートできるようにして、アラートを設定したり、監査イベントに関するレポートを作成することができます。 Microsoft 365 コンプライアンス センター内のすべての監査ログ データに対する警告を設定し、さらに分析のためにこのデータをフィルター処理およびエクスポートすることができます。 Microsoft 365 または Office 365 の監査ログ検索を実行する方法の詳細については、「監査ログを検索する」を参照してください。 [](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) Microsoft 365 コンプライアンス センターで Microsoft Teams イベントを検索する方法の詳細については [、Teams](audit-log-events.md) で監査を有効にすることもできます。

## <a name="privacy"></a>プライバシー

Microsoft では、データの保護が最優先事項です。 プライバシーの取り扱いについては、以下を参照してください。  

- [Microsoft のプライバシー](https://www.microsoft.com/trust-center/privacy)
- [Microsoft Teams のプライバシーとセキュリティへの取り組み](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [IT プロフェッショナル向け: Microsoft Teams のプライバシーとセキュリティ](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>情報保護アーキテクチャ

次の図は、Teams のファイルやメッセージに対応する、Exchange と SharePoint の両方への Teams データの取り込みフローを示しています。

> [!div class="mx-imgBorder"]
> ![Exchange と SharePoint への Teams データのワークフローの図](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

次の図は、Teams 会議および通話データの Exchange への取り込みフローを示しています。

> [!div class="mx-imgBorder"]
> ![Exchange への Teams 会議と通話データのワークフローの図](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Teams のコンテンツの開示には最大で 24 時間の遅延が発生する場合があります。

## <a name="licensing"></a>ライセンス

情報保護機能に関しては、Microsoft 365 サブスクリプション、Office 365 サブスクリプション、および関連するスタンドアロン ライセンスによって、利用可能な機能セットが決定されます。

セキュリティとコンプライアンスの機能を実装するために必要なライセンスの決定については、セキュリティおよびコンプライアンス機能[](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)のライセンス要件を確認してください。

> [!NOTE]
> コンテンツ検索と電子情報開示を機能させるために、セキュリティ/コンプライアンス センター内で有効にする操作は不要です。

## <a name="location-of-data-in-teams"></a>Teams のデータの場所

Teams のデータはご利用の Microsoft 365 または Office 365 の組織に関連付けられている地理的領域内に存在します。 現在サポートされている地域を確認するには、「[Microsoft Teams のデータの場所](location-of-data-in-teams.md)」を参照してください。

ご利用のテナントのデータがどの地域で格納されるかを確認するには、[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home)  >  **[設定]**  >  **[組織プロファイル]** に移動してください。 下にスクロールして **[データの場所]** に移動します。

> [!div class="mx-imgBorder"]
> ![管理センターの、Teams を含む、[データの場所] の表を示すスクリーンショット](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>コンプライアンス基準

Teams では[、ISO 27001、ISO](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001) [27018、SSAE18](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018) [SOC 1 および SOC](https://docs.microsoft.com/microsoft-365/compliance/offering-soc)2、HIPAA、EU モデル条項[](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)[(EUMC)](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses)の標準が使用されます。 Microsoft のコンプライアンス フレームワークでは、Microsoft 365 と 365 Office 4 つのカテゴリに分類されます。 各カテゴリは、Microsoft 365 または Office 365 サービス、または関連する Microsoft サービスをそのカテゴリに一覧表示するために満たされる必要がある特定のコンプライアンスコミットメントによって定義されます。

詳細については、データ保護リソース [を参照してください](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)。 Teams では、Cloud Security Alliance のコンプライアンスもサポートしています。

## <a name="related-topics"></a>関連項目

[Microsoft 365 セキュリティ](https://docs.microsoft.com/microsoft-365/security/)

[Microsoft 365 コンプライアンス](https://docs.microsoft.com/microsoft-365/compliance/)

[Microsoft のコンプライアンスサービス](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
