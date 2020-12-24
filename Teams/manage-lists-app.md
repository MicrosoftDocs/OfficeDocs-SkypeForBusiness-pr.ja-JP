---
title: 組織のリスト アプリを管理する
author: cichur
ms.author: v-cichur
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 組織内のユーザーの Teams でリスト アプリを管理する方法について学習します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8ba05b4922b25cc6294fc85f1264a44bdb031660
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731125"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のリスト アプリを管理する

## <a name="overview-of-lists"></a>リストの概要

Microsoft Teams のリスト アプリは、組織内のユーザーが情報を追跡し、作業を整理し、ワークフローを管理するのに役立ちます。 リストを使用すると、ユーザーはカスタマイズ可能なビュー、ルール、警告を使用して、問題、資産、ルーチン、連絡先、在庫、インシデント、ローン、患者などのデータを追跡し、チームの全員の同期を維持できます。

Teams では、ユーザーはチャネル内のタブとしてリストにアクセスします。 タブ **+** ギャラリーをクリックして開き、新しいリスト アプリ タブ インスタンスをチャネルに追加して開始します。

![タブ ギャラリーのリスト アプリ](media/lists-tab.png)

ユーザーは、新しいリストを作成したり、同じチーム内またはアクセス権を持つ別の SharePoint サイトから既存のリストを固定することができます。 新しいリストは、一から作成したり、組み込みのテンプレートから作成したり、既存のリストの構造に基づいて作成したり、Excel ブックからデータをインポートしたりして作成できます。 リスト アプリは、Teams デスクトップ、Web、モバイル クライアントで利用できます。

![リスト アプリでリストを作成する方法](media/lists-create-list.png)

## <a name="templates"></a>テンプレート

リスト内のテンプレートは、ユーザーの一般的な情報追跡シナリオに合わせて調整されます。 各テンプレートには、定義済みのリスト構造、フォーム レイアウト、書式設定オプションがリスト ビューと詳細ビュー レベルの両方に用意され、ユーザーがすぐに使い始めることができます。 テンプレートを選択すると、ユーザーはリストの外観とサンプル データのプレビューを取得します。 次に、組織内のチームがリストで定義済みのテンプレートを使用する方法の例を示します。

- 問題を追跡し、問題管理テンプレートを使用してそれらを終了します。
- イベント日程テンプレートを使用して、すべてのイベントの詳細を整理します。
- 患者テンプレートを使用して、医療組織の医療チームの患者のニーズと状態を記録し、ケアを監視および調整します。
- ローン申請の状況を、[ローン] テンプレートで追跡します。

## <a name="example-scenario"></a>シナリオ例

地域内でメールの並べ替えと配信を行うのは、現地の郵便会社が担当します。 毎日の目標を確認し、お知らせを共有し、既知のインシデントについて話し合うチームが、毎日のオフィスにいます。

連絡を受け取ると、メール会社はメールを受け取り、配送ルートを開始します。 インシデントは、自動車の事故、犬関連の問題、社会不安の原因など、ルート上で発生する可能性があります。 メールの携帯電話会社がインシデントに遭遇すると、モバイル デバイス上の Teams を使用してインシデントの詳細を記録します。これは、チーム チャネルのリストで追跡されます。 フィールド内のメール通信事業者を含むチームの全員が、この情報を確認し、最新の情報を取得できます。

Teams に移行する前に、メールの通信事業者は、Excel スプレッドシートに入力されたインシデントを報告するために、ハード コピーフォームを完成するために、郵便会社に戻る必要がありました。 Teams は、メール携帯電話会社に最初にモバイル機能を提供し、リストを使用して発生したインシデントを現場で報告し、インシデントの詳細をチーム メンバーと共有し、チャネル上でインシデントに関する会話を行い、インシデントを解決に追い込む操作を行います。

## <a name="what-you-need-to-know-about-lists"></a>リストについて知る必要がある情報

### <a name="lists-is-available-in-every-team-and-channel"></a>リストは、すべてのチームとチャネルで利用できます

リストは、すべての Teams ユーザーにプレインストールされ、すべてのチームとチャネルのタブ ギャラリーで直接利用できます。 つまり、ユーザーは Teams アプリ ストアにアクセスしてインストールする必要が生じます。

### <a name="lists-and-sharepoint"></a>リストと SharePoint

リスト データは SharePoint Online チーム サイトに保存されます。 SharePoint Online が Teams とやり取りする方法の詳細については [、「SharePoint Online](SharePoint-OneDrive-interact.md)と OneDrive for Business が Teams と対話する方法」を参照してください。

