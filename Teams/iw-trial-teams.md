---
title: Microsoft Teams の商用クラウドの試用提供を管理する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 04/23/2019
ms.topic: reference
audience: Admin
ms.reviewer: marubins
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams のライセンスが付与されていない Office 365 ユーザーは、Teams の 1 年間試用版を開始できます。
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: baad7614cbcb622017de7629fa62799be330dc88
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402516"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Microsoft Teams の商用クラウドの試用提供を管理する
=======================================================

Microsoft Teams は、組織に最適な共同作業ツールです。 Office 365 の機能を使用して、ユーザーやチームがアイデアのディスカッション、導入、共有を行うことができます。 Microsoft Teams の商用クラウド試用版は、製品の 1 年間試用版を開始するための Microsoft Teams ライセンスを所有していない、組織内の既存の Office 365 ユーザーを対象にしています。 管理者は組織内のユーザーに対して、この機能をオンまたはオフに切り替えることができます。

> [!IMPORTANT]
> Microsoft Teams の商用クラウドの試用版は、Teams の機能を増やす追加のサービス プランを含む更新がされ、現在組織の請求管理者によって所有し管理されています。これは、試用をより管理しやすくし、その他の Microsoft 365 のすべての特典に一貫性を持たせることができます。 既存の Teams の商用クラウドの試用版のユーザーは、新しいプランに移行されます。

## <a name="whats-in-the-offer"></a>オファーの内容

このオファーに含まれるサービス プランは次のとおりです。

- Exchange の基礎
- Office 365 プラン 1 のフロー
- フォーム
- Microsoft Planner
- Microsoft Teams (Teams1、Teams IW)
- Office Online
- PowerApps for Office 365 プラン 1
- SharePoint Online Kiosk
- Stream
- Sway
- Whiteboard
- Yammer Enterprise 

試用版では、組織全体に 1 年間の試用版サブスクリプションを付与します。 試用版では、500,000 ライセンスが割り当て可能になります。 割り当てられたライセンスごとに、試用版では 2 GB の SharePoint Online 記憶域が割り当てられます。 

## <a name="who-is-eligible"></a>対象者

ユーザーがアプリや試用版にサインアップできるようにする必要があります (Office 365 管理センターで)。 詳細については、この記事で後述する「[試用版を管理する](#manage-the-trial)」を参照してください。 

Teams を含む Office 365 ライセンスを所有していないユーザーは、Microsoft Teams 商用クラウド試用版のオファーを開始できます。 たとえば、ユーザーが Office 365 Business (Teams を含まない) を所有している場合、ユーザーは試用版の対象になります。

## <a name="who-is-not-eligible"></a>対象外

シンジケート パートナー顧客である場合、または GCC、GCC High、DoD、または教育機関の顧客である場合、あなたの組織は試用版の対象ではありません。

組織が Microsoft Teams 商用クラウド試用版オファーの対象外の場合は、**[ユーザーに試用版アプリとサービスのインストールを許可する]** スイッチは表示されません。

## <a name="how-users-sign-up-for-the-trial"></a>ユーザーが試用版にサインアップする方法

対象となるユーザーは、Teams ([teams.microsoft.com](https://teams.microsoft.com)) にサインインして試用版オファーにサインアップできます。 試用版を開始するために、次の画面が表示されます。 

![Teams IW 試用版のスタート ページのスクリーン ショット。](media/iw-trial-start-screen.png)

組織内のすべての試用版は、最初のユーザーが試用版にサインアップした日付と同じ開始日と終了日を共有します。 たとえば、ユーザー A が 2019 年 1 月 25 日に最初の試用を開始し、ユーザー B が 2019 年 6 月 3 日に試用を開始した場合は、2020 年 1 月 25 日にどちらのユーザーの試用も期限が切れます。

## <a name="manage-the-trial"></a>試用版の管理

試用版のライセンスには、管理者によって割り当てられたその他のサブスクリプションの取得と同じ方法が割り当てられます。 詳細については、「[Office 365 for businessライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)」を参照してください。 

さらに、管理者はエンド ユーザーが組織内で試用版アプリおよびサービスを要求できないようにすることも可能です。 現時点では、この記事で説明している試用版が、このカテゴリの唯一の試用版ですが、将来、別の同様のプログラムに適用される可能性があります。 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>ユーザーが試用版アプリおよびサービスをインストールできないようにする

試用版のアプリとサービスをユーザーがインストールする機能をオフにできます。

1. [[Microsoft 365 管理センター]](https://portal.office.com/adminportal/home) から、**[設定]** > **[サービスとアドイン]** > **[ユーザーが所有するアプリとサービス]** に移動します。

    ![Office 365 管理センターの [サービスとアドイン] ページのスクリーンショット。](media/iw-trial-enable-1.png)

2. **[ユーザーに試用版アプリとサービスのインストールを許可する]** をオフにします。

    ![Office 365 管理センターの [ユーザーが所有するアプリとサービス] ページのスクリーンショット。](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Teams が含まれているライセンスを持つユーザーの試用版利用可能性を管理する

Teams が含まれているライセンスの割り当てられたユーザーは、試用版の対象になりません。 Teams のサービス プランが有効なときには、そのユーザーは Teams にログインして使用できます。 サービス プランが無効な場合、そのユーザーはログインすることも、試用版のオプションが表示されることもありません。

Teams へのアクセスをオフにするには:

1. Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。

2. ユーザーの名前の横にあるボックスを選択します。

3. 右側の **[製品ライセンス]** 行で、**[編集]** を選択します。

4. **[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。

    ![Office 365 管理センターの [製品ライセンス] ページのスクリーンショット。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>既に試用版を要求しているユーザーの Teams の利用可能性を管理する

ユーザーが Teams 試用版のライセンスを要求していた場合は、そのライセンスまたはサービス プランを削除することで試用版ライセンスを削除できます。

試用版ライセンスをオフにするには:

1. Microsoft 365 管理センターで、**[ユーザー]** > **[アクティブ ユーザー]** を選択します。

2. ユーザーの名前の横にあるボックスを選択します。

3. 右側の **[製品ライセンス]** 行で、**[編集]** を選択します。

4. **[製品ライセンス]** ウィンドウで、**[オフ]** に切り替えます。

    ![[製品ライセンス] ウィンドウの Teams 試用版ライセンスの設定を示すスクリーンショット](media/iW-trial-enable-4.png)
    
>[!Note]
>Microsoft Teams の試用版の切り替えスイッチは、組織内の最初のユーザーが試用版にサインアップした後に表示されます。

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>試用版ライセンスを持つユーザーの Teams を管理する

試用版ライセンスを持っているユーザーは、通常の有料ライセンスを持っているユーザーと同じように管理できます。 詳細については、[組織のMicrosoft Teams 設定の管理](enable-features-office-365.md)を参照してください。

### <a name="upgrade-users-from-the-trial-license"></a>試用版ライセンスからユーザーをアップグレードする

試用版ライセンスからユーザーをアップグレードするには、次の手順を実行します。

1. Teams が含まれているサブスクリプションを購入します。

2. ユーザーから Teams 試用版のサブスクリプションを削除します。

3. 新しく購入したライセンスを割り当てます。

詳細については、「[Microsoft Teams 用の Office 365 ライセンス](Office-365-licensing.md)」を参照してください。

> [!NOTE]
> 試用期間が終了し、Teams を含むサブスクリプションにユーザーがすぐにアップグレードされない場合は、ユーザー データは削除されません。 ユーザーは引き続き Azure Active Directory に残り、Teams 内のすべてのデータが残されたままになります。 ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、すべてのコンテンツが残ります。 