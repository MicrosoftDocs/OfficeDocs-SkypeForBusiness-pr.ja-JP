---
title: Microsoft Teams のセキュリティとコンプライアンスの概要
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: 監査しレポート作成、コンプライアンス ・ コンテンツの検索、電子的証拠開示などを含む、マイクロソフトのチームのセキュリティとコンプライアンスの機能の概要について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8521816fe8aaa74c45028d962d024ab4bfd1b467
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013988"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Microsoft Teams のセキュリティとコンプライアンスの概要
======================================================

Microsoft Teams は、お客様の期待に応える高度セキュリティおよびコンプライアンス能力を備えた Office 365 ハイパースケールのエンタープライズクラスのクラウド上に構築されています。

Teams は販売開始時点から Tier C 準拠です。これにより、ISO 27001、ISO 27018、SSAE16 SOC 1 および SOC 2、HIPAA、EU モデル契約条項 (EUMC) といった標準に対応します。Microsoft コンプライアンス フレームワークにおいて、Microsoft は Office 365 のアプリケーションとサービスを 4 つのカテゴリに分類しています。各カテゴリは、そのカテゴリのリストに記載されるために Office 365 サービスや関連するマイクロソフトのサービスが満たす必要のある、特定のコンプライアンス コミットメントによって定義されます。

