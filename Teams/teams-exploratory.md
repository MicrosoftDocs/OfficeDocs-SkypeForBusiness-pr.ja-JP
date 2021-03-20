---
title: Microsoft Teams Exploratory エクスペリエンスを管理する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams ライセンスが付与されていない Microsoft 365 または Office 365 ユーザーは、Exploratory Teams ライセンスを開始できます。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb5e415128baae6bfc458b5d0000128010a9b5cd
ms.sourcegitcommit: 71b9b5ec80014bd25758493bc06d633c4eac735c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50867046"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a>Microsoft Teams Exploratory ライセンスを管理する

Microsoft Teams Exploratory エクスペリエンスを使用すると、Azure Active Directory (Azure AD) を持ち、Teams のライセンスを取得していない組織内のユーザーは、Teams の Exploratory エクスペリエンスを開始できます。 管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。 以前の [Microsoft の商用クラウド試用版](iw-trial-teams.md)は、 Teams Exploratory エクスペリエンスに変更になりました。

> [!NOTE]
> テナントごとに 100 の Microsoft Teams Exploratory ライセンスの制限があります。

## <a name="whats-in-the-teams-exploratory-experience"></a>Teams Exploratory エクスペリエンスの内容

Teams Exploratory エクスペリエンスの一部として管理者に表示されるサービス プランは次のとおりです。

- Exchange Online (プラン 1)
- Microsoft 365 または Office 365 のフロー
- MyAnalytics を利用した分析情報
- Microsoft Forms (プラン E1)
- Microsoft Planner
- Microsoft Search
- Microsoft StaffHub
- Microsoft Stream for Microsoft 365 E1 SKU および Office 365 E1 SKU <sup>1</1>
- Microsoft Teams
- Microsoft 365 または Office 365 のモバイル デバイス管理
- Office Mobile Apps for Office 365
- Office Online
- PowerApps for Microsoft 365 または Office 365
- SharePoint Online (プラン 1)
- Sway
- To-Do (プラン 1)
- Whiteboard (プラン 1)
- Yammer Enterprise

  <sup>1</sup> Microsoft Stream の使用から [会議の記録用の OneDrive for Business および SharePoint](tmr-meeting-recording-change.md) への変更は段階的なアプローチになります。 起動時に、この機能に加入できるようになります。 ストリームの使用を続ける場合は、11 月に脱退する必要があります。 2021 年の初めには、新しい会議を記録するためにすべてのお客様に OneDrive for Business と SharePoint を使用していただく必要があります。

## <a name="whos-eligible"></a>対象者

Teams Exploratory エクスペリエンスの抽出条件を満たすユーザーは、次のとおりです。

- 管理された Azure AD ドメインのメールアドレスをお持ちである。
- 有料サブスクリプションのテナントに所属している。
- アクティブな Teams ライセンスを持っていない。
- ライセンスの割り当てポリシーが作成されたテナントに存在していない。

