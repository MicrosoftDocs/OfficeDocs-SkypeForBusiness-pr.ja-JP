---
title: 組織のシフトアプリを管理する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織の Firstline Worker の Teams でシフトアプリを設定および管理する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c2ca24f2176547f83efb6bdce591ac71d516dca9
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416887"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

> [!IMPORTANT]
> 2020年6月30日の有効な Microsoft StaffHub は廃止されます。 Microsoft Teams で StaffHub 機能を構築しています。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 2020年6月30日に、StaffHub はすべてのユーザーに対して機能しなくなります。 ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

## <a name="overview-of-shifts"></a>シフトの概要

Microsoft Teams の [シフト] アプリでは、Firstline Worker が接続され、同期されます。モバイル機能を搭載しているので、チームの時間管理とコミュニケーションを迅速かつ効率的に行うことができます。 [シフト] では、最初の行の作業者とそのマネージャーは、モバイルデバイスを使ってスケジュールを管理し、連絡を取ることができます。

- マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。 マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。 マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。 
- 従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストが行えます。 

シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。 つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。 

## <a name="availability-of-shifts"></a>シフトの可用性

シフトは、Teams が利用できるすべての Enterprise Sku で利用できます。

## <a name="location-of-shifts-data"></a>シフトのデータの場所

現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。 データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。

## <a name="set-up-shifts"></a>シフトのセットアップ

### <a name="enable-or-disable-shifts-in-your-organization"></a>組織のシフトを有効または無効にする

シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 Microsoft Teams 管理センターの [[アプリの管理](../../manage-apps.md)] ページで、組織レベルでアプリをオンまたはオフにすることができます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。
2. アプリの一覧で、次のいずれかの操作を行います。

    - 組織のシフトをオフにするには、[シフト] アプリを検索して選択し、[**ブロック**] をクリックします。
    - 組織のシフトを有効にするには、[シフト] アプリを検索して選択し、[**許可**] をクリックします。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>組織内の特定のユーザーのシフトを有効または無効にする

組織内の特定のユーザーによるシフトの使用を許可またはブロックするには、[[アプリの管理](../../manage-apps.md)] ページで組織のシフトが有効になっていることを確認してから、カスタムのアプリのアクセス許可ポリシーを作成して、それらのユーザーに割り当てます。 詳細については、「 [Teams でアプリのアクセス許可ポリシーを管理](../../teams-app-permission-policies.md)する」を参照してください。

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>FirstlineWorker アプリのセットアップポリシーを使用して、チームにシフトをピン留めする

アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。 ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。 
 
Teams には、組織内の Firstline Worker に割り当てることができる、FirstlineWorker アプリセットアップポリシーが組み込まれています。 既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。 

Firstlineworker ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[ **Teams アプリ**  >  **アプリセットアップポリシー**] に移動します。

![FirstlineWorker アプリセットアップポリシーのスクリーンショット](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの FirstlineWorker アプリセットアップポリシーのスクリーンショット")

#### <a name="assign-the-firstlineworker-policy-to-users"></a>FirstlineWorker ポリシーをユーザーに割り当てる

FirstlineWorker アプリのセットアップポリシーを1人のユーザーに割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。
3. [**アプリセットアップポリシー**] で [ **firstlineworker**] を選択し、[**適用**] をクリックします。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。
2. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。
3. [**設定の編集**] をクリックし、[**アプリセットアップポリシー**] で [ **firstlineworker**] を選択し、[**適用**] をクリックします。  

または、次の操作も実行できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**  >  **セットアップポリシー**] に移動します。
2. ポリシー名の左側をクリックして、FirstlineWorker ポリシーを選択します。
3. [**ユーザーを管理**] を選択します。
4. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、[**適用**] を選択します。

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a>FirstlineWorker アプリのセットアップポリシーをグループのユーザーメンバーに割り当てる

最初の Lineworker アプリのセットアップポリシーは、セキュリティグループなどのグループのユーザーメンバーに割り当てることができます。これには、Graph モジュール用の Azure Active Directory PowerShell と Skype for Business PowerShell モジュールに接続します。 PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](../../teams-powershell-overview.md)」を参照してください。

この例では、Contoso Firstline チームグループのすべてのユーザーメンバーに FirstlineWorker アプリセットアップポリシーを割り当てます。

> [!NOTE]
> 「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。

特定のグループの GroupObjectId を取得します。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
指定したグループのメンバーを取得します。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
グループのすべてのユーザーメンバーに FirstlineWorker アプリセットアップポリシーを割り当てます。
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。

## <a name="search-the-audit-log-for-shifts-events"></a>監査ログでシフトイベントを検索する

**(プレビュー段階)**

監査ログを検索して、組織内のシフトアクティビティを表示できます。  監査ログを検索し、監査ログに記録されている[シフトアクティビティ](../../audit-log-events.md#shifts-in-teams-activities)の一覧を表示する方法の詳細については、「 [Teams のイベントの監査ログを検索](../../audit-log-events.md)する」を参照してください。

監査ログを検索する前に、まず[セキュリティ & コンプライアンスセンター](https://protection.office.com)で監査を有効にする必要があります。 詳細については、「[監査ログの検索を有効または無効に](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)する」を参照してください。 監査データは、監査を有効にした時点でのみ利用可能であることに注意してください。

## <a name="related-topics"></a>関連項目

- [Firstline Worker のヘルプをシフトする](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [チームのユーザーにポリシーを割り当てる](../../assign-policies.md)
