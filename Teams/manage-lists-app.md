---
title: 組織のリストアプリを管理する
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 組織内のユーザーのために Teams のリストアプリを管理する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 56197394d4b4edbe714b5edab62f905e1c520ede
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790479"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のリストアプリを管理する

## <a name="overview-of-lists"></a>リストの概要

Microsoft Teams のリストアプリは、組織内のユーザーが情報を追跡したり、作業を整理したり、ワークフローを管理したりするのに役立ちます。 リストを使用すると、問題、資産、ルーチン、連絡先、在庫、インシデント、ローン、患者などのデータを、カスタマイズ可能なビュー、ルール、およびアラートを使って追跡できます。

Teams では、ユーザーはリストをチャネル内のタブとしてアクセスします。 クリック **+** するとタブギャラリーが開き、新しいリストアプリのタブインスタンスをチャネルに追加して、開始することができます。 

![タブギャラリーのリストアプリのスクリーンショット](media/lists-tab.png)

ユーザーは、同じチーム内から、またはアクセス権のある別の SharePoint サイトから、新しいリストを作成したり、既存のリストをピン留めしたりできます。 新しいリストは、組み込みのテンプレートから、既存のリストの構造に基づいて、または Excel ブックからデータをインポートすることによって、最初から作成することができます。 リストアプリは、Teams のデスクトップ、web、モバイルクライアントで利用できます。

![リストアプリでリストを作成する方法を示すスクリーンショット](media/lists-create-list.png)

## <a name="templates"></a>Templates

リスト内のテンプレートは、ユーザー向けの一般的な情報管理シナリオに合わせてカスタマイズされます。 各テンプレートには、事前に定義されたリスト構造、フォームレイアウト、および書式設定オプションが用意されています。リストビューと詳細表示レベルでは、ユーザーがすぐに使い始めるのに役立ちます。 テンプレートを選択すると、リストがどのように表示されるか、サンプルデータと共に、ユーザーにプレビューが表示されます。 組織内のチームがリストで定義済みのテンプレートを使用する方法の例を次に示します。

- 問題を追跡して、問題追跡テンプレートを使用して、問題を解決します。
- すべてのイベントの詳細をイベント旅程テンプレートで整理します。
- 患者のテンプレートを使用して、医療機関における医療チームの患者のニーズと状態を記録して、治療を監視および調整します。
- ローン申請の状態をローンテンプレートで追跡します。

## <a name="example-scenario"></a>シナリオ例

地元の投稿会社は、地域内でのメールの並べ替えと配信を担当します。 毎朝、office の投稿には、毎日の目標を確認し、お知らせを共有し、既知の問題について話し合うためのチーム huddle があります。

Huddle は、メールキャリアがメールを受け取り、配信ルートを開始します。 障害は、自動車事故、犬関連の問題、ソーシャル unrest 受取拒否など、ルートに沿って発生する可能性があります。 メールキャリアでインシデントが発生した場合は、モバイルデバイスで Teams を使って、チームチャネルのリストで追跡されたインシデントの詳細を記録します。 フィールドのメールキャリアを含む、チームの全員がこの情報を表示して、最新情報を入手できます。

チームに移行する前に、メールの運送会社は、Excel スプレッドシートに入力されたインシデントを報告するために、ハードコピーフォームを完成させるために、office のポストオフィスに戻っている必要がありました。 チームでは、メールキャリアを携帯電話にすることができます。これは、リストを使って、発生時にフィールドのインシデントを報告し、チームメンバーとインシデントの詳細を共有し、問題を解決するための問題を解決することを意図しています。

## <a name="what-you-need-to-know-about-lists"></a>リストについて知っておくべきこと

### <a name="lists-is-available-in-every-team-and-channel"></a>すべてのチームおよびチャネルでリストを使用できます

リストはすべての Teams ユーザー用にプレインストールされており、すべてのチームとチャネルのタブギャラリーで直接利用できます。 これは、ユーザーが Teams app store に移動してインストールする必要がないことを意味します。

### <a name="lists-and-sharepoint"></a>リストと SharePoint

リストデータは、SharePoint Online チームサイトに保存されます。 SharePoint Online と Teams の相互作用の詳細については、「 [Sharepoint online と OneDrive For business が teams を操作する方法](SharePoint-OneDrive-interact.md)」を参照してください。