ユーザーが (Microsoft 365 管理センターで) アプリや試用版にサインアップできるようにする必要があります。 詳細については、この記事で後述する「[Teams Exploratory エクスペリエンスを管理する](#manage-the-teams-exploratory-experience)」を参照してください。

## <a name="who-isnt-eligible"></a>対象外

抽出条件を満たさないユーザーは、次のとおりです。

- 現在までに有料版、無料版、試用版ライセンスでの Teams を所有していたことがある
- 特別 COVID プランを 1 回以上利用した/受け取ったテナントに所属している。

シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、組織は試用版の対象ではありません。

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法

対象となるユーザーは、デスクトップまたは Web から Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして Teams Exploratory エクスペリエンスにサインアップできます。 現時点では、モバイルを通した探索の有効化はサポートされていません。 サインアップを完了すると、このライセンスは自動的に割り当てられ、組織内の誰かが初めて Teams Exploratory エクスペリエンスを開始すると、テナント管理者に、メール通知が送信されます。

## <a name="manage-the-teams-exploratory-experience"></a>Teams Exploratory エクスペリエンスを管理する

Teams Exploratory エクスペリエンスは個々のエンド ユーザーが開始するためのものであり、エンド ユーザーの従業員に代わってこのサービスを開始することはできません。

Teams Exploratory エクスペリエンスには Exchange Online ライセンスが付属していますが、管理者が割り当てるまでユーザーに割り当てられません。 ユーザーにまだ Exchange ライセンスがなく、管理者がまだ Exchange Online ライセンスを割り当てていない場合、ユーザーは Teams で会議をスケジュールできず、他の Teams の機能を利用できない可能性があります。

管理者は、**試用版のアプリとサービス** スイッチを使用して、エンド ユーザーが組織内で Teams Exploratory エクスペリエンスを実行できないようにすることができます。

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>ユーザーが試用版アプリおよびサービスをインストールできないようにする

ユーザーが試用版アプリとサービスをインストールできるようにする機能をオフにすると、そのユーザーは Teams Exploratory エクスペリエンスを実行できなくなります。

1. Microsoft 365 管理センターから **[設定]** > **[組織の設定]** に移動し、**[サービス]** を選択し、**[ユーザー所有のアプリとサービス]** を選択します。

    ![管理センターの [サービス] ページ](media/iw-trial-services.png)

2. **[ユーザーに試用版アプリとサービスのインストールを許可する]** のチェック マークをクリアします。

    ![管理センターの [ユーザーが所有するアプリとサービス] ページ](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 組織が Teams Exploratory エクスペリエンスの対象外の場合は、「**ユーザーが試用版アプリとサービスをインストールできるようにする**」オプションは表示されません。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Teams が含まれているライセンスを持つユーザーの利用可能性を管理する

Teams が含まれているライセンスの割り当てられたユーザーは、Teams Exploratory エクスペリエンスの対象になりません。 Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。 サービス プランが無効になっている場合、ユーザーはサインインできず、Teams Exploratory エクスペリエンスは利用できません。 管理者権限が必要です。

Teams へのアクセスをオフにするには:

1. Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。

2. ユーザーの名前の横にあるボックスを選択します。

3. [**製品のライセンス**] 行で、[**編集**] を選びます。

4. **[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。

    ![管理センターの [製品ライセンス] ページ。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Teams Exploratory エクスペリエンスをすでに使用しているユーザーの Teams の可用性を管理する

ユーザーが Teams Exploratory エクスペリエンスを実行している場合は、ライセンスまたはサービス プランを削除することでそれをオフにできます。 管理者権限が必要です。

Teams Exploratory エクスペリエンスのライセンスをオフにするには:

1. Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。

2. ユーザーの名前の横にあるボックスを選択します。

3. [**製品のライセンス**] 行で、[**編集**] を選びます。

4. [**製品ライセンス**] ウィンドウで、この Exploratory ライセンスのトグルを [**オフ**] に切り替えます。

    > [!NOTE]
    > Teams Exploratory のトグル スイッチは、組織の最初のユーザーが Teams Exploratory エクスペリエンスを起動した後に表示されます。

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Teams Exploratory ライセンスを持つユーザーの Teams を管理する

Teams Exploratory ライセンスを持つユーザーは、通常の有料ライセンスを持つユーザーと同じように管理できます。 詳細については、「[組織の Teams 設定を管理する](enable-features-office-365.md)」を参照してください。

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Teams Exploratory ライセンスからユーザーをアップグレードする

Teams Exploratory ライセンスからユーザーをアップグレードするには(管理者権限が必要です)、次のタスクを実行します。

1. Teams が含まれているサブスクリプションを購入します。

2. ユーザーから Teams Exploratory のサブスクリプションを削除します。

3. 新しく購入したライセンスを割り当てます。

詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。

> [!NOTE]
> Teams Exploratory ライセンスが終了し、ユーザーが Teams を含むサブスクリプションにすぐにアップグレードされない場合は、30 日間の猶予期間が設定され、30 日経過後にデータが削除されます。 ユーザーは引き続き Azure Active Directory に残ります。 ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、猶予期間のタイムフレーム内にユーザーが追加された場合はすべてのコンテンツが残ります。

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>従来の Microsoft Teams の商用クラウドの試用版のライセンスはどうなりますか

2020 年 2 月から、対象ユーザーは最新の Microsoft Teams Exploratory エクスペリエンスの使用を開始できます。 従来の Teams の商用クラウドの試用版のライセンスはすべて、試用版の有効期限が切れる前に自動的に新しいサービスに変換されます。

ユーザーが初めて、有効期限が切れた Teams の商用クラウドの試用版にサインインすると、そのユーザーに Teams Exploratory ライセンスが自動的に割り当てられます。 ユーザーがサインインするまで、変換されません。

### <a name="remove-a-teams-exploratory-license"></a>Teams Exploratory ライセンスを削除する

- Powershell を使用してこのライセンスを削除する場合は、次を参照してください :「[Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」

- 管理ポータルからこのライセンスを削除する場合は、「[組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。

## <a name="what-is-the-data-retention-policy"></a>データ保持ポリシーとは

詳細については、「[Microsoft 365 サブスクリプション情報](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)」を参照してください。

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Teams Exploratory エクスペリエンスの利用可能期間

2021 年初頭の時点で、Teams Exploratory は、すべての新規のお客様を対象とした (最初のユーザー サインアップから) 12 か月のサブスクリプションとして利用できます。 新しい Teams Exploratory サブスクリプションは、組織の最初のユーザーが Teams Exploratory にサインアップしたときに開始され、12 か月後に期限切れになります。 有効期限は同じテナントのすべてのユーザーに適用されます。12 か月の期間は最初のユーザーのサインアップした日付から開始します。

> [!NOTE]
> エクスペリエンスの終了日は組織レベルで構成されます。つまり、同じ組織内のすべてのユーザーに適用されます。 たとえば、ユーザー 1 が 2021 年 1 月 1 日にサブスクリプションにサインアップしたとします。 これにより、2021 年 12 月 31 日を終了日とするサブスクリプションが開始されます。 別のユーザーであるユーザー 2 が、2021 年 10 月 1 日にサブスクリプションにサインアップした場合、 ユーザー 2 は Teams Exploratory を 2 か月間使用できます。これは、ユーザー 1 と同じ組織のサブスクリプションでは、終了日が 2021 年 12 月 31 日となるためです。

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a>12 か月の Teams Exploratory エクスペリエンスの終了時に管理者がすべきこと

12 か月のサブスクリプションの終了時に、管理者はすべての Teams Exploratory ユーザーを Teams を含む有料ライセンスに変換する必要があります。 ユーザー エクスペリエンスの中断を回避するために、Teams Exploratory サブスクリプションの有効期限が切れる前にこの処理を完了しておくことが重要です。


> [!NOTE]
> お客様は、以前の Exploratory 試用版ライセンスの有効期限が終了してから 3 か月間、新しい Exploratory 試用版ライセンスは無効になり、起動がブロックされます。

詳細については、この記事の上記の「[Teams Exploratory ライセンスからユーザーをアップグレードする](#upgrade-users-from-the-teams-exploratory-license))」を参照してください。

