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
ms.openlocfilehash: f27dc7e8772e25b6dcc91622cabec421e058af7b
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031483"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Microsoft Teams Exploratory ライセンスを管理する
=======================================================

Microsoft Teams Exploratory エクスペリエンスを使用すると、Azure Active Directory (Azure AD) を持ち、Teams のライセンスを取得していない組織内のユーザーは、Teams の Exploratory エクスペリエンスを開始できます。 管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。 以前の [Microsoft の商用クラウド試用版](iw-trial-teams.md) は、 Teams Exploratory エクスペリエンスに変更になりました。

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

  <sup>1</sup> Microsoft Stream の使用から [会議の記録用の OneDrive for Business および SharePoint](tmr-meeting-recording-change.md) への変更は段階的なアプローチになります。 起動時にこの機能に加入できるようになります。 ストリームの使用を続ける場合は、11 月に脱退する必要があります。 2021 年の初めには、新しい会議を記録するためにすべてのお客様に OneDrive for Business と SharePoint を使用していただく必要があります。

## <a name="whos-eligible"></a>対象者

Teams Exploratory エクスペリエンスの抽出条件を満たすユーザーは、次のとおりです。

- 管理された Azure AD ドメインのメールアドレスをお持ちである。
- 有料サブスクリプションのテナントに所属している。

ユーザーが (Microsoft 365 管理センターで) アプリや試用版にサインアップできるようにする必要があります。 詳細については、この記事で後述する「[Teams Exploratory エクスペリエンスを管理する](#manage-the-teams-exploratory-experience)」を参照してください。

## <a name="who-isnt-eligible"></a>対象外

抽出条件を満たさないユーザーは、次のとおりです。

- 現在までに有料版、無料版、試用版ライセンスでの Teams を所有していたことがある 
- 特別 COVID プランを 1 回以上利用した/受け取ったテナントに所属している。

シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、組織は試用版の対象ではありません。

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法

対象となるユーザーは、Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして Teams Exploratory エクスペリエンスにサインアップできます。 このライセンスは自動的に割り当てられ、組織内の誰かが初めて Teams Exploratory エクスペリエンスを開始すると、テナント管理者に、メール通知が送信されます。

## <a name="manage-the-teams-exploratory-experience"></a>Teams Exploratory エクスペリエンスを管理する

Teams Exploratory エクスペリエンスは個々のエンド ユーザーが開始するためのものであり、エンド ユーザーの従業員に代わってこのサービスを開始することはできません。

Teams Exploratory エクスペリエンスには Exchange Online ライセンスが付属していますが、管理者が割り当てるまでユーザーに割り当てられません。 ユーザーにまだ Exchange ライセンスがなく、管理者がまだ Exchange Online ライセンスを割り当てていない場合、ユーザーは Teams で会議をスケジュールできず、他の Teams の機能を利用できない可能性があります。

管理者は、 **試用版のアプリとサービス** スイッチを使用して、エンド ユーザーが組織内で Teams Exploratory エクスペリエンスを実行できないようにすることができます。

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>ユーザーが試用版アプリおよびサービスをインストールできないようにする

ユーザーが試用版アプリとサービスをインストールできるようにする機能をオフにすると、そのユーザーは Teams Exploratory エクスペリエンスを実行できなくなります。

1. Microsoft 365 管理センターから **[設定]** > **[組織の設定]** に移動し、 **[サービス]** を選択し、 **[ユーザー所有のアプリとサービス]** を選択します。

    ![管理センターの [サービス] ページ](media/iw-trial-services.png)

2. **[ユーザーに試用版アプリとサービスのインストールを許可する]** チェック ボックスをクリアします。

    ![管理センターの [ユーザーが所有するアプリとサービス] ページ](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 組織が Teams Exploratory エクスペリエンスの対象外の場合は、「 **ユーザーが試用版アプリとサービスをインストールできるようにする** 」オプションは表示されません。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Teams が含まれているライセンスを持つユーザーの利用可能性を管理する

Teams が含まれているライセンスの割り当てられたユーザーは、Teams Exploratory エクスペリエンスの対象になりません。 Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。 サービス プランが無効になっている場合、ユーザーはサインインできず、Teams Exploratory エクスペリエンスは利用できません。 管理者権限が必要です。

Teams へのアクセスをオフにするには:

1. Microsoft 365 管理センターで、 **[ユーザー]** > **[アクティブ ユーザー]** を選択します。

2. ユーザーの名前の横にあるボックスを選択します。

3. [ **製品のライセンス** ] 行で、[ **編集** ] を選びます。

4. **[製品ライセンス]** ウィンドウで、 **[オフ]** に切り替えます。

    ![管理センターの [製品ライセンス] ページ。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Teams Exploratory エクスペリエンスをすでに使用しているユーザーの Teams の可用性を管理する

ユーザーが Teams Exploratory エクスペリエンスを実行している場合は、ライセンスまたはサービス プランを削除することでそれをオフにできます。 管理者権限が必要です。

Teams Exploratory エクスペリエンスのライセンスをオフにするには:

1. Microsoft 365 管理センターで、 **[ユーザー]** > **[アクティブ ユーザー]** を選択します。

2. ユーザーの名前の横にあるボックスを選択します。

3. [ **製品のライセンス** ] 行で、[ **編集** ] を選びます。

4. [ **製品ライセンス** ] ウィンドウで、この Exploratory ライセンスのトグルを [ **オフ** ] に切り替えます。

    >[!Note]
    >Teams Exploratory のトグル スイッチは、組織の最初のユーザーが Teams Exploratory エクスペリエンスを起動した後に表示されます。

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

Microsoft Teams Exploratory エクスペリエンスは、次の **契約応当日** 、または 2021 年 1 月以降の **更新日** まで追加料金なしで利用可能です。 この時点で、Microsoft Exploratory エクスペリエンス ライセンスのエンド ユーザーは、Teams を含む有料のライセンスに移行する必要があります。 その後に開始したすべての Microsoft Exploratory エクスペリエンス ライセンスは、次の **契約応当日** 、または **更新日** まで追加料金なしで引き続き利用できます。

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a>エンド ユーザーが、Microsoft Teams Exploratory エクスペリエンスを契約日、または更新日の前に開始した場合は、どうなりますか

Microsoft Teams Exploratory エクスペリエンス ライセンスの開始が、 **契約応当日** 、または **更新日** の 90 日以内であれば、次の契約応当日、更新日まで有料のライセンスに移行する必要はありません。

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a>契約に応当日または年次更新日がない場合 (月単位の契約など)

応当日または年次更新日を含まない契約については、最初のエンド ユーザーが Microsoft Teams Exploratory エクスペリエンス ライセンスをアクティブ化した翌年が、応当日または年次更新日として扱われます。 Microsoft Teams Exploratory ライセンスを使用しているユーザーは、この記事のポリシーに従って、その年のその日までに有料ライセンスに移行する必要があります。

たとえば、最初のエンドユーザーが、2020 年 6 月 19 日に Microsoft Teams Exploratory をアクティブ化した場合、2021 年 6 月 19 日までにそれらのユーザーと顧客テナントのその他のすべての対象ユーザーが Teams の有料ライセンスに移行する必要があります。

> [!Note]
> お客様は、以前の Exploratory 試用版ライセンスの有効期限が終了してから 3 か月間、新しい Exploratory 試用版ライセンスは無効になり、起動がブロックされます。