SharePoint で設定した権限は、リストアプリで作成されたリストに適用されます。 既定では、リストは、所属するサイトから権限を継承します。 これらのアクセス許可は、リストを作成または編集できるかどうかなど、ユーザーが実行できる操作の種類を制御します。 詳細については、「sharepoint [のアクセス許可レベル](https://docs.microsoft.com/sharepoint/understanding-permission-levels) 」および「 [sharepoint Server でのユーザーのアクセス許可レベル](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)」を参照してください。

特定のシナリオでは、ユーザーがリストで実行できる操作を制限することができます。 たとえば、チームのユーザーがリストビューを編集して、すべてのチームメンバーに対してそれを変更し、チーム所有者または特定のチームメンバーのみがリストビューを編集できるようにします。 詳細については、「 [SharePoint リストまたはライブラリの権限をカスタマイズ](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)する」を参照してください。

> [!NOTE]
> この時点では、チームの所有者とメンバーのアクセス許可は、リストアプリまたはリストアプリの動作を管理するチームサイトのアクセス許可にリンクされません。 ただし、お客様のフィードバックと使用状況に基づいて、この製品は今後のイテレーションで考慮されます。  

### <a name="limitations"></a>伴う

リストを使用すると、ユーザーはデスクトップ、web、モバイル環境を利用できます。 ユーザーは、チームのモバイルクライアントのリストを使って、新しいリストを作成したり、既存のリストをピン留めしたりすることはできないことを知っておくことが重要です。 Teams モバイルクライアントでリストを表示または編集するには、まず Teams のデスクトップまたは web クライアントのリストを使用してリストを作成または追加する必要があります。

ゲストは、リストを作成したり、削除したりすることはできません。 リストアイテムを既存のリストに追加したり、リストアイテムに関する新しい会話を開始したり、リストアイテムに関する既存の会話に返信したりすることができます。

### <a name="lists-and-the-sharepoint-app"></a>リストと SharePoint アプリ

組織内のユーザーが SharePoint アプリを使用してリストを作成した場合、ユーザーからのアクションを必要とせずに、リストに自動的に移動されます。 Teams で最も機能が豊富なリストの統合エクスペリエンスを実現するには、Lists アプリを使用して、既存のリストをピン留めします。

## <a name="set-up-lists"></a>リストを設定する

### <a name="enable-or-disable-lists-in-your-organization"></a>組織内のリストを有効または無効にする

リストは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 Microsoft Teams 管理センターの [ [アプリの管理](manage-apps.md) ] ページで、組織レベルでアプリをオンまたはオフにすることができます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ** の管理] に移動  >  **Manage apps** します。
2. 次のいずれかの操作を行います。

    - 組織のリストをオフにするには、リストアプリを検索して選択し、[ **ブロック** ] をクリックします。
    - 組織のリストを有効にするには、リストアプリを検索して選択し、[ **許可** ] をクリックします。

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>組織内の特定のユーザーのリストを有効または無効にする

組織内の特定のユーザーによるリストの使用を許可またはブロックするには、[ [アプリの管理](manage-apps.md) ] ページで組織のリストが有効になっていることを確認してから、カスタムのアプリのアクセス許可ポリシーを作成して、それらのユーザーに割り当てます。 詳細については、「 [Teams でアプリのアクセス許可ポリシーを管理](teams-app-permission-policies.md)する」を参照してください。

## <a name="search-the-audit-log-for-list-events"></a>監査ログでリストイベントを検索する

エンタープライズレベルの監査ではリストが有効になっているため、セキュリティ & コンプライアンスセンターの監査ログでリストとリストアイテムのイベントを検索することができます。 詳細については、「 [セキュリティ & コンプライアンスセンターで監査ログを検索](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)する」を参照してください。

Teams のリストアプリに関連する監査イベントの一覧については、「 [SharePoint リストアクティビティ](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)」をご覧ください。

監査ログを検索する前に、まず [セキュリティ & コンプライアンスセンター](https://protection.office.com)で監査を有効にする必要があります。 監査データは、監査を有効にした時点でのみ利用可能であることに注意してください。

## <a name="power-automate-power-apps-and-graph-api"></a>Power オートメーション、Power Apps、Graph API

リストフォームのワークフローと[Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)の[power オートメーション](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint)をサポートしています。 開発者は、 [LISTS API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) を使用して、リストデータをソースとして Microsoft Graph で接続できます。

## <a name="give-feedback-or-report-an-issue"></a>フィードバックを送信する、または問題を報告する
  
フィードバックを送信したり、問題を報告したりするには、Teams の左側のナビゲーションの下部にある [ **ヘルプ** ] をクリックして、[ **問題の報告** ] を選択します。 [ **リスト** ] を選択し、お客様のフィードバックまたは発生した問題に関する詳細情報を入力します。

## <a name="related-topics"></a>関連項目

- [ヘルプドキュメントを一覧表示する](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
