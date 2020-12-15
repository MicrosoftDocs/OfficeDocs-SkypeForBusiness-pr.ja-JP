---
title: Teams での承認アプリケーションの可用性
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Microsoft Teams での承認アプリケーションの可用性について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675195"
---
# <a name="teams-approvals-app-availability"></a>Teams 承認アプリの可用性

[!INCLUDE [preview-feature](includes/preview-feature.md)]

承認アプリは、すべての Microsoft Teams ユーザーの個人用アプリとして使用できます。
承認アプリは、監査、コンプライアンス、責任、ワークフローを Teams の構造化された承認と非構造化承認の両方に表示する簡単な方法を提供します。

 ![承認アプリを表示する](media/approvals-selection.png)

ユーザーは承認アプリをピン留めして、メニュー バーに保存できます。

 ![[ピン] オプションが表示された承認アプリ](media/approvalApp-pin.png)

承認アプリから最初に作成された承認は、既定の Common Data Service (CDS) 環境での承認ソリューションのプロビジョニングをトリガーします。 承認アプリから作成された承認は、既定の CDS 環境に保存されます。

この記事では、承認アプリの要件とロールについて説明します。

## <a name="required-permissions-and-licenses"></a>必要なアクセス許可とライセンス

承認アプリを使用するには、次のアイテムに対するアクセス許可が必要です。

- Microsoft CDS データベースを作成する権限。

- アカウント [のflow.microsoft.com](https://flow.microsoft.com/)

- ターゲット環境の管理者ロール。

- [Power Automate、Office](https://docs.microsoft.com/power-automate/get-started-approvals)365、または Dynamics 365 のライセンス。

## <a name="storage-with-cds"></a>CDS 付きストレージ

共通データ モデル (CDM) は、CDS のビジネス アプリケーションや分析アプリケーションで使用される共有データ言語です。 Microsoft とパートナーが公開する標準化された拡張データ スキーマのセットで構成され、アプリケーションやビジネス プロセス全体でデータとその意味の一貫性を保ちます。 Microsoft Power [Platform の共通データ モデルの詳細については、以下を参照してください](https://docs.microsoft.com/power-automate/get-started-approvals)。

承認ワークフローの [詳細については、以下を参照してください](https://docs.microsoft.com/power-automate/modern-approvals)。

## <a name="approvals-teams-app-permissions"></a>承認 Teams アプリのアクセス許可

承認チーム アプリでは、次の機能にアクセスできます。

- 指定したメッセージとデータを受信します。

- メッセージと通知を送信します。

- Teams が提供するヘッダーなしで個人用アプリとダイアログを表示します。

- 名前、メール アドレス、会社名、優先する言語などのプロファイル情報にアクセスします。

- チャネルでチーム メンバーが提供するメッセージとデータを受信します。

- チャネルでメッセージと通知を送信します。

- チームの情報にアクセスします。
  - チーム名
  - チャネル リスト
  - リスト (チーム メンバーの名前とメール アドレス)

- チームの情報を使用して、チームに連絡します。

## <a name="disable-the-approvals-app"></a>承認アプリを無効にする

承認アプリは既定で使用できます。 Teams 管理センターでアプリを無効にできます。

  1. Teams 管理センターにサインインします。

  2. Teams アプリ **を展開し、[** アプリの **管理] を選択します**。

  3. 承認アプリを検索します。

![[Teams アプリ] と [アプリの管理] が>管理センターのナビゲーションを表示する](media/manage-approval-apps.png)

  4. [承認] を選択します。

  5. トグルを選択して、組織のアプリを無効にします。

![承認アプリの詳細を表示する](media/approvals-details.png)

## <a name="retention-policy"></a>アイテム保持ポリシー

承認アプリから作成された承認は既定の CDS 環境に保存されます。現時点ではバックアップはサポートされていません。 環境をバックアップおよび復元 [する方法の詳細については、Power Platform \| Microsoft Docs を参照してください](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)。

## <a name="auditing"></a>監査

承認アプリは、Microsoft 365 セキュリティ/コンプライアンス センター内の監査イベントをログに記録します。 監査ログを表示できます。

1. M365 コンプライアンス サイトに移動します。

2. [監査] **セクションを選択** します。

3. Microsoft Teams の承認アクティビティ **の下でアクティビティを検索します**。

次のアクティビティを検索できます。

- 新しい承認要求を作成する

- 承認要求の詳細を表示する

- 承認された承認要求

- 承認要求が却下されました

- 承認要求が取り消されました

- 共有承認要求

- 承認要求に添付されたファイル

- 再割り当てされた承認要求

- 承認要求に電子署名が追加されました

Flow 内で他の監査承認にアクセスするには、プライマリ承認エンティティの承認、承認要求、承認応答の既定の環境で監査を有効にして構成します。 作成、更新、削除の操作は、承認レコードの監査可能なイベントです。 セキュリティとコンプライアンスの [データとユーザー アクティビティの監査について詳しくは、Power Platform Microsoft Docs をご \| 覧ください](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)。

監査は [、Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)セキュリティ/コンプライアンス センターでさらにカスタマイズできます。

1. 事前に構成されたレポートを使用するには、Office 365 セキュリティ/コンプライアンスにサインインします。

2. [検索 **と調査&選択します**。

3. 監査ログを検索し **、[Dynamics 365 アクティビティ] タブを選択** します。

[Microsoft Dataverse とモデル駆動型アプリのアクティビティ ログの詳細については、Power Platform を参照してください](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)。

## <a name="security"></a>セキュリティ

Teams 承認アプリから、ユーザーは新しい承認を作成し、送信および受信した承認を表示するアクセス権を持っています。 他のユーザーが作成した承認へのアクセス権は、ユーザーが回答者または要求の閲覧者ではない限り、アクセスできません。

> [!Note]
> 承認が作成されたチャットまたはチャネルの一部である場合、ユーザーにはリクエストの閲覧者の役割が与えられる。 承認が作成された際にロールが与えらなかった場合、要求に対してアクションを実行することはできません。
