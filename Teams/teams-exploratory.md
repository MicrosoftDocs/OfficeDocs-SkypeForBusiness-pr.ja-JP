---
title: Microsoft Teams Exploratory エクスペリエンスを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams ライセンスが付与されていない Office 365 ユーザーは、Exploratory Teams ライセンスを開始できます。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6777dfbafac89c798955245b93f1e4537093b0cf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871789"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Microsoft Teams Exploratory ライセンスを管理する
=======================================================

Microsoft Teams Exploratory エクスペリエンスを使用すると、Azure Active Directory (AAD) を持ち、Teams のライセンスを取得していない組織内のユーザーは、Teams の Exploratory エクスペリエンスを開始できます。 管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。 以前の [Microsoft の商用クラウドの試用版](iw-trial-teams.md)は、Teams Exploratory エクスペリエンスと呼ばれています。

[!INCLUDE [preview-feature](includes/preview-feature.md)] このエクスペリエンスは、2020 年 1 月中旬から利用可能になります。

## <a name="whats-in-the-teams-exploratory-experience"></a>Teams Exploratory エクスペリエンスの内容

Teams Exploratory エクスペリエンスに含まれるサービス プランは次のとおりです。
 - Exchange Online (プラン 1)
 - Office 365 のフロー
 - MyAnalytics を利用した分析情報
 - Microsoft Forms (プラン E1)
 - Microsoft Planner
 - Microsoft Search
 - Microsoft StaffHub
 - Microsoft Stream for O365 E1 SKU
 - Microsoft Teams
 - Mobile Device Management for Office 365
 - Office Mobile Apps for Office 365 
 - Office Online
 - Office 365 向けの PowerApps
 - SharePoint Online (プラン 1)
 - Sway
 - To-Do (プラン 1)
 - Whiteboard (プラン 1)
 - Yammer Enterprise


## <a name="whos-eligible"></a>対象者

