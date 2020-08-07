---
title: 米国政府機関向けの無料の Office 365 G1 試用版を管理する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aarimm
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 米国政府機関の場合、Microsoft Teams を所有しておらず、急いで必要な場合は、COVID-19 (コロナウィルス) の発生により遠隔勤務または在宅勤務 (WFH) の必要に迫られているユーザー向けの Office 365 G1 試用版を展開してください。
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bdfdfb180005913b650cee27c350cf7c3ad5a27
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583224"
---
<a name="manage-the-office-365-g1-trial-for-us-government"></a>米国政府機関向けの Office 365 G1 試用版を管理する 
==============================

2020 年 7 月 1 日をもって、Office 365 E1 試用版ライセンスは利用できなくなりました。 ユーザーに Microsoft Teams のライセンスを付与する必要がある場合は、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を読んで、Teams を含む有料サブスクリプションのリストを確認してください。 

この記事のガイダンスを使用して、[有料サブスクリプションへのアップグレード](#upgrade-users-from-the-office-365-g1-trial-license)など、既存の Office 365 G1 試用版ライセンスを管理します。 詳細については、「[Microsoft 365 政府機関向けプラン](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans)」および「[GCC クラウドで利用可能な Microsoft Teams の機能](plan-for-government-gcc.md)」をご覧ください。

 [Teams でリモート ワーカーをサポートする](support-remote-work-with-teams.md)ためのガイダンスのすべてをお見逃しなく。

## <a name="manage-the-g1-trial"></a>E1 試用版を管理する

Office 365 G1 試用版のライセンス認証が完了したら、ライセンスが必要なユーザーに対してライセンスを有効にします。 方法については、「 [Teams へのユーザー アクセスを管理する](user-access.md)」を参照してください。

G1 試用版が必要なユーザーに対して有効にした後は、有料ライセンスを持っているユーザーを管理するのと同じように、これらのユーザーを管理します。 詳細については、「 [組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)」を参照してください。

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>Office 365 G1 試用版ライセンスからユーザーをアップグレードする

G1 試用版のユーザーを有料サブスクリプションにアップグレードするには:

1.  Teams が含まれているサブスクリプションを購入します。

2.  ユーザーから Office 365 G1 試用版のサブスクリプションを削除します。

3.  新しく購入したライセンスを割り当てます。

詳細については、「[政府機関用の Teams](expand-teams-across-your-org/teams-for-government-landing-page.md)」を参照してください。

> [!NOTE]
> G1 試用版のライセンス期間が終了し、Teams を含むサブスクリプションにユーザーがすぐにアップグレードされない場合は、ユーザー データは削除されません。 ユーザーは引き続き Azure Active Directory に残り、Teams 内のすべてのデータが残されたままになります。 ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、すべてのコンテンツが残ります。
> 
### <a name="remove-an-office-365-g1-trial-license"></a>Office 365 G1 試用版ライセンスを削除する

  - Powershell を使用してこのライセンスを削除する場合は、次を参照してください:「 [Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」

  - 管理ポータルからこのライセンスを削除する場合は、「 [組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams へのユーザー アクセスを管理する](user-access.md)

[組織のMicrosoft Teams の設定を管理します](enable-features-office-365.md)