業界をリードするコンプライアンスへの取り組みを実施しているコンプライアンス カテゴリ C および D のサービスは、既定で有効になっています。カテゴリ A と B のサービスでは、組織全体に対してオンまたはオフにする制御が用意されています。詳細については、「[Compliance Framework for Industry Standards and Regulations (業界の規格と規制のコンプライアンス フレームワーク)](https://go.microsoft.com/fwlink/?linkid=855777)」をご覧ください。Teams はクラウド セキュリティ アライアンス (CSA) にも準拠しています。

チームは、チーム全体および組織全体の二要素認証、シングルサインオンによって、Active Directory、および転送中のデータの暗号化にも適用されます。 ファイルは、SharePoint に格納され、SharePoint の暗号化によってバックアップされています。 ノートでは、OneNote に保存され、OneNote の暗号化によってバックアップされます。 OneNote のデータは、チームの SharePoint サイトに格納されます。 メモを取ることで、[Wiki] タブを使用することも、チームの SharePoint サイト内のコンテンツが格納されているも.

監査ログ検索、電子情報開示、訴訟ホールド (チャネル、チャット、ファイルを対象とした)、Microsoft Intune 内でのモバイル アプリ管理のサポートを追加しました。 これらの設定を管理するためには、Office 365 のセキュリティとコンプライアンスの中心に移動します。 

## <a name="auditing-and-reporting"></a>監査と報告

監査ログの検索は、Office 365 のセキュリティとコンプライアンスの中心に右のプラグし、アラートを設定すると、レポートの監査イベントを作成することにより、特定のワークロードのエクスポートまたは全体で管理および調査の結果、一般的なイベントを設定する機能を公開する、監査タイムラインの制限はありません。 監査ログのすべてのデータは、Office 365 のセキュリティとコンプライアンス ・ センター内でアラートの設定、フィルタ リングの利用可能なさらに分析するためにエクスポートします。 Office 365 のセキュリティとコンプライアンスの中心でマイクロソフトのチームのイベントの監査ログの検索を実行する方法の詳細についてはこの[リンク](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)を参照してください。 

## <a name="compliance-content-search"></a>コンプライアンスのコンテンツ検索

コンテンツの検索をフィルタ リング機能が豊富なすべてのチーム データを検索するために使用し、コンプライアンス、訴訟をサポートするための特定のコンテナーをエクスポートできます。 これは、電子的証拠開示のサポート案件の有無にかかわらずを実行できます。 これにより、コンプライアンスの管理者にすべてのユーザー間でチームのデータを収集し、確認して、エクスポートしてさらに処理できます。 Office 365 のセキュリティとコンプライアンスの中心でマイクロソフトのチームのコンテンツ コンプライアンス ・ コンテンツの検索を実行する方法の詳細についてはこの[リンク](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4)を参照してください。 

ヒント: フィルター処理の条件のみコンテンツのマイクロソフトのチームにすなわちチャットし、チャネルのメッセージ、会議、および呼び出しの種類の MicrosoftTeams を使用できます。 

## <a name="ediscovery"></a>電子情報開示

電子情報開示とは、訴訟または調査における開示要求に対応するための電子保持情報 (ESI) の電子的な特定、収集、生成です。 ケース管理、保存、検索、分析、およびチームのデータのエクスポート機能が含まれます。 これには、チャット、メッセージング、ファイル、会議および呼び出しの概要が含まれます。 チーム会議と呼び出しは、呼び出し、会議で発生したイベントの概要が作成され、電子的証拠開示で利用できます。 

セキュリティとコンプライアンスのセンターでは、電子的証拠開示を行い、コンプライアンス チームのコンテンツをコンテンツの検索を実行する方法の詳細については、次のリンクを参照してください。 

[電子情報開示](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[コンテンツの検索](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

お客様が活用して、インプレース電子証拠開示、または [高度な電子的証拠開示] ごとの要件 (https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)。 次の表にその違いを示します。


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


## <a name="legal-hold"></a>訴訟ホールド

訴訟、中には多くの場合必要なことすべてのデータは、ユーザー (管理者) に関連付けられているまたはチームが保持されます immutably の場合の証拠として使えるようにします。 これは、法的保存要件に、ユーザー (ユーザーのメールボックス) またはチームを配置することによって実現されます。 インプレース (対象となるクエリまたはフィルター処理されたコンテンツからメールボックスまたはサイト コレクションのサブセット) を押しながらまたは訴訟 (メールボックスまたはサイト コレクション全体) を押したままにチーム内のすべてのチームを配置すると、保留リストは、グループのメールボックスに置かれます。 これにより、エンド ・ ユーザーを削除または、グループのメールボックスに取り込まれ、チャネルのメッセージを編集した場合でもそのコンテンツのコピーを変更できないが維持され、eDisscovery の検索で使用できます。 訴訟ホールドの場合は、通常、電子情報開示ケース内に適用されます。 参照してください[この](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a)記事を保存し、Office 365 のセキュリティとコンプライアンス ・ センター内の保留の詳細についてのヘルプです。 

## <a name="information-protection-architecture-for-microsoft-teams"></a>マイクロソフトのチームの情報保護アーキテクチャです。 

次の図では、チームのファイルとメッセージの交換および SharePoint の両方をチームのデータの取り込みフローを示します。 

![Exchange と SharePoint への Teams データのワークフローの図。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

次の図では、チームの会議および Exchange への呼び出し元のデータの取り込みの流れを示します。

![チームの会議および Exchange データの呼び出し元のワークフローの図です。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> できるチームのコンテンツを検出するのには 24 時間の遅延です。

<a name="licensing"></a>ライセンス
---------------

情報保護機能については、Office 365 サブスクリプションとそれに関連付けられたスタンドアロン ライセンスによって利用可能な機能セットが決定します。

|情報保護機能   |Office 365 Business Essentials   |Office 365 Business Premium   |Office 365 Enterprise E1   |Office 365 Enterprise E3/E4   |Office 365 Enterprise E5   |
|---|---|---|---|---|---|
|アーカイブ|-  |-   |-   |はい   |はい   |
|インプレース電子情報開示|-   |-   |-   |はい   |はい   |
|Advanced eDiscovery|-   |-   |-   |-   |はい   |
|訴訟ホールド|-   |-   |-   |はい   |はい   |
|コンプライアンスのコンテンツ検索|- |- |- |はい |はい |
|監査と報告|はい |あり |あり |あり |はい |
|条件付きアクセス* |はい |あり |あり |あり |はい |
> [!NOTE]
> \*条件付きアクセスには追加のライセンスが必要


| |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |判断ポイント         |お客様の組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?         |
|![次のステップ アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |次のステップ         |組織の現在のライセンスを確認し、コンプライアンスとセキュリティに関するすべてのビジネス要件を満たしていることを確認します。         |

これらの機能を有効にする前に Office 365 の管理ページで、セキュリティとコンプライアンス センターへのアクセスがあることを確認します。 既定では、テナントの管理者がアクセス権を持ちます。

コンテンツの検索と電子的証拠開示では、セキュリティとコンプライアンス センターで支援を必要はありません。

<a name="location-of-data-in-teams"></a>Teams のデータの場所
-------------------------

Teams のデータはご利用の Office 365 テナントに関連付けられている地理的領域内に存在します。 現時点では、チームでは、オーストラリア、カナダ、インド、日本、英国、南北アメリカ、APAC、および EMEA 地域をサポートしています。 

> [!IMPORTANT]
> チーム現在提供していますデータ常駐オーストラリア、カナダ、インド、日本、および英国で新しいテナントのみにします。 新しいテナントは、Teams に 1 人のユーザーもサインインさせていない任意のテナントとして定義されます。 APAC 地域に格納されている、チームのデータが存在するオーストラリア、インド、日本からの既存のテナントが続行されます。 カナダ、英国内の既存のテナントは、南北アメリカに格納されているデータには、EMEA 地域では、それぞれ。

インドおよび英国での Teams によるデータ常駐の開始の詳細については、Ansuman Acharya のブログの投稿記事「[Microsoft Teams launches India Data Residency, other geos coming soon (Microsoft Teams でのデータ常駐がインドで開始、その他の地域でも近日中に開始)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)」をお読みください。 

チームのカナダのデータの常駐サービスの詳細については、[マイクロソフト チーム カナダ データ常駐の起動、オーストラリアおよび日本の準備中](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)に、Varun Sagar のブログ投稿を参照してください。 

チームのオーストラリアと日本のデータ常駐サービスの起動に関する詳細については、[マイクロソフト チームの起動のオーストラリアと日本のデータの常駐](https://go.microsoft.com/fwlink/?linkid=867773)Varun Sagar のブログ記事を参照してください。 

どの地域、テナントのデータを格納するを表示するにはを参照して、 [Office 365 管理者センター](https://portal.office.com/adminportal/home) > **設定** > **組織プロファイル**です。 下にスクロールして [**データの場所**] に移動します。 

![Office 365 の管理ページで、チームを含む、データの場所テーブルのスクリーン ショットです。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>チームの条件付きのアクセス ポリシーの動作方法
-------------------------

マイクロソフトのチームに大きく依存して SharePoint Online では、Exchange Online と Skype オンライン ビジネスの会議、予定表、相互運用機能のチャット、ファイル共有と同様に、中核となる生産性の向上をします。 これらのクラウド アプリケーションに設定されている条件付きのアクセス ポリシーは、ユーザー直接サインインしているマイクロソフトのチームのすべてのクライアントの場合、マイクロソフトのチームに適用されます。 

マイクロソフト チームは Azure Active Directory のアクセスの条件付きポリシーでクラウド アプリケーションとして個別にサポートします。 マイクロソフト チームのクラウド アプリケーションに設定されている条件付きのアクセス ポリシーは、ユーザーがサインインするときに、マイクロソフトのチームに適用されます。 ただし、Exchange Online や SharePoint Online のような他のアプリケーションに適切なポリシー、ユーザー可能性がありますもがなければこれらのリソースに直接アクセスすること。 Azure ポータル内の条件付きのアクセス ポリシーの設定に関する詳細についてを参照して: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Windows と Mac のデスクトップ クライアントをマイクロソフトのチームでは、最新の認証をサポートします。 現代の認証は、サインインのベースに、Azure Active ディレクトリ認証ライブラリ (ADAL) を Microsoft Office クライアント アプリケーションのプラットフォーム間で表示されます。

マイクロソフト チームのデスクトップ アプリケーションでは、AppLocker をサポートします。  AppLocker の前提条件の詳細についてを参照してください: AppLocker を使用するための要件 (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)。

<a name="privacy-in-teams"></a>Teams でのプライバシー
--------------------------

Office 365 のユーザーとして、お客様はデータを所有して管理します。Microsoft が、お客様が購読しているサービスの提供以外の目的でお客様のデータを使用することはありません。Microsoft は、サービス プロバイダーとして、広告や他のサービスと無関係な目的のためにお客様のメール、ドキュメント、チームを調べることはありません。Microsoft はアップロード済みのコンテンツに対してアクセス権を持ちません。OneDrive for Business や SharePoint Online と同様に、お客様のデータはテナント内にあります。

信頼およびセキュリティに関連する情報について詳しくは、[Office 365 セキュリティ センター](https://go.microsoft.com/fwlink/?linkid=855779)にアクセスしてください。 Teams は Office 365 セキュリティ センターと同じガイダンスと原則に従っています。