ユーザーが (Microsoft 365 管理センターで) アプリや試用版にサインアップできるようにする必要があります。 詳細については、この記事で後述する「[Teams Exploratory エクスペリエンスを管理する](#manage-the-teams-exploratory-experience)」を参照してください。 

Teams を含む Office 365 ライセンスを持っていないユーザーは、Teams Exploratory エクスペリエンスを開始できます。 たとえば、ユーザーが Office 365 Business (Teams を含まない) を持っている場合、ユーザーは Teams Exploratory エクスペリエンスの対象になります。

## <a name="who-isnt-eligible"></a>対象外

シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、組織は試用版の対象ではありません。


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>ユーザーが Teams Exploratory エクスペリエンスにサインアップする方法

対象となるユーザーは、Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして Teams Exploratory エクスペリエンスにサインアップできます。 これらのライセンスは自動的に割り当てられ、組織内の誰かが初めて Teams Exploratory エクスペリエンスを開始すると、テナント管理者に、メール通知が送信されます。

## <a name="manage-the-teams-exploratory-experience"></a>Teams Exploratory エクスペリエンスを管理する

Teams Exploratory エクスペリエンスは個々のエンド ユーザーが開始するためのものであり、エンド ユーザーの従業員に代わってこのサービスを開始することはできません。

Teams Exploratory エクスペリエンスには Exchange Online ライセンスが付属していますが、管理者が割り当てるまでユーザーに割り当てられません。 ユーザーにまだ Exchange ライセンスがなく、管理者がまだ Exchange Online ライセンスを割り当てていない場合、ユーザーは Teams で会議をスケジュールできず、他の Teams の機能を利用できない可能性があります。

管理者は、**試用版のアプリとサービス** スイッチを使用して、エンド ユーザーが組織内で Teams Exploratory エクスペリエンスを実行できないようにすることができます。


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>ユーザーが試用版アプリおよびサービスをインストールできないようにする

試用版アプリとサービスをインストールするユーザーの機能をオフにすると、ユーザーが Teams Exploratory エクスペリエンスを実行できなくなります。

1. [[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home) から、**[設定]** > **[サービスとアドイン]** > **[ユーザーが所有するアプリとサービス]** に移動します。

    ![管理センターの [サービスとアドイン] ページのスクリーン ショット](media/iw-trial-enable-1.png)

2. **[ユーザーに試用版アプリとサービスのインストールを許可する]** をオフにします。

    ![管理センターの [ユーザーが所有するアプリとサービス] ページのスクリーンショット](media/iw-trial-enable-2.png)
> [!NOTE]
> 組織が Teams Exploratory エクスペリエンスの対象外の場合は、「**ユーザーが試用版アプリとサービスをインストールできるようにする**」スイッチは表示されません。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Teams が含まれているライセンスを持つユーザーの利用可能性を管理する

Teams が含まれているライセンスの割り当てられたユーザーは、Teams Exploratory エクスペリエンスの対象になりません。 Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。 サービス プランが無効になっている場合、ユーザーはサインインできず、Teams Exploratory エクスペリエンスは利用できません。

Teams へのアクセスをオフにするには:

1. Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。

2. ユーザーの名前の横にあるボックスを選択します。

3. 右側の **[製品ライセンス]** 行で、**[編集]** を選択します。

4. **[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。

    ![管理センターの [製品ライセンス] ページのスクリーン ショット。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Teams Exploratory エクスペリエンスをすでに使用しているユーザーの Teams の可用性を管理する

ユーザーが Teams Exploratory エクスペリエンスを実行している場合は、ライセンスまたはサービス プランを削除することでそれをオフにできます。

Teams Exploratory エクスペリエンスのライセンスをオフにするには:

1. Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。

2. ユーザーの名前の横にあるボックスを選択します。

3. 右側の **[製品ライセンス]** 行で、**[編集]** を選択します。

4. [**製品ライセンス**] ウィンドウで、この Exploratory ライセンスのトグルを [**オフ**] に切り替えます。

    
>[!Note]
>Teams Exploratory のトグル スイッチは、組織の最初のユーザーが Teams Exploratory エクスペリエンスを起動した後に表示されます。

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Teams Exploratory ライセンスを持つユーザーの Teams を管理する

Teams Exploratory ライセンスを持つユーザーは、通常の有料ライセンスを持つユーザーと同じように管理できます。 詳細については、「[組織の Teams 設定を管理する](enable-features-office-365.md)」を参照してください。

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Teams Exploratory ライセンスからユーザーをアップグレードする

Teams Exploratory ライセンスからユーザーをアップグレードするには、次の手順を実行します。

1. Teams が含まれているサブスクリプションを購入します。

2. ユーザーから Teams Exploratory のサブスクリプションを削除します。

3. 新しく購入したライセンスを割り当てます。

詳細については、「[Microsoft Teams 用の Office 365 ライセンス](Office-365-licensing.md)」を参照してください。

> [!NOTE]
> Teams Exploratory ライセンスが終了し、Teams を含むサブスクリプションにユーザーがすぐにアップグレードされない場合は、ユーザー データは削除されません。 ユーザーは引き続き Azure Active Directory に残り、Teams 内のすべてのデータが残されたままになります。 ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、すべてのコンテンツが残ります。 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>従来の Microsoft Teams の商用クラウドの試用版のライセンスはどうなりますか?

2020 年 1 月中旬から、対象ユーザーは最新の Microsoft Teams Exploratory エクスペリエンスの使用を開始できます。 従来の Teams の商用クラウドの試用版のライセンスはすべて、試用版の有効期限が切れる前に自動的に新しいサービスに変換されます。

### <a name="remove-a-teams-exploratory-license"></a>Teams Exploratory ライセンスを削除する

- Powershell を使用してこのライセンスを削除する場合は、次を参照してください :「[Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」

- 管理ポータルからこのライセンスを削除する場合は、次を参照してください :「[一般法人向け Office 365 のユーザーからライセンスを削除する](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)」
