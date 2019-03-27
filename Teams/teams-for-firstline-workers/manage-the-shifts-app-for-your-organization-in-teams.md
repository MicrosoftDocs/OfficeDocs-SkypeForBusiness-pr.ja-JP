---
title: Microsoft Teams で組織のシフト アプリを管理する
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Teams で組織の現場担当者向けにシフト アプリを設定および管理する方法を学びます。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fdb34f0cc1df67350ec5224e02d5922d49b2663f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891637"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織のシフト アプリを管理する

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 スケジュールやタスク管理などの StaffHub の機能は Microsoft Teams に構築中です。 現場担当者向けの追加機能は、段階的に Teams に公開されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

## <a name="overview-of-shifts"></a>シフトの概要
Microsoft Teams のシフト アプリでは、現場担当者との連絡と同期を常に行えます。このアプリは、チームが迅速で効果的な時間管理とコミュニケーションを行えるようにモバイル ファーストで構築されています。 シフトを使用すると、現場担当者とそのマネージャーは自分のモバイル デバイスを使用して、スケジュールを管理し、連絡を取ることができます。 

- マネージャーは、チームのシフト スケジュールを作成、更新、および管理します。 マネージャーは、メッセージを 1 人のユーザーに送ることも ("床が汚れています" など)、チーム全体に送ることもできます ("地区本部長があと 20 分で到着します" など)。 マネージャーは、ポリシー ドキュメント、ニュース速報、およびビデオを送信することもできます。 
- 従業員は、自分の今後のシフトの確認、自分の他にその日にスケジュールが入っている従業員の表示、シフトの入れ替えや申し出のリクエスト、および休暇のリクエストが行えます。 

シフトでは現在、ゲスト ユーザーはサポートされていませんのでご注意ください。 つまり、Teams でゲスト アクセスがオンになっていると、チームのゲストをシフト スケジュールに追加することも、チームのゲストがシフト スケジュールを使用することもできません。 

## <a name="availability-of-shifts"></a>シフトの可用性

シフトは Teams を含むすべての Office 365 サブスクリプションでご利用いただけますが、いくつかの例外があります。 例外となるのは、米国の Government Community Cloud (GCC) および無料版の Teams です。 シフトは、Office 365 US Government または Teams の無料サービスでは利用できません。

Teams を含む Office 365 サブスクリプションの一覧など、Teams のライセンスの詳細については、「[Teams の Office 365 ライセンス](../Office-365-licensing.md)」を参照してください。

## <a name="location-of-shifts-data"></a>シフトのデータの場所

現在、シフトのデータは、北米、西ヨーロッパ、およびアジア太平洋にあるデータ センターの Azure に保存されています。 データが保存される場所の詳細については、「[データの保存場所](http://o365datacentermap.azurewebsites.net/)」を参照してください。

## <a name="set-up-shifts"></a>シフトのセットアップ

### <a name="enable-or-disable-shifts-in-your-organization"></a>組織のシフトを有効または無効にする

シフトは、組織内のすべての Teams ユーザーに対して既定で有効になっています。 Microsoft 365 管理センターで、ご自分の組織についてアプリをオフまたはオンにすることができます。

1. Office 365 管理者アカウントで Microsoft 365 管理センターにサインインします。
2. **[設定]**  >  **[サービスとアドイン]**  >  **[Microsoft Teams]** の順に移動します。 
3. **[テナント レベルの設定]** で **[アプリ]** を選択し、**[既定のアプリ]** の下で、**[シフト]** チェック ボックスをオンにするかオフにすることで、アプリのオンとオフを切り替えます。 

    ![[既定のアプリ] セクションのスクリーンショット](../media/firstline-worker-enable-disable-shifts.png "シフト アプリを含むアプリの一覧を示す、Microsoft 365 管理センターの [既定のアプリ] セクションのスクリーンショット")

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>FirstLineWorker のアプリ セットアップ ポリシーを使用してシフトを Teams にピン留めする

> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

アプリ セットアップ ポリシーを使用すると、組織内のユーザーにとって最も重要なアプリを強調表示するように Teams をカスタマイズできます。 ポリシーに設定されたアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。 
 
Teams には組み込みの FirstLineWorker アプリ セットアップ ポリシーが含まれており、これを組織内の現場担当者に割り当てることができます。 既定では、ポリシーにはアクティビティ、シフト、チャット、および通話の各アプリが含まれています。 

FirstLineWorker ポリシーを表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]**  >  **[アプリ セットアップ ポリシー]** の順に移動します。

![Microsoft Teams 管理センターの FirstLineWorker アプリ セットアップ ポリシーのスクリーンショット](../media/firstline-worker-app-setup-policy.png "Microsoft Teams 管理センターの FirstLineWorker アプリ セットアップ ポリシーのスクリーンショット")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>個々のユーザーに FirstLineWorker ポリシーを割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[割り当てられているポリシー]** の隣にある **[編集]** を選択します。
3. **[Teams アプリのセットアップ ポリシー]** で、**[FirstLineWorker]** を選び、**[保存]** を選択します。

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a>FirstLineWorker アプリのセットアップ ポリシーをグループ内のユーザーに割り当てる

Azure Active Directory PowerShell for Graph モジュールおよび Skype for Business PowerShell モジュールに接続することで、セキュリティ グループなどのグループ内のユーザーに FirstLineWorker アプリのセットアップ ポリシーを割り当てることができます。 PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](../teams-powershell-overview.md)」を参照してください。

この例では、FirstLineWorker アプリのセットアップ ポリシーを Contoso 現場チーム グループのすべてのユーザーに割り当てます。

> [!NOTE]
> 「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。

特定のグループの GroupObjectId を取得します。
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
指定したグループのメンバーを取得します。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
FirstLineWorker アプリのセットアップ ポリシーにグループ内のすべてのユーザーを割り当てます。
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。

## <a name="related-topics"></a>関連項目
- [現場担当者とマネージャー向けのシフトに関するヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
