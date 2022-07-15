---
title: セキュリティとコンプライアンスの概要
author: MSFTTracyP
ms.author: tracyp
manager: laurawi
ms.date: 04/12/2022
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: プライバシーと暗号化、監査とレポートなど、Microsoft Teams のセキュリティとコンプライアンス機能の概要。
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
ms.openlocfilehash: c4e31e59992d24aeac190c4f1ffb40d8c3dfef78
ms.sourcegitcommit: 2871c05e00458a0cc76d919ff822b0b354bd1f72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66810069"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams のセキュリティとコンプライアンス

> [!IMPORTANT]
> **COVID-19 の発生中に全員が自宅で作業しているときにセキュリティを** 確保する最善の方法については、次の記事を参照してください。
>  - [Top 12 tasks for security teams to support working from home](/microsoft-365/security/top-security-tasks-for-remote-work) (在宅勤務をサポートするためにセキュリティ チームが行う 12 の主なタスク)
>  - [VPN スプリット トンネリングを使用してリモート ユーザーの Microsoft 365 または Office 365 の接続を最適化する](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 2020 年 4 月 2 日に更新: [Teams セキュリティ ガイド](teams-security-guide.md)


Microsoft Teams は Microsoft 365 上に構築され、ハイパースケールのエンタープライズ レベルのクラウドをOffice 365し、お客様が期待する高度なセキュリティとコンプライアンス機能を提供します。 Microsoft 365 またはOffice 365でのセキュリティの計画の詳細については、[セキュリティ ロードマップ](/microsoft-365/security/office-365-security/security-roadmap)を開始することをお勧めします。 Microsoft 365 またはOffice 365でのコンプライアンスの計画の詳細については、[セキュリティ&コンプライアンスの計画](/microsoft-365/compliance/plan-for-security-and-compliance)から始めることができます。


この記事では、Teams 固有のセキュリティとコンプライアンスについて詳しく説明します。 セキュリティとコンプライアンスに関する Microsoft Mechanics のビデオをお見逃しなく。

- [IT 担当者向けの Microsoft Teams の基礎](https://youtu.be/91lHNKVVvQ4) (12 分 42 秒)
- [Microsoft Teams でのセキュリティとコンプライアンスに関する扱い](https://www.youtube.com/watch?v=Km4T4hMM__k) (10 分 54 秒)

> [!IMPORTANT]
> Microsoft 365 またはOffice 365のお客様は、お客様のデータを所有および制御します。 Microsoft は、お客様が登録したサービスを提供する以外の目的で、お客様のデータを使用することはありません。 サービス プロバイダーとして、広告のため、またはサービスに関連しない用途のために、メール、ドキュメント、チームをスキャンすることはありません。 Microsoft は、アップロードされたコンテンツにアクセスできません。 Microsoft 365 の OneDrive や SharePoint と同様に、顧客データはテナント内に残ります。 信頼およびセキュリティに関連する情報の詳細については、[Microsoft Trust Center](https://microsoft.com/trustcenter) で確認できます。 Teams は Microsoft Trust Center と同じガイダンスと原則に従っています。

## <a name="security"></a>セキュリティ

Teams では、チーム全体および組織全体の 2 要素認証、Active Directory を介したシングル サインオン、転送中のデータと保存データの暗号化が適用されます。 ファイルは SharePoint に格納され、SharePoint 暗号化が適用されます。 メモは OneNote に格納され、OneNote 暗号化が適用されます。 OneNote データはチームの SharePoint サイトに格納されます。 Wiki タブを使用してノートを取ることもできます。また、その内容もチームの SharePoint サイトに格納されます。

認証と Teams の詳細については、「[ID モデルと認証](identify-models-authentication.md)」を参照してください。先進認証については、「[先進認証のしくみ](sign-in-teams.md)」が特に役立ちます。

Teams は SharePoint、OneNote、Exchange などと連携して動作するため、Microsoft 365 またはOffice 365のオールアップでセキュリティを快適に管理する必要があります。 詳細については、[セキュリティを強化するために Microsoft 365 またはOffice 365組織を構成する方法](/office365/securitycompliance/tenant-wide-setup-for-increased-security)について説明します。

> [!NOTE]
> 現時点では、[プライベート チャネル](private-channels.md)でサポートされるセキュリティとコンプライアンス機能は制限されています。 プライベート チャネルにおけるすべてのセキュリティ機能とコンプライアンス機能のサポートは、近日中に行われる予定です。

### <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

Microsoft Defender for Office 365は、コンテンツ管理のために Teams と統合する SharePoint および OneDrive アプリケーションと共に Microsoft Teams で使用できます。 Defender for Office 365では、これらのアプリケーションのコンテンツが本質的に悪意があるかどうかを判断し、このコンテンツをユーザー アクセスからブロックすることができます。

検出後に影響を受けるコンテンツを管理する方法は、Microsoft 365 またはOffice 365で選択した設定までです。 Defender for Office 365の構成に関しては、すべてのアプリケーションを検討することを強くお勧めします。詳細については、[安全なリンクのしくみの概要と設定手順](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide)を参照してください。

### <a name="safe-links-in-microsoft-teams"></a>Microsoft Teams の安全なリンク

Defender for Office 365安全なリンクは、Microsoft Teams で入手できます。 安全なリンクとこの機能の使用方法の詳細については、 [Teams の安全なリンク設定を参照してください](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide)。 安全なリンクは、[Defender for Office 365プラン 1 とプラン 2 の](/microsoft-365/security/office-365-security/overview?view=o365-worldwide)両方で使用できます。

### <a name="safe-attachments"></a>安全な添付ファイル

安全な添付ファイルは、悪意のある添付ファイルをチェックして検出することで、ユーザーのセキュリティを強化するように設計された機能です。 グローバル管理者またはセキュリティ管理者は [、この機能を有効にして](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams?view=o365-worldwide) 、疑わしい悪意のある添付ファイルを処理するための [ポリシーを作成](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide) して、ユーザーへの送信、クリック、操作を防止します。

安全な添付ファイル保護は、SharePoint、OneDrive、Microsoft Teams、Microsoft 365、またはMicrosoft Defender for Office 365[プラン 1 およびプラン 2 のOffice 365](/microsoft-365/security/office-365-security/overview?view=o365-worldwide)で使用できます。 安全な添付ファイルの詳細と、組織の保護に役立つ方法については、 [この記事を参照](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide)してください。

### <a name="secure-score"></a>セキュリティスコア

Microsoft Secure Score は、組織のセキュリティ体制の測定値であり、より多くの改善アクションが実行されたことを示す数値が多くなります。 [Microsoft 365 セキュリティ センター](https://security.microsoft.com/securescore)にあります。 セキュリティスコアに関する推奨事項に従うと、組織を脅威から保護できます。 組織は、Microsoft 365 セキュリティ センターの一元化されたダッシュボードから、Microsoft 365 ID、アプリ、デバイスのセキュリティを監視し、作業できます。 Microsoft Teams にセキュリティ スコアに関する推奨事項が追加され、管理者はプラットフォーム上でセキュリティに関する姿勢を監視することをお勧めします。

セキュリティスコアは、組織に役立ちます。
- 組織のセキュリティ体制の現在の状態を報告します。
- 検出可能性、可視性、ガイダンス、および制御を提供することで、セキュリティ体制を改善します。
- ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。

### <a name="how-conditional-access-policies-work-for-teams"></a>Teams での条件付きアクセス ポリシーの仕組み

Microsoft Teams は、会議、予定表、相互運用チャット、ファイル共有などの主要な生産性シナリオで、Exchange Online、SharePoint、Skype for Business Online に大きく依存しています。 これらのクラウド アプリ向けに設定された条件付きアクセス ポリシーは、任意のクライアントの Microsoft Teams にユーザーが直接サインインするときに適用されます。

Microsoft Teams は、Azure Active Directory の条件付きアクセス ポリシーのクラウド アプリとして個別にサポートされています。 Microsoft Teams クラウド アプリ向けに設定されている条件付きアクセス ポリシーは、ユーザーがサインインするときに Microsoft Teams に適用されます。 ただし、Exchange Onlineや SharePoint などの他のアプリに対する正しいポリシーがない場合でも、ユーザーはこれらのリソースに直接アクセスできる場合があります。 Azure portalでの条件付きアクセス ポリシーの設定の詳細については、「[Azure Active Directory クイック スタート」を](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)参照してください。

Windows および Mac 版の Microsoft Teams デスクトップ クライアントは先進認証をサポートしています。 先進認証により、Azure Active Directory 認証ライブラリ (ADAL) に基づくサインインが、あらゆるプラットフォームの Microsoft Office クライアント アプリケーションに導入されています。

Microsoft Teams デスクトップ アプリケーションは、AppLocker をサポートしています。  AppLocker の前提条件の詳細については、「[AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker) を使用するための要件」をご覧ください。

## <a name="compliance"></a>コンプライアンス

Teams には、チャネル、チャット、添付ファイルの通信コンプライアンス、アイテム保持ポリシー、データ損失防止 (DLP)、チャネル、チャット、ファイルの電子情報開示と訴訟ホールド、監査ログ検索、Microsoft Intuneを使用したモバイル アプリケーション管理など、コンプライアンス領域に役立つさまざまな情報があります。 以下のすべてのトピックに関するいくつかの情報が提供されており、[Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com)に移動してこれらの設定を管理できます。

### <a name="information-barriers"></a>情報バリア

Microsoft Purview Information Barriers は、Teams 管理者が、ユーザーやグループが互いに通信できないようにするポリシーです (ビジネスで連絡する必要がない場合、または規制上の理由で通信をブロックする場合)、ルックアップや電子情報開示 (以下で説明します) などに関連するポリシーを設定することもできます。 これらのポリシーは、1 対 1 のチャット、グループ チャット、またはチーム レベルのユーザーに影響を与える可能性があります。 情報バリア機能はパブリック クラウドで利用でき、2021 年 1 月以降は GCC クラウドにロールアウトされました。

このトピックの詳細については、 [Microsoft Teams の情報バリアに関するページを参照してください](information-barriers-in-teams.md)。

### <a name="communication-compliance"></a>通信コンプライアンス

Microsoft Purview コミュニケーション コンプライアンスを使用すると、Microsoft Teams の通信で、不適切な言語、機密情報、および内部および規制標準に関連する情報を調べるために構成できるスコープ内ポリシーにユーザーを追加できます。 チャット通信と、パブリックとプライベートの両方の Teams チャネル、個々のチャット、添付ファイルの添付ファイルをスキャンして、組織内のコミュニケーション リスクを最小限に抑えることができます。 不適切な Teams 通信の検出、キャプチャ、およびアクションの実行に役立つポリシーを構成する方法の詳細については、「 [通信コンプライアンスの詳細](/microsoft-365/compliance/communication-compliance)」を参照してください。

### <a name="sensitivity-labels"></a>秘密度ラベル

[秘密度ラベル](/microsoft-365/compliance/sensitivity-labels)を適用して、チーム内での共同作業中に作成された機密組織のコンテンツへのアクセスを保護し、規制します。 たとえば、チームのプライバシー (パブリックまたはプライベート) を構成し、ゲスト アクセスと外部共有を制御し、管理されていないデバイスからのアクセスを管理するラベルを適用します。 詳細については、 [Microsoft Teams の秘密度ラベルを確認してください](sensitivity-labels.md)。

### <a name="microsoft-purview-data-loss-prevention-dlp"></a>Microsoft Purview データ損失防止 (DLP)

Microsoft Teams のデータ損失防止 (DLP) と Microsoft Purview の大規模な DLP ストーリーは、機密ドキュメントとデータの保護に関してビジネスの準備を中心に展開されています。 メッセージやドキュメントの機密情報に関する懸念がある場合、DLP ポリシーを使用すれば、ユーザーがその機密データを不適切な人々と共有しないようにすることができます。

Teams でのデータ損失防止の詳細については、「[Microsoft Teams 向け DLP](/microsoft-365/compliance/dlp-microsoft-teams)」を参照してください。 DLP に関する懸念事項の良い記事は、「 [データ損失防止について学習する」です](/microsoft-365/compliance/dlp-learn-about-dlp)。

### <a name="customer-key"></a>顧客キー

Microsoft 365 では、コンテンツのサービス暗号化に加えて、追加の暗号化レイヤーが提供されます。 顧客キーは、指定したキーを使用して、Microsoft Teams でさまざまな種類のデータを暗号化します。 顧客キーをアプリケーション レベルで使用すると、カスタマー キーは SharePoint Online に格納されている Teams ファイルを暗号化します。 詳細については、「 [Microsoft Purview カスタマー キーを使用したサービス暗号化](/microsoft-365/compliance/customer-key-overview)」を参照してください。

顧客キーをテナント レベルで使用すると、Customer Key は次の暗号化を行います。
- Teams チャット メッセージ (1:1 チャット、グループ チャット、会議チャット、チャネル会話)
- Teams メディア メッセージ (画像、コード スニペット、ビデオ、Wiki 画像)
- Teams ストレージに保存されている Teams の通話と会議の記録
- Teams チャット通知
- Cortana による Teams チャットの提案
- Teams の状態メッセージ

詳細については、 [テナント レベルでの顧客キーの概要に関する](/microsoft-365/compliance/customer-key-tenant-level) ページを参照し、 [パブリック プレビューで公開されている Microsoft Teams のカスタマー キーサポート](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)に関する Microsoft Teams ブログを参照してください。 テナント レベルで Customer Key を含むMicrosoft Purview 情報保護 リリースの詳細については、「[機密データを把握して保護するための新しいMicrosoft Purview 情報保護機能の発表」を参照してください](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)。

### <a name="retention-policies"></a>アイテム保持ポリシー

Microsoft Teams のアイテム保持ポリシーを使用すると、規制、法的、ビジネス、その他の理由で、組織が所有する必要がある重要なデータを保持することができます。また、保持する必要がないコンテンツや通信を削除することもできます。 アイテム保持ポリシーを使用して、データを一定期間保管してから削除することもできます。 詳細については、 [Microsoft Teams のアイテム保持ポリシーを確認してください](retention-policies.md)。

### <a name="ediscovery"></a>電子情報開示

電子情報開示 (eDiscovery) とは、訴訟または調査における開示要求に対応するための電子保持情報 (ESI) の電子的な特定、収集、生成です。 これらの機能には、Teams データのケース管理、保持、検索、分析、エクスポートが含まれています。 チャット、メッセージング、ファイル、会議と通話の概要も含まれています。 Teams の会議と通話では、会議と通話で発生したイベントの概要が作成され、電子情報開示で利用可能な状態になります。

Microsoft Purview コンプライアンス ポータルで電子情報開示ツールを使用して Teams コンテンツを検索する方法の詳細については、次のリンクを参照してください。

- [電子情報開示](/microsoft-365/compliance/manage-legal-investigations)

- [コンテンツ検索](/microsoft-365/compliance/search-for-content)

Microsoft Teams の [コンテンツの電子情報開示調査の実施に関する詳細については、Teams 固有の記事を参照してください](eDiscovery-investigation.md)。

顧客は、要件に従って [電子情報開示または電子情報開示 (Premium)](/microsoft-365/compliance/office-365-advanced-ediscovery) を利用できます。 次の表で、これらの 2 つの違いについて説明します。

|&nbsp; |電子情報開示  |電子情報開示 (Premium)  |
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

Microsoft Purview コンプライアンス ポータルの保持と保持の詳細については、[アイテム保持ポリシーの概要](/microsoft-365/compliance/retention-policies)に関するページを参照してください。 訴訟ホールドに関する Teams 固有の詳細については、 [Microsoft Teams のユーザーまたはチームを訴訟ホールドに](legal-hold.md) 置くこともできます。詳細については、こちらを参照してください。

### <a name="content-search"></a>コンテンツ検索

コンテンツ検索では、豊富なフィルター機能を活用してすべてのチーム データを検索することができます。 結果として得られるデータは、特定のコンテナにエクスポートでき、コンプライアンスおよび訴訟のサポートとして用いることができます。 この操作は電子情報開示ケースの有無に関わらず実行できます。 これにより、コンプライアンス管理者は、すべてのユーザーにわたる Teams データを収集し、そのデータをレビューして、さらに処理するためにエクスポートできるようになります。 Microsoft Teams やその他の Microsoft 365 またはMicrosoft Purview コンプライアンス ポータルのOffice 365 コンテンツのコンプライアンス コンテンツ検索を実行する方法の詳細については、[コンテンツ検索](/microsoft-365/compliance/content-search)を参照してください。

> [!TIP]
> コンテンツ検索を使用すると、チャット、チャネル メッセージ、会議、通話など、Microsoft Teams のみのコンテンツへの絞り込みを必要に応じて行うことができます。

コンテンツ検索の構成に関する Teams 固有の詳細については、 [Microsoft Teams のコンテンツ検索を確認してください](content-search.md)。

### <a name="auditing"></a>監査

監査ログ検索は、Microsoft Purview コンプライアンス ポータルに直接接続され、無制限の監査タイムラインで管理者が使用および調査するためのワークロード固有または汎用イベント セットのエクスポートを許可することで、アラートの設定や監査イベントのレポートを行う機能を提供します。 Microsoft Purview コンプライアンス ポータル内のすべての監査ログ データに対してアラートを設定し、このデータをフィルター処理してエクスポートして詳細な分析を行うことができます。 Microsoft Purview コンプライアンス ポータルで Microsoft Teams イベントを検索する方法の詳細については、「[Microsoft Teams のイベントの監査ログを検索する」を参照してください](audit-log-events.md)。

## <a name="privacy"></a>プライバシー

Microsoft では、お客様のデータを保護することが最優先事項です。 プライバシーの取り組みについて詳しくは、以下をご覧ください。  

- [Microsoft のプライバシー](https://www.microsoft.com/trust-center/privacy)
- [Microsoft Teams でのプライバシーとセキュリティへの取り組み](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [IT プロフェッショナル向け: Microsoft Teams のプライバシーとセキュリティ](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>情報保護アーキテクチャ

次の図は、Teams のファイルやメッセージに対応する、Exchange と SharePoint の両方への Teams データの取り込みフローを示しています。

> [!div class="mx-imgBorder"]
> ![Teams データから Exchange および SharePoint へのワークフローの図。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

次の図は、Teams 会議および通話データの Exchange への取り込みフローを示しています。

> [!div class="mx-imgBorder"]
> ![Teams 会議のワークフローと Exchange へのデータの呼び出しの図。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Teams のコンテンツの開示には最大で 24 時間の遅延が発生する場合があります。

## <a name="licensing"></a>ライセンス

情報保護機能に関しては、Microsoft 365 サブスクリプション、Office 365 サブスクリプション、および関連するスタンドアロン ライセンスによって、使用可能な機能セットが決定されます。

セキュリティとコンプライアンスの機能を実装するためのライセンスニーズの決定については、セキュリティ機能とコンプライアンス機能の [ライセンス要件を](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) 確認してください。

> [!NOTE]
> コンテンツ検索、電子情報開示 (Standard)、電子情報開示 (Premium) は、Microsoft Purview コンプライアンス ポータルで有効にする必要はありません。 詳細については、「 [Microsoft 365 電子情報開示ソリューション](/microsoft-365/compliance/ediscovery)」を参照してください。

## <a name="location-of-data-in-teams"></a>Teams のデータの場所

Teams のデータはご利用の Microsoft 365 または Office 365 の組織に関連付けられている地理的領域内に存在します。 現在サポートされている地域を確認するには、「[Microsoft Teams のデータの場所](location-of-data-in-teams.md)」を参照してください。

ご利用のテナントのデータがどの地域で格納されるかを確認するには、[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home)  >  **[設定]**  >  **[組織プロファイル]** に移動してください。 下にスクロールして **[データの場所]** に移動します。

> [!div class="mx-imgBorder"]
> ![管理センターの Teams を含むデータの場所テーブルのスクリーンショット。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>コンプライアンス基準

Teams では、 [ISO 27001](/microsoft-365/compliance/offering-iso-27001)、 [ISO 27018](/microsoft-365/compliance/offering-iso-27018)、 [SSAE18 SOC 1、SOC 2](/microsoft-365/compliance/offering-soc)、 [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech)、 [EU モデル条項 (EUMC)](/microsoft-365/compliance/offering-eu-model-clauses) の標準が使用されます。 Microsoft コンプライアンス フレームワーク内では、Microsoft は Microsoft 365 と Office 365 アプリケーションとサービスを 4 つのカテゴリに分類します。 各カテゴリは、そのカテゴリに一覧表示される Microsoft 365 またはOffice 365 サービス、または関連する Microsoft サービスに対して満たす必要がある特定のコンプライアンスコミットメントによって定義されます。

詳細については、 [Data Protection リソース](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)を参照してください。 Teams では、Cloud Security Alliance コンプライアンスもサポートされています。

## <a name="related-topics"></a>関連項目

[Microsoft 365 セキュリティ](/microsoft-365/security/)

[Microsoft 365 コンプライアンス](/microsoft-365/compliance/)

[Microsoft コンプライアンス オファリング](/microsoft-365/compliance/offering-home)
