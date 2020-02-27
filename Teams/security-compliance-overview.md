---
title: Microsoft Teams のセキュリティとコンプライアンスの概要
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27c46949391ec37178985ab3ed4a08aebc7e5747
ms.sourcegitcommit: 29034bda30a8460eb18600785f785528d0944041
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "42285739"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams のセキュリティとコンプライアンス

> [!IMPORTANT]
> Office 365 のお客様は、データを所有して管理します。 Microsoft は、お客様が登録したサービスを提供する以外の目的でデータを使用することはありません。 サービスプロバイダとして、メール、ドキュメント、またはチームの広告をスキャンしたり、サービスに関連していなかったりすることはありません。 Microsoft には、アップロードされたコンテンツへのアクセス権がありません。 OneDrive for Business と SharePoint Online と同様に、顧客データはテナント内に残ります。 [Microsoft セキュリティセンター](https://microsoft.com/trustcenter)で、信頼関係とセキュリティ関連の情報を確認できます。 Teams は Microsoft Trust Center と同じガイダンスと原則に従っています。

Microsoft Teams は、お客様の期待に応える高度セキュリティおよびコンプライアンス能力を備えた Office 365 ハイパースケールのエンタープライズクラスのクラウド上に構築されています。 O365 でのセキュリティの計画の詳細については、「O365 のコンテンツ」を参照してください。 [O365 セキュリティのロードマップは、](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)最初に始めるのに最適な場所です。 O365 のコンプライアンスの計画について詳しくは、「[セキュリティとコンプライアンスの計画](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)」をご覧ください。

この記事では、Teams 固有のセキュリティとコンプライアンスについて詳しく説明します。 セキュリティとコンプライアンスについては、次の Microsoft のしくみに関するビデオをご覧ください。

- [Microsoft Teams の IT の基礎: セキュリティとコンプライアンス](https://youtu.be/91lHNKVVvQ4)(12:42 分)
- [セキュリティとコンプライアンスのための Microsoft Teams コントロール](https://www.youtube.com/watch?v=Km4T4hMM__k)(10:54 分)

## <a name="security"></a>セキュリティ

Teams では、チーム全体および組織全体の2要素認証、Active Directory によるシングルサインオン、送信および保存されているデータの暗号化が適用されます。 ファイルは SharePoint に格納され、SharePoint 暗号化が適用されます。 メモは OneNote に格納され、OneNote 暗号化が適用されます。 OneNote データはチームの SharePoint サイトに格納されます。 [Wiki] タブはメモの作成にも使用でき、そのコンテンツはチーム SharePoint サイトにも保存されます。

認証とチームの詳細については、「 [id モデルと認証](identify-models-authentication.md)」を参照してください。先進認証のしくみは、特に先進認証についての[説明](sign-in-teams.md)です。

Teams は SharePoint、OneNote、Exchange などと連携して動作するため、O365 でセキュリティを管理する必要があります。 Office 365 セキュリティの詳細については、「 [office 365 テナントを構成してセキュリティを強化](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)する」を参照してください。

> [!NOTE]
> 現時点では、[プライベートチャネル](private-channels.md)は、セキュリティとコンプライアンスの制限された機能をサポートしています。 プライベートチャネルの一連のセキュリティ機能とコンプライアンス機能のサポートは、近日中にサポートされます。

### <a name="advance-threat-protection-atp"></a>事前脅威保護 (ATP)

事前脅威防止 (ATP) は、Microsoft Teams と SharePoint および OneDrive for Business、およびコンテンツ管理のためにチームと統合されたアプリケーションと共に使用できます。 ATP では、これらのアプリケーションのコンテンツが悪意のあるものであるかどうかを判断し、ユーザーアクセスからこのコンテンツをブロックすることができます。

検出後の影響を受けるコンテンツの管理方法は、O365 で選択した設定によって異なります。 ATP の構成に関しては、すべてのアプリケーションについて考慮することを強くお勧めします。さらに詳しくは、 [Office 365 atp For SharePoint、OneDrive、Microsoft Teams の](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)記事では、使用を開始する方法についての詳細情報を参照してください。

### <a name="safe-links"></a>安全なリンク

現時点では、ATP の安全なリンクは Microsoft Teams では利用できませんが、後で利用できるようになります。その場合は、このコンテンツを更新してお知らせください。 それまでの間、O365 の安全なリンクについては、「 [Office 365 ATP の安全なリンク](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)」を参照してください。

### <a name="how-conditional-access-policies-work-for-teams"></a>チームの条件付きアクセスポリシーのしくみ

Microsoft Teams は、会議、カレンダー、相互運用チャット、ファイル共有などの主要な生産性に関するシナリオについて、Exchange Online、SharePoint Online、および Skype for Business Online と強く結びついています。 これらのクラウド アプリ向けに設定された条件付きアクセス ポリシーは、任意のクライアントの Microsoft Teams にユーザーが直接サインインするときに適用されます。

Microsoft Teams は、Azure Active Directory の条件付きアクセス ポリシーのクラウド アプリとして個別にサポートされています。 Microsoft Teams クラウド アプリ向けに設定されている条件付きアクセス ポリシーは、ユーザーがサインインするときに Microsoft Teams に適用されます。 ただし、 Exchange Online や SharePoint Online などの他のアプリにおいて適正なポリシーがなくでも、ユーザーはそれらのリソースに直接アクセスできます。 Azure portal での条件付きアクセスポリシーの設定の詳細については、「 [Azure Active Directory のクイックスタート](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)」を参照してください。

Windows および Mac 版の Microsoft Teams デスクトップ クライアントは先進認証をサポートしています。 先進認証により、Azure Active Directory 認証ライブラリ (ADAL) に基づくサインインが、あらゆるプラットフォームの Microsoft Office クライアント アプリケーションに導入されています。

Microsoft Teams デスクトップ アプリケーションは、AppLocker をサポートしています。  AppLocker の前提条件の詳細については、「 [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)を使用するための要件」を参照してください。

## <a name="compliance"></a>コン

チームには、アイテム保持ポリシー、データ損失防止 (DLP)、チャネルの電子情報開示および法的保持、チャットとファイル、監査ログの検索、Microsoft とのモバイルアプリケーション管理など、コンプライアンスの領域に役立つさまざまな情報が用意されています。Intune. 以下のすべてのトピックに関する情報が記載されています。 Office 365 セキュリティ & コンプライアンスセンターにアクセスして、これらの設定を管理できます。

### <a name="retention-policies"></a>アイテム保持ポリシー

Microsoft Teams のアイテム保持ポリシーを使用すると、規制、法的、ビジネス、その他の理由により、組織が保持する必要があるデータを保持することができます。また、保持する必要がないコンテンツや通信を削除することもできます。 アイテム保持ポリシーを使用して、データを一定期間保持してから削除することもできます。 詳細については、「 [Microsoft Teams のアイテム保持ポリシー」](retention-policies.md)を参照してください。

### <a name="data-loss-prevention-dlp"></a>データ損失防止 (DLP)

Microsoft Teams でのデータ損失防止 (DLP) と O365 の大きな DLP ストーリーは、ビジネスの準備に関するものであり、O365 の機密ドキュメントやデータを保護するために発生します。 メッセージやドキュメントの機密情報に関する懸念事項がある場合は、DLP ポリシーを使用することで、ユーザーがこの機密データを不適切なユーザーと共有しないようにすることができます。

Teams でのデータ損失防止の詳細については、「 [Microsoft teams の DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)」を参照してください。 O36 DLP の問題についての[https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)優れた記事は、です。

### <a name="ediscovery"></a>電子情報開示

電子的証拠開示 (電子情報開示) は、法律、または調査での生産要求に応じて、電子的に保存された情報 (ESI) を特定し、収集し、生成するための電子的な側面です。 これらの機能には、Teams データのケース管理、保持、検索、分析、エクスポートが含まれています。 チャット、メッセージング、ファイル、会議と通話の概要も含まれています。 Teams の会議と通話では、会議と通話で発生したイベントの概要が作成され、電子情報開示で利用可能な状態になります。

セキュリティ & コンプライアンスセンターでの O365 eDiscovery の実行方法と、コンプライアンスコンテンツ検索の実行の詳細については、以下のリンクを参照してください。

[電子情報開示](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[コンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

[ゲスト間のチャットの電子情報開示の](eDiscovery-investigation.md)詳細については、チーム固有の記事を参照してください。

お客様は、[必要に応じ](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery)てインプレース ediscovery または [Advanced ediscovery] を活用できます。 次の表で、これらの 2 つの違いについて説明します。

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

### <a name="legal-hold"></a>訴訟ホールド

訴訟の際には、ユーザー (カストディアン) またはチームに関連付けられたすべてのデータを、ケースの証拠として使用できるように、変更不可として保持する必要がある場合があります。 この操作を行うには、ユーザー (ユーザーのメールボックス) かチームを法的な保留リストに配置します。 チームの法的保持の場合、チームのメールボックスは次の保留リストに含めることができます。

- インプレースホールド (ターゲットのクエリまたはフィルター処理されたコンテンツを使用した、メールボックスまたはサイトコレクションのサブセット) または
- 訴訟ホールド (メールボックスまたはサイトコレクション全体が保留中)

どちらの場合も、保留を設定すると、エンドユーザーがグループのメールボックス内のチャネルメッセージを削除または編集した場合でも、そのコンテンツの不変コピーは保持され、電子情報開示検索で利用できるようになります。 通常、法的保持は電子情報開示ケースのコンテキスト内に適用されます。

Office 365 セキュリティ & コンプライアンスセンターでの保存と保持の詳細については、「[アイテム保持ポリシーの概要](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)」を参照してください。 法的保持に関するその他のチーム固有の情報については、 [Microsoft Teams のユーザーまたはチームに法的保持](legal-hold.md)に関する記事も掲載しています。詳細については、こちらを参照してください。

### <a name="compliance-content-search"></a>コンプライアンスのコンテンツ検索

コンテンツ検索を使用すると、豊富なフィルター機能を利用してすべてのチームデータを検索できます。 結果として得られたデータは、コンプライアンスと訴訟のサポートを目的として特定のコンテナーにエクスポートできます。 この操作は電子情報開示ケースの有無に関わらず実行できます。 これにより、コンプライアンス管理者は、すべてのユーザーにわたる Teams データを収集し、そのデータをレビューして、さらに処理するためにエクスポートできるようになります。 Office 365 セキュリティ & コンプライアンスセンターで、Microsoft Teams およびその他の O365 のコンテンツに対するコンプライアンスコンテンツ検索の実施方法の詳細については、「 [O365 の記事でこのコンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/content-search)を参照してください。

> [!TIP]
> コンテンツ検索を使用すると、必要に応じて、チャットやチャネルメッセージ、会議、通話などの Microsoft Teams のみのコンテンツにフィルターを適用することができます。

コンテンツ検索の構成についてチーム固有の情報が必要な場合は、「 [Microsoft Teams のコンテンツ検索」](content-search.md)を参照してください。

### <a name="auditing-and-reporting"></a>監査と報告

監査ログの検索機能は、Office 365 セキュリティ & コンプライアンスセンターに直接表示されます。また、負荷の高い管理者によるワークロードの使用や汎用イベントセットのエクスポートを許可することで、通知を設定し、監査イベントに関するレポートを作成することができます。 Office 365 セキュリティ & コンプライアンスセンター内のすべての監査ログデータに対して通知を設定することができ、さらに分析するためにこのデータをフィルター処理し、エクスポートすることができます。 O365 の監査ログの実施方法の詳細については、「[監査ログの検索](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)」の記事を参照してください。 Office 365 セキュリティ & コンプライアンスセンターで Microsoft Teams のイベントを検索する方法については、「 [Teams で監査を有効](audit-log-events.md)にする」を参照してください。

## <a name="information-protection-architecture"></a>情報保護のアーキテクチャ

次の図は、Teams のファイルやメッセージに対応する、Exchange と SharePoint の両方への Teams データの取り込みフローを示しています。

![Exchange と SharePoint へのチームデータのワークフローの図](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

次の図は、Teams 会議および通話データの Exchange への取り込みフローを示しています。

![チーム会議のワークフローと Exchange へのデータの発信の図](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Teams のコンテンツの開示には最大で 24 時間の遅延が発生する場合があります。

## <a name="licensing"></a>ライセンス

情報保護機能については、Office 365 サブスクリプションと関連するスタンドアロンライセンスによって、利用可能な機能セットが決定されます。

セキュリティとコンプライアンスのための機能を実装するためにライセンスのニーズを特定する方法については、「 [Office のライセンス](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)認証を行う」を参照してください。365

> [!NOTE]
> コンテンツ検索と電子情報開示は、セキュリティ & コンプライアンスセンターで有効にする必要はありません。

## <a name="location-of-data-in-teams"></a>Teams のデータの場所

Teams のデータはご利用の Office 365 テナントに関連付けられている地理的領域内に存在します。 現在サポートされている地域を確認するには、 [Microsoft Teams でデータの場所](location-of-data-in-teams.md)を確認してください。

テナントのデータが格納されている領域を確認する必要がある場合は、 [Microsoft 365 管理センター](https://portal.office.com/adminportal/home) > の**設定** > **組織プロファイル**に移動します。 下にスクロールして [**データの場所**] に移動します。

![管理センターの Teams を含むデータの場所テーブルのスクリーンショット](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>コンプライアンス標準

Teams は Tier D 準拠です。これにより、ISO 27001、ISO 27018、SSAE16 SOC 1 および SOC 2、HIPAA、EU モデル契約条項 (EUMC) といった標準に対応します。Microsoft コンプライアンス フレームワークにおいて、Microsoft は Office 365 のアプリケーションとサービスを 4 つのカテゴリに分類しています。各カテゴリは、そのカテゴリのリストに記載されるために Office 365 サービスや関連するマイクロソフトのサービスが満たす必要のある、特定のコンプライアンス コミットメントによって定義されます。

業界をリードするコンプライアンスへの取り組みを実施しているコンプライアンス カテゴリ C および D のサービスは、既定で有効になっています。カテゴリ A と B のサービスでは、組織全体に対してオンまたはオフにする制御が用意されています。詳細については、「[Compliance Framework for Industry Standards and Regulations (業界の規格と規制のコンプライアンス フレームワーク)](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf)」をご覧ください。Teams はクラウド セキュリティ アライアンス (CSA) にも準拠しています。

## <a name="related-topics"></a>関連トピック

[M365 セキュリティ](https://docs.microsoft.com/microsoft-365/security/)
[M365 コンプライアンス](https://docs.microsoft.com/microsoft-365/compliance/)
