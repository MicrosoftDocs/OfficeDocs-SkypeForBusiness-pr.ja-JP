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
description: 組織内のユーザー向けに Teams でリスト アプリを管理する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365initiative-lists
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: aa26dd24fac90b023453e3834baf51da6f292082
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092255"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

## <a name="overview-of-lists"></a>リストの概要

Microsoft Teams のリスト アプリは、組織内のユーザーが情報を追跡し、仕事を整理し、ワークフローを管理するのに役立ちます。 リストを使用すると、ユーザーはカスタマイズ可能なビュー、ルール、アラートを使用して、問題、資産、ルーチン、連絡先、インベントリ、インシデント、ローン、患者などのデータを追跡し、チーム内のすべてのユーザーが同期を保つことができるようになります。

Teams では、ユーザーはチャネル内のタブとしてリストにアクセスします。 **[+]** をクリックしてタブ ギャラリーを開き、開始するチャネルに新しいリスト アプリのタブ インスタンスを追加します。

![タブ ギャラリーのリスト アプリ](media/lists-tab.png)

ユーザーは、新しいリストを作成したり、同じチーム内またはアクセス権のある別の SharePoint サイトから既存のリストをピン留めしたりすることができます。 新しいリストは、既存のリストの構造をベースにして、または Excel ワークブックからデータをインポートして、組み込みのテンプレートを基に一から作成することができます。 リスト アプリは Teams のデスクトップ、Web、モバイル クライアントで利用できます。

![リスト アプリでリストを作成する方法](media/lists-create-list.png)

## <a name="templates"></a>テンプレート

リストのテンプレートは、ユーザーにとって一般的な情報追跡シナリオに合わせてカスタマイズされています。 各テンプレートには、定義済みのリスト構造、フォームのレイアウト、リスト ビューと詳細ビューの両方のレベルでの書式設定オプションが付属しており、ユーザーがすぐに使用を始められるようになっています。 テンプレートを選択すると、ユーザーはいくつかのサンプル データとともにリストがどのように表示されるかをプレビューすることができます。 以下に、組織内のチームがリストの定義済みのテンプレートを使用する方法についての例を示します。

- 問題の追跡テンプレートを使用して問題を追跡し、解決に導きましょう。
- イベントの日程表テンプレートを使用して、すべてのイベントの詳細情報を整理しましょう。
- 患者テンプレートを使用して、医療関係組織の医療チームの患者のニーズや状態を記録し、ケアの監視や調整を行いましょう。
- ローン テンプレートを使用してローンの申請状況を追跡しましょう。

## <a name="example-scenario"></a>シナリオ例

地元の郵便局は、その地区の郵便物を仕分けして配達する役割を担っています。 毎朝、郵便局にはチーム メンバーが集まり、その日の目標を確認したり、情報を共有したり、既知のインシデントについて話し合ったりしています。

打ち合わせ後、郵便配達員が郵便物を受け取り、配達ルートへの移動を開始します。 インシデントはルート上で発生する可能性があります。たとえば、車両事故、犬に関連する問題、社会問題に対する抗議運動などです。 配達員がインシデントに遭遇した場合、モバイル デバイス上の Teams を使用してインシデントの詳細を記録します。そしてそのインシデントは、チーム チャネル内のリストで追跡されます。 現場の郵便配達員を含むチームの全員がこの情報を確認しながら、常に情報を得ることができます。

Teams に移行する前であれば、郵便配達員は郵便局に戻り、Excel のスプレッドシートに入力するための印刷用紙にインシデントに関する報告を記入しなければなりませんでした。 Teams は、リストを使用して現場で発生したインシデントを報告したり、インシデントの詳細をチーム メンバーと共有したり、チャネル上で会話したり、インシデントを解決したりすることができるモバイル ファーストな使用体験を郵便配達員に提供します。

## <a name="what-you-need-to-know-about-lists"></a>リストについて知っておくべきこと

### <a name="lists-is-available-in-every-team-and-channel"></a>リストは、すべてのチームおよびチャネルで使用できます。

リストはすべての Teams ユーザーにプリインストールされており、すべてのチームとチャネルのタブ ギャラリーから直接利用できます。 これは、ユーザーが Teams アプリ ストアに行かなくてもインストールできることを意味しています。

### <a name="lists-and-sharepoint"></a>リストと SharePoint

リストのデータは SharePoint Online のチーム サイトに保存されます。 SharePoint Online と Teams の相互作用については、「[Teams との SharePoint Online と OneDrive for Business の相互作用](SharePoint-OneDrive-interact.md)」を参照してください。

