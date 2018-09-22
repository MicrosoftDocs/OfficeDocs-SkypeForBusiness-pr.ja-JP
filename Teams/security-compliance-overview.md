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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 331e4d600c26123079315a77d5d99f17496c12a9
ms.sourcegitcommit: 6212645c485c41aafe1206bf7d39171ce35837b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2018
ms.locfileid: "24967432"
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

## <a name="retention-policies"></a>リテンション ・ ポリシー

チームの会話は、永続的な既定値が永久に保持されています。 リテンション ・ ポリシーの導入により、管理者を構成できます (保存と削除の両方) の保持ポリシー セキュリティとコンプライアンス センターでチーム チャット、およびチャネルのメッセージを。 これにより、組織のコンプライアンス (つまり、保持ポリシーを特定の期間のデータを保持] または [特定の期間の後、責任と見なされる場合データ (つまり、削除ポリシーを削除します。 チーム ・ リテンション ・ ポリシーは、データを削除するときはチーム サービスすべて永続的なデータ ストレージの場所から削除されますを確認します。 

チームのリテンション ・ ポリシーを管理するための設定と Office 365 のセキュリティとコンプライアンス センターは、**データ ・ ガバナンス**のコマンドレットを使用して、 > **保存**します。

チーム ・ リテンション ・ ポリシーはサポートしています。 
    
- 保存: 指定された期間のチームのデータを保持して、何もしません。
- 保存とし、[削除: 指定した期間のチームのデータを保持し、削除
- 削除: 指定した期間の後のチームのデータを削除します。

チーム ・ リテンション ・ ポリシーをサポートしていません。

- チャットのチームとチームのチャネル メッセージの場所に高度な保存ポリシーが適用されません。
- 30 日以内の期間

管理者は、チームのプライベート チャット (チャットが 1:1 または 1 対多) とチャネルのメッセージをチームの別の保存ポリシーを設定できます。 多くの場合、組織は複数のチャネル メッセージは、複数のプロジェクトに関連する会話は、通常よりも負債としてプライベート チャット データを検討してください。 セキュリティとコンプライアンス ・ センター、**データの管理**でこれらのポリシーを設定します > **保存**します。 **チャネルのメッセージをチーム**と**チームのチャット**をオンにし、(もは次の図に示すように) これらの場所の保存ポリシーを定義し、します。 

**チームのメッセージのチャネル**を有効にするとき、チームはこのポリシーを適用するを指定できます。 たとえば、X、Y、および Z は、チームの管理者ことができます 1 年間でこれらのチームを個別に選択)、削除ポリシーを設定、チームの残りの部分に 3 年間の削除ポリシーを適用します。 

特定のユーザーを選択し、一意の保持ポリシーを適用することによって**チームのチャット**の同じことを行うことができます。 

![Exchange と SharePoint への Teams データのワークフローの図。](media/Retention-Policies.png)


> [!IMPORTANT]
> チームのチャネルのメッセージの場所とチーム チャットの場所は、Exchange Online のメールボックス (メールボックスをユーザーとグループ) に格納されているチームの会話にしか対応します。 メッセージは、すべての関連する記憶域、つまりメールボックス、基板、およびチャット サービスから削除されます。 
> 
> ビジネスおよび SharePoint の OneDrive に保存されている、チームのファイルの保存ポリシーを管理するために、リテンション ・ ポリシーを使用します。




仕様では、削除チーム ファイルのポリシーを構成して SharePoint Online OneDrive の事業所です。 その結果、ポリシーがそれらのメッセージは削除する前に、チーム チャットやチャネルのメッセージで参照されているファイルを削除できなかったことができます。 この例では、ファイルは表示されますチームのメッセージが、ファイルをクリックすると、(に起こる場合も、ポリシーがない場合はファイルが SharePoint Online またはビジネスのための OneDrive から手動で削除する場合)、"ファイルが見つかりません"というエラーが表示されます。


Office 365 用のリテンション ・ ポリシーの構成の詳細については、[保存ポリシーの概要](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)を参照してください。
 

## <a name="retention-policies-faq"></a>リテンション ・ ポリシーに関する FAQ

### <a name="what-types-of-policies-can-i-setup-in-retention-policies-and-how-do-they-work"></a>リテンション ・ ポリシーでどのような種類のポリシーがセットアップされ、どのように動作するでしょうか。

SSecurity/コンプライアンス ・ センターで、チーム、またはその他のワークロードでは、リテンション ・ ポリシーを設定すると 2 つの主な種類のポリシーを設定できます。 
- 保存: これらのポリシーでは、エンド ユーザー ツールで何が起きても、時間の特定の期間のデータが保持されることを確認します。 これらは、コンプライアンス上の理由からデータが保存され、この時点までには、電子的証拠開示に利用可能な有効期限が切れることを確認します。 時間を経過した後、ポリシーは何もしない、またはデータを削除するかどうかを指定できます。 チームでエンド ・ ユーザー、チームのメッセージを削除する場合でも、7 年間、保持ポリシーを作成する場合これらのメッセージは保持されます電子的証拠開示の 7 年間。
- 削除: これらのポリシーでは、データが組織の負債ではないことを確認します。 、指定した期間の後は、チームに関連するすべての記憶域からデータが削除されます。 

### <a name="can-we-include-teams-in-org-wide-policies"></a>チームを組織全体のポリシーは含めることができますか。 

いいえ、されていません。 チームの場所の行またはチームのこれらのコマンドレットを使用して、チームのチャットおよびチャネルのメッセージの特定のポリシーを作成する必要があります:[新しい TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [新規 TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)。 これらのコマンドレットでは、get し、同様のバージョンを設定します。

### <a name="are-these-retention-policies-retroactive"></a>これらのアイテム保持ポリシーは、さかのぼって適用しますか。 

います。 60 日よりも古いデータを削除する保持ポリシーを作成する場合は、60 日以上前に作成したチームのデータが削除されます。 

### <a name="what-is-the-default-retention-policy"></a>デフォルトの保存ポリシーとは何ですか。 

既定では、チーム チャット、チャネル、およびファイルのデータは永久保持します。 ユーザーは、何かを削除できますが、リテンション ・ ポリシーがない場合は、チームのデータ (ユーザーおよびグループ) は、Exchange オンライン メールボックスにアーカイブが常に、電子的証拠開示のないままです。 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>ユーザーまたはチームのポリシーのセットを対象することができますか。 

はい、次のように実行します。 ポリシーの作成ウィザードのステップでは、場所では、または (**チームは、メッセージをチャネル**) のチームまたはユーザー (**チーム チャット**) を除外して組織の対象となるポリシーを作成できます。 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>グループのメールボックスの場所の行とチームのチャネルのメッセージの場所の行を使用して、リテンション ・ ポリシーでの主な違いは何ですか。 

Exchange Online のメールボックスのグループとユーザーのメールボックスの場所の行を使用する場合、チームのデータが指定されたメールボックスから削除されます。 ただし、メールボックスからこの、だけデータを削除します。 チャット サービスなど、他のチームのデータは、削除されません。 チーム ・ リテンション ・ ポリシーを使用して、チームのすべてのデータを適切に管理することをお勧めします。 チーム ・ リテンション ・ ポリシーは、すべてストレージの場所: メールボックス、チャット サービス、チーム クライアントからチームのデータを削除します。 

注: チームは、保持ポリシーの機能の起動、唯一のチーム ポリシーが Exchange メールボックスの場所 (ユーザーまたはグループ) 内に格納されているチームの項目を削除します。 メールボックスでは、他のポリシー設定は、チームのアイテムに適用できません。 これまでは、true ですが保持ポリシーの機能の起動が修正されています。 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>どうなる Skype ビジネス オンラインでチームの相互運用機能チャット – のリテンション ・ ポリシーによって影響をあるか

はい、オンライン ビジネスとチームの相互運用機能のチャットの Skype 同様に動作します。 ビジネス オンライン チャットの Skype は、チームには、そのチーム チャットのスレッド内のメッセージとなり、取得、適切なメールボックスに取り込まれ。 動作: を同じフロー、チームの削除ポリシーはチームのスレッドからこれらのメッセージを削除します。 ただし、会話の履歴がオンになって Skype のオンライン ビジネスの場合は、オンライン ビジネスのクライアント側の Skype からそれらを保存しているメールボックスにこのチャットのデータはチーム ・ リテンション ・ ポリシーによって処理されません。

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>どうすればこれらのセキュリティとコンプライアンスの中心のコマンドレットを使用しますか。 どう使用する必要がありますか。 

そうですよ。 [セキュリティとコンプライアンス センターの Powershell コマンドレット]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)を使用するチーム ・ リテンション ・ ポリシーを作成できます。 オンライン Exchange コマンドレットがないことを覚えておいてください。 ここでは、コマンドレットのチームを作成しました。 従う既存の用語とスタイルから保存のコマンドレットが現在利用可能なセキュリティとコンプライアンスの中心にします。

|ポリシー|ルール|
|---|---|
|[新しい-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [新しい-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[セット TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [セット TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[削除 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [削除 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>チームのさまざまな期間、どちらかを wins での複数の保存ポリシーがある場合ですか。

[リテンション ・ ポリシーの原則](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)に従ってし、も実行することをお勧めします。 短い答えは次のとおりです。 
-   削除を優先、常に情報を保持
-   最長の保存期間を常に優先します。
-   明示的なインクルードが場所で暗黙の信頼を優先します。
-   最短の削除期間 wins



## <a name="retention-policies-known-issues"></a>リテンション ・ ポリシーに関する既知の問題

1. 選択チームのチャネル メッセージの場所の行で、チームでもないチームには、Office 365 のグループを参照してください可能性があります。 これは、将来的に解決されます。

1. チームのチャットの場所の行で [ユーザーの選択] の下、来園者とユーザーのメールボックスではないを表示ことがあります。 リテンション ・ ポリシーを来園者を設定する必要はないし、これらの一覧から削除することに努めています。 

1. Exchange のライフ サイクルのアシスタント (ELC) は毎日実行されるが、7 日間の SLA。 結果として、60 日より古いアイテムを削除するのには、チームの保持ポリシーがあれば、これらの項目でした永続化を 67 日間のことができます。 新しい状況ではありません - 交換モデルに依存しています。 もちろん、ほとんどの場合、時間はかかりません。


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |判断ポイント         |組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?         |
|![次のステップ アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |次のステップ         |必要なセキュリティとコンプライアンスの機能を文書化します。         |

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