SharePoint で設定されたアクセス許可は、リスト アプリで作成されたリストに適用されます。 既定では、リストは属するサイトから権限を継承します。 これらのアクセス許可は、リストを作成または編集できるかどうかなど、ユーザーが実行できる操作の種類に適用されます。 詳細については [、「SharePoint のアクセス許可レベル」および「SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) Server のユーザー権限と権限 [レベル」を参照してください](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)。

特定のシナリオでは、ユーザーがリストで実行できる操作を制限する必要がある場合があります。 たとえば、チームのユーザーがリスト ビューを編集すると、すべてのチーム メンバーに対して変更され、チーム所有者または特定のチーム メンバーだけがリスト ビューを編集できるとします。 詳細については、「SharePoint リストまたはライブラリ [の権限をカスタマイズする」を参照してください](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)。

> [!NOTE]
> この時点では、チームの所有者とメンバーのアクセス許可は、リストまたはリスト アプリの動作を制御するチーム サイトのアクセス許可にリンクされるものではありません。 ただし、お客様からのフィードバックと使用状況に基づいて、これは製品の今後の反復について考慮されます。  

### <a name="limitations"></a>制限事項

リストを使用すると、ユーザーはデスクトップ、Web、モバイルの操作環境を利用できます。 Teams モバイル クライアントのリストを使用して、ユーザーが新しいリストを作成したり、既存のリストを固定したりできないという点を知る必要があります。 Teams モバイル クライアントでリストを表示または編集するには、最初に Teams デスクトップまたは Web クライアントのリストを使用してリストを作成または追加する必要があります。

ゲストはリストを作成または削除できない。 既存のリストにリスト アイテムを追加したり、リスト アイテムに関する新しい会話を開始したり、リスト アイテムに関する既存の会話に返信することができます。

### <a name="lists-and-the-sharepoint-app"></a>リストと SharePoint アプリ

組織内のユーザーが SharePoint アプリを使用してリストを作成した場合、それらのリストは、ユーザーからの操作を行わずにリストに自動的に移動されます。 Teams で最適で豊富なリスト統合エクスペリエンスを得る場合は、リスト アプリを使用して既存のリストを固定します。

## <a name="set-up-lists"></a>リストを設定する

### <a name="enable-or-disable-lists-in-your-organization"></a>組織内のリストを有効または無効にする

リストは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 Microsoft Teams 管理センターの [アプリの管理] ページ[](manage-apps.md)で、組織レベルでアプリをオフまたはオンにできます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。
2. 次のいずれかの操作を行います。

    - 組織のリストをオフにする場合は、リスト アプリを検索して選び、[ブロック] をクリック **します**。
    - 組織のリストを有効にする場合は、リスト アプリを検索して選び、[許可] をクリック **します**。

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>組織内の特定のユーザーのリストを有効または無効にする

組織内の特定のユーザーによるリストの使用を許可またはブロックするには、[アプリの管理] ページで組織の[](manage-apps.md)リストが有効になっていることを確認し、カスタム アプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てる必要があります。 詳細については、「Teams でアプリ [のアクセス許可ポリシーを管理する」を参照してください](teams-app-permission-policies.md)。

## <a name="search-the-audit-log-for-list-events"></a>リスト イベントの監査ログを検索する

リストはエンタープライズ レベルの監査で有効になっているので、セキュリティ/コンプライアンス センターの監査ログでリストとリスト アイテム&できます。 詳細については、セキュリティ/コンプライアンス センターで監査ログを検索する [&参照してください](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。

Teams のリスト アプリに関連する監査イベントの一覧については [、SharePoint リストアクティビティを参照してください](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)。

監査ログを検索するには、まずセキュリティ/コンプライアンス センターで監査 [&があります](https://protection.office.com)。 監査データは、監査を有効にした時点からのみ利用できます。

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automate、Power Apps、Graph API

リストでは [、ワークフロー用の Power Automate](https://docs.microsoft.com/power-automate/flow-types) とリスト [フォーム用の Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) がサポートされます。 デベロッパーはリスト API を [使用して、Microsoft](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) Graph を介してソースとしてリスト データを接続できます。

## <a name="give-feedback-or-report-an-issue"></a>フィードバックを送信する、または問題を報告する
  
フィードバックを送信したり、問題を報告したりするには、Teams の左側のナビゲーションの下部にある [ヘルプ] をクリックし、[問題の報告] を **選択します**。 [ **リスト]** を選択し、発生している問題に関するフィードバックまたは詳細を入力します。

## <a name="related-topics"></a>関連項目

- [ヘルプ ドキュメントの一覧](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