SharePoint で設定したアクセス許可は、リスト アプリで作成したリストに適用されます。 既定では、リストは、ユーザーが所属するサイトから権限を継承します。 これらのアクセス許可は、ユーザーがリストの作成や編集をできるかどうかなど、ユーザーが実行可能なアクションの種類を管理します。 詳細については、「[SharePoint でのアクセス許可レベル](/sharepoint/understanding-permission-levels)」と「[SharePoint Server でのユーザー アクセス許可とアクセス許可レベル](/sharepoint/sites/user-permissions-and-permission-levels)」を参照してください。

特定のシナリオでは、ユーザーがリストで実行可能なアクションを制限する必要がある場合があります。 たとえば、あるチーム内のユーザーがすべてのチーム メンバーに変更が適用されるリスト ビューの編集を行う場合や、チームの所有者や特定のチーム メンバーにのみリスト ビューの編集を許可する必要がある場合などです。 詳細については、「[SharePoint リストまたはライブラリのアクセス許可をカスタマイズする方法](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)」を参照してください。

> [!NOTE]
> 現時点では、チーム内の所有者やメンバーのアクセス許可は、リストやリスト アプリの動作を管理するチーム サイトのアクセス許可とは一切リンクしていません。 ただし、これについては、お客様からのフィードバックやご利用状況を元に今後のイテレーションで検討していきます。  

### <a name="limitations"></a>制限事項

リストを使用すると、ユーザーはデスクトップ、Web、モバイルでの利用環境を得ることができます。 重要な点として、Teams モバイル クライアントではリストを使用した新しいリストの作成や、既存のリストのピン留めができないという点が挙げられます。 Teams モバイル クライアントでリストを表示または編集するには、最初に Teams デスクトップ クライアントまたは Web クライアントでリストを使用して作成または追加を行う必要があります。

ゲストがリストを作成したり、削除したりすることはできません。既存のリストにリスト アイテムを追加したり、リスト アイテムに関する新しい会話を開始したり、リスト アイテムに関する既存の会話に返信したりすることができます。

### <a name="lists-and-the-sharepoint-app"></a>リストと SharePoint アプリ

組織内のユーザーが SharePoint アプリを使用してリストを作成した場合、そのリストはユーザーが操作を行わなくても自動的にリストに移動されます。 Teams でリッチなリストの統合エクスペリエンスを得るには、リスト アプリを使用して既存のリストをピン留めします。

## <a name="set-up-lists"></a>リストのセットアップ

### <a name="enable-or-disable-lists-in-your-organization"></a>組織のリストを有効または無効にする

リストは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 組織レベルでアプリをオフまたはオンにするには、Microsoft Teams 管理センターの [[アプリの管理]](manage-apps.md) ページで行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリの管理]** の順に移動します。
2. 次のいずれかの操作を行います。

    - 組織のリストをオフにするには、リスト アプリを検索して選択し、**[ブロック]** をクリックします。
    - 組織のリストをオンにするには、リスト アプリを検索して選択し、**[許可]** をクリックします。

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>組織内の特定のユーザーのリストを有効または無効にする

組織内の特定のユーザーによるリストの使用を許可またはブロックするには、[[アプリの管理]](manage-apps.md) ページで組織のリストがオンになっていることを確認してからカスタムのアプリのアクセス許可ポリシーを作成し、それらのユーザーに割り当てます。 詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

## <a name="search-the-audit-log-for-list-events"></a>Teams でリスト イベントの監査ログを検索する

リストは、企業レベルの監査で有効になっているので、セキュリティ/コンプライアンス センターの監査ログでリストやリスト アイテムのイベントを検索できます。 詳細については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)」を参照してください。

Teams のリスト アプリに関連する監査イベントの一覧については、「[SharePoint リスト アクティビティ](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)」を参照してください。

監査ログを検索できるようになるには、最初に[セキュリティ/コンプライアンス センター](https://protection.office.com) で監査をオンにする必要があります。 利用できる監査データは、監査を有効にした時点以降のデータのみであることにご注意ください。

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automate、Power Apps、Graph API

リストはワークフローについては [Power Automate](/power-automate/flow-types) を、リスト フォームについては [Power Apps](/powerapps/maker/canvas-apps/customize-list-form) をサポートしています。 開発者は[リスト API](/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) を使用して、Microsoft Graph を介してリストのデータにソースとして接続することができます。

## <a name="give-feedback-or-report-an-issue"></a>フィードバックの提供/問題の報告
  
フィードバックを送信したり、問題を報告したりするには、Teams の左側のナビゲーションの下部にある **[ヘルプ]** をクリックしてから、**[問題の報告]** を選択します。 **[リスト]** を選択し、フィードバックや発生している問題についての詳細情報を入力します。

## <a name="related-topics"></a>関連項目

- [リストのヘルプ ドキュメント](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)