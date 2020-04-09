---
title: セキュリティとコンプライアンスの概要
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: 監査および報告、コンプライアンスのコンテンツ検索、電子情報開示などを含む、Microsoft Teams のセキュリティとコンプライアンス機能の概要。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66ef35a8a8235507e4d87a7b9c4da7625a939770
ms.sourcegitcommit: 9419860f9a1c1dd2c7c444162e1d55d704e19c69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43207006"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams のセキュリティとコンプライアンス

> [!IMPORTANT]
> **共同作業中に全員が自宅で仕事をしているときに**、確実にセキュリティを確保する方法については、次の記事を参照してください。
>  - [Top 12 tasks for security teams to support working from home](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work) (在宅勤務をサポートするためにセキュリティ チームが行う 12 の主なタスク)
>  - [VPN スプリット トンネリングを使用してリモート ユーザーの Office 365 の接続を最適化する](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 更新日: 2020 年4月2日: [Teams セキュリティガイド](teams-security-guide.md)


Microsoft Teams は、お客様の期待に応える高度セキュリティおよびコンプライアンス能力を備えた Office 365 ハイパースケールのエンタープライズクラスのクラウド上に構築されています。 Office 365 のセキュリティの計画について詳しくは、「Office 365 のコンテンツ」を参照してください。 [Office 365 セキュリティのロードマップ](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)を開始することをお勧めします。 Office 365 でのコンプライアンスの計画の詳細については、「[セキュリティとコンプライアンスの計画](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)」を参照してください。


この記事では、Teams 固有のセキュリティとコンプライアンスについて詳しく説明します。 セキュリティとコンプライアンスに関する以下の Microsoft のしくみに関するビデオをお見逃しなく。

- [IT 担当者向けの Microsoft Teams の基礎](https://youtu.be/91lHNKVVvQ4) (12 分 42 秒)
- [Microsoft Teams でのセキュリティとコンプライアンスに関する扱い](https://www.youtube.com/watch?v=Km4T4hMM__k) (10 分 54 秒)

> [!IMPORTANT]
> Office 365 のお客様は、データを所有して管理します。 Microsoft は、お客様が登録したサービスを提供する以外の目的で、お客様のデータを使用することはありません。 サービス プロバイダーとして、広告のため、またはサービスに関連しない用途のために、メール、ドキュメント、チームをスキャンすることはありません。 Microsoft には、アップロードされたコンテンツへのアクセス権がありません。 OneDrive for Business および SharePoint Online と同様に、顧客データはテナント内に留まります。 信頼およびセキュリティに関連する情報の詳細については、[Microsoft Trust Center](https://microsoft.com/trustcenter) で確認できます。 Teams は Microsoft Trust Center と同じガイダンスと原則に従っています。

## <a name="security"></a>セキュリティ

Teams では、チーム全体および組織全体の 2 要素認証、Active Directory を介したシングル サインオン、転送中のデータと保存データの暗号化が適用されます。 ファイルは SharePoint に格納され、SharePoint 暗号化が適用されます。 メモは OneNote に格納され、OneNote 暗号化が適用されます。 OneNote データはチームの SharePoint サイトに格納されます。 Wiki タブを使用してノートを取ることもできます。また、その内容もチームの SharePoint サイトに格納されます。

認証と Teams の詳細については、「[ID モデルと認証](identify-models-authentication.md)」を参照してください。先進認証については、「[先進認証のしくみ](sign-in-teams.md)」が特に役立ちます。

Teams は SharePoint、OneNote、Exchange などと連携して動作するため、Office 365 のセキュリティを管理する必要があります。 Office 365 のセキュリティに関する詳細については、「[セキュリティ強化のために、Office 365 テナントを構成する](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)」を参照してください。

> [!NOTE]
> 現時点では、[プライベート チャネル](private-channels.md)でサポートされるセキュリティとコンプライアンス機能は制限されています。 プライベート チャネルにおけるすべてのセキュリティ機能とコンプライアンス機能のサポートは、近日中に行われる予定です。

### <a name="advance-threat-protection-atp"></a>Advanced Threat Protection (ATP)

Advanced Threat Protection (ATP) は、Microsoft Teams で使用することができます。SharePoint や OneDrive for Business など、コンテンツ管理用に Teams と統合されたアプリケーションと共に利用することができます。 ATP を使用すると、これらのアプリケーションのコンテンツが悪意のあるものであるかどうかを判断し、ユーザーのアクセスからこのコンテンツをブロックすることができます。

検出後に影響を受けるコンテンツがどのように管理されるかは、Office 365 で選択した設定によって異なります。 ATP の構成に関しては、すべてのアプリケーションについて考慮することを強くお勧めします。「[SharePoint、OneDrive、Microsoft Teams 用の Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)」の記事に開始方法の詳細が記載されています。

### <a name="safe-links"></a>安全なリンク

現時点で、Microsoft Teams で ATP の安全なリンクは利用できませんが、Technology Adoption Program (TAP) を通じてパブリック プレビューされています。一般公開のリリース日は設定されていませんが、その時が来たらこの記事を更新します。 また、Office 365 の安全なリンクについては、「 [office 365 の ATP の安全なリンク](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)」を参照してください。

### <a name="how-conditional-access-policies-work-for-teams"></a>Teams での条件付きアクセス ポリシーの仕組み

Microsoft Teams は、会議、カレンダー、相互運用チャット、ファイル共有などの主要な生産性に関するシナリオについて、Exchange Online、SharePoint Online、および Skype for Business Online と強く結びついています。 これらのクラウド アプリ向けに設定された条件付きアクセス ポリシーは、任意のクライアントの Microsoft Teams にユーザーが直接サインインするときに適用されます。

Microsoft Teams は、Azure Active Directory の条件付きアクセス ポリシーのクラウド アプリとして個別にサポートされています。 Microsoft Teams クラウド アプリ向けに設定されている条件付きアクセス ポリシーは、ユーザーがサインインするときに Microsoft Teams に適用されます。 ただし、 Exchange Online や SharePoint Online などの他のアプリにおいて適正なポリシーがなくでも、ユーザーはそれらのリソースに直接アクセスできます。 Azure ポータルでの条件付きアクセス ポリシーの設定の詳細については、「[Azure Active Directory のクイックスタート](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)」を参照してください。

Windows および Mac 版の Microsoft Teams デスクトップ クライアントは先進認証をサポートしています。 先進認証により、Azure Active Directory 認証ライブラリ (ADAL) に基づくサインインが、あらゆるプラットフォームの Microsoft Office クライアント アプリケーションに導入されています。

Microsoft Teams デスクトップ アプリケーションは、AppLocker をサポートしています。  AppLocker の前提条件の詳細については、「[AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker) を使用するための要件」をご覧ください。

## <a name="compliance"></a>コンプライアンス

チームには、チャネル、チャット、添付ファイル、アイテム保持ポリシー、データ損失防止 (DLP)、チャネル、チャットとファイル、監査ログの検索、Microsoft Intune でのモバイルアプリケーション管理など、コンプライアンスの分野に関するさまざまな情報が含まれています。 以下のすべてのトピックに関する情報が記載されています。 [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)または[Office 365 セキュリティ & コンプライアンスセンター](https://protection.microsoft.com)にアクセスして、これらの設定を管理できます。

### <a name="information-barriers"></a>情報の障壁

情報バリアは、メンバーやグループが相互に通信できないようにするためのポリシー (ビジネス上の必要性がない場合、またはユーザーがその操作をブロックすることを規制している場合) や、検索や電子情報開示 (以下で取り上げた理由) に関連するポリシーを設定できるようにするものです。 これらのポリシーは、1:1 チャット、グループチャット、またはチームレベルでユーザーに影響を与える可能性があります。

このトピックについて詳しくは、「 [Microsoft Teams の情報の障壁」](information-barriers-in-teams.md)をご覧ください。

### <a name="communication-compliance"></a>通信のコンプライアンス

Microsoft 365 での通信のコンプライアンスによって、不快感を持つ言語、機密情報、および社内および規制標準に関連する情報について Microsoft Teams の通信を調査するように構成可能な、範囲内ポリシーにユーザーを追加することができます。 パブリックとプライベートの両方の Teams チャネルでのチャットおよび関連付けられた添付ファイルは、個々のチャットと添付ファイルをスキャンして、組織内の通信リスクを最小限に抑えることができます。 不適切なチームの通信を検出、キャプチャし、対処するために役立つポリシーを構成する方法の詳細については、「 [Microsoft 365 での通信のコンプライアンス](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)」を参照してください。

### <a name="retention-policies"></a>アイテム保持ポリシー

Microsoft Teams のアイテム保持ポリシーを使用すると、規制、法的、ビジネス、その他の理由で、組織が所有する必要がある重要なデータを保持することができます。また、保持する必要がないコンテンツや通信を削除することもできます。 アイテム保持ポリシーを使用して、データを一定期間保管してから削除することもできます。 詳細については、「[Microsoft Teams の保持ポリシー](retention-policies.md)」の記事を参照してください。

### <a name="data-loss-prevention-dlp"></a>データ損失防止 (DLP)

Microsoft Teams のデータ損失防止 (DLP) と、Office 365 の大きな DLP ストーリーは、Office 365 で機密性の高いドキュメントやデータを保護するためのビジネス対応状況を中心としています。 メッセージやドキュメントの機密情報に関する懸念がある場合、DLP ポリシーを使用すれば、ユーザーがその機密データを不適切な人々と共有しないようにすることができます。

Teams でのデータ損失防止の詳細については、「[Microsoft Teams 向け DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)」を参照してください。 O36 DLP の懸念事項については、 [「データ損失防止の概要」](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)をご覧ください。

### <a name="ediscovery"></a>電子情報開示

電子情報開示 (eDiscovery) とは、訴訟または調査における開示要求に対応するための電子保持情報 (ESI) の電子的な特定、収集、生成です。 これらの機能には、Teams データのケース管理、保持、検索、分析、エクスポートが含まれています。 チャット、メッセージング、ファイル、会議と通話の概要も含まれています。 Teams の会議と通話では、会議と通話で発生したイベントの概要が作成され、電子情報開示で利用可能な状態になります。

セキュリティ & コンプライアンスセンターで Office 365 eDiscovery を実行する方法と、コンプライアンスコンテンツ検索を実行する方法の詳細については、以下のリンクを参照してください。

[電子情報開示](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[コンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

[ゲスト間のチャットの電子情報開示](eDiscovery-investigation.md)についての Teams 固有の記事もあります。

お客様は、各自の[要件](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery)に応じて、インプレース電子情報開示または [Advanced eDiscovery] を活用できます。 次の表で、これらの 2 つの違いについて説明します。

| |インプレース電子情報開示  |Advanced eDiscovery  |
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

Office 365 セキュリティ/コンプライアンス センターでの保持およびホールドの詳細については、「[アイテム保持ポリシーの概要](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)」の記事を参照してください。 訴訟ホールドについての Teams 固有の情報は、「[Microsoft Teams ユーザーまたはチームを訴訟ホールドの対象にする](legal-hold.md)」の記事を参照してください。

### <a name="compliance-content-search"></a>コンプライアンスのコンテンツ検索

コンテンツ検索では、豊富なフィルター機能を活用してすべてのチーム データを検索することができます。 結果として得られるデータは、特定のコンテナにエクスポートでき、コンプライアンスおよび訴訟のサポートとして用いることができます。 この操作は電子情報開示ケースの有無に関わらず実行できます。 これにより、コンプライアンス管理者は、すべてのユーザーにわたる Teams データを収集し、そのデータをレビューして、さらに処理するためにエクスポートできるようになります。 Office 365 セキュリティ & コンプライアンスセンターで Microsoft Teams およびその他の Office 365 コンテンツのコンプライアンスコンテンツ検索を実行する方法については、「 [office 365 の記事でこのコンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/content-search)を行う」を参照してください。

> [!TIP]
> コンテンツ検索を使用すると、チャット、チャネル メッセージ、会議、通話など、Microsoft Teams のみのコンテンツへの絞り込みを必要に応じて行うことができます。

コンテンツ検索の構成に関する Teams 固有の詳細情報については、「[Microsoft Teams でのコンテンツ検索](content-search.md)」の記事を参照してください。

### <a name="auditing-and-reporting"></a>監査と報告

監査ログ検索は、Office 365 セキュリティ/コンプライアンス センターに直結しています。無制限の監査タイムラインでの管理上の使用や調査ができるように、ワークロード固有または汎用のイベント セットをエクスポートすることにより、監査イベントに関するアラートと報告の設定を行うことができます。 Office 365 セキュリティ/コンプライアンス センター内ですべての監査ログ データに関するアラートを設定することができ、このデータをさらに分析するために、フィルター処理およびエクスポートすることもできます。 Office 365 の監査ログの実施方法について詳しくは、「[監査ログの検索](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)」の記事を参照してください。 Office 365 セキュリティ/コンプライアンス センターで Microsoft Teams のイベントを検索する方法の詳細について、「[Teams での監査を有効にする](audit-log-events.md)」の記事を検討することもできます。

## <a name="privacy"></a>プライバシー

Microsoft では、データの保護は最も優先度の高いものとなっています。 プライバシーに関するベストプラクティスについては、「 [Microsoft のプライバシー](https://www.microsoft.com/trust-center/privacy)に関する声明」を参照してください。

## <a name="information-protection-architecture"></a>情報保護アーキテクチャ

次の図は、Teams のファイルやメッセージに対応する、Exchange と SharePoint の両方への Teams データの取り込みフローを示しています。

![Exchange と SharePoint への Teams データのワークフローの図](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

次の図は、Teams 会議および通話データの Exchange への取り込みフローを示しています。

![Exchange への Teams 会議と通話データのワークフローの図](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Teams のコンテンツの開示には最大で 24 時間の遅延が発生する場合があります。

## <a name="licensing"></a>ライセンス

情報保護機能については、Office 365 サブスクリプションとそれに関連付けられたスタンドアロン ライセンスによって利用可能な機能セットが決まります。

セキュリティとコンプライアンスのための機能を実装するためにライセンスのニーズを特定する方法については、「 [Office 365 または Microsoft 365 のライセンス](https://download.microsoft.com/download/8/7/7/877B1713-671E-43AA-BB79-AF8478C64AFF/Licensing-Microsoft-365.pdf)を確認する」を参照してください。

> [!NOTE]
> コンテンツ検索と電子情報開示を機能させるために、セキュリティ/コンプライアンス センター内で有効にする操作は不要です。

## <a name="location-of-data-in-teams"></a>Teams のデータの場所

Teams のデータはご利用の Office 365 テナントに関連付けられている地理的領域内に存在します。 現在サポートされている地域を確認するには、「[Microsoft Teams のデータの場所](location-of-data-in-teams.md)」を参照してください。

ご利用のテナントのデータがどの地域で格納されるかを確認するには、[[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home)  >  **[設定]**  >  **[組織プロファイル]** に移動してください。 下にスクロールして **[データの場所]** に移動します。

![管理センターの、Teams を含む、[データの場所] の表を示すスクリーンショット](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>コンプライアンス基準

Teams は層 D に準拠しています。 これには、 [iso 27001](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001)、 [iso 27018](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018)、 [SSAE16 soc 1 と soc 2](https://docs.microsoft.com/microsoft-365/compliance/offering-soc)、 [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)、および[EU モデル条項 (EUMC)](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses)が含まれます。 Microsoft のコンプライアンスフレームワークでは、Office 365 アプリケーションとサービスは4つのカテゴリに分類されています。 各カテゴリは、そのカテゴリに記載されるように、Office 365 サービスまたは関連する Microsoft サービスに対して満たす必要がある特定のコンプライアンスコミットメントによって定義されます。

業界をリードするコンプライアンスへの取り組みを実施しているコンプライアンス カテゴリ C および D のサービスは、既定で有効になっています。カテゴリ A と B のサービスでは、組織全体に対してオンまたはオフにする制御が用意されています。詳細については、「[Compliance Framework for Industry Standards and Regulations (業界の規格と規制のコンプライアンス フレームワーク)](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf)」をご覧ください。Teams はクラウド セキュリティ アライアンス (CSA) にも準拠しています。

## <a name="related-topics"></a>関連項目

[Microsoft 365 セキュリティ](https://docs.microsoft.com/microsoft-365/security/)
[microsoft 365 コンプライアンス](https://docs.microsoft.com/microsoft-365/compliance/)
に関する[microsoft のコンプライアンスサービス](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
