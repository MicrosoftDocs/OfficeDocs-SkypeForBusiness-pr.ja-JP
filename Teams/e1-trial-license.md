---
title: 無料の Office 365 E1 試用版を管理する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aytange
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams を所有しておらず、急いで必要な場合は、COVID-19 (コロナウィルス) の発生により遠隔勤務または在宅勤務 (WFH) の必要に迫られているユーザー向けの Office 365 E1 試用版を展開してください。
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6146b6d4a7ca3d988c5dc1042a7f75848cf4fc7b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092665"
---
<a name="manage-the-office-365-e1-trial"></a>Office 365 E1 試用版を管理する
==============================

2020 年 7 月 1 日をもって、Office 365 E1 試用版ライセンスは利用できなくなりました。 ユーザーに Microsoft Teams のライセンスを付与する必要がある場合は、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を読んで、Teams を含む有料サブスクリプションのリストを確認してください。 または、適格な組織は **[Teams の無料版](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)** を使用でき、従業員は **[Teams Exploratory](teams-exploratory.md)** エクスペリエンスのライセンス認証を行います。


Teams for Education のお客様は、無料版の [Office 365 A1 ライセンス](teams-edu-licensing.md)を確認してください。

この記事のガイダンスを使用して、[有料サブスクリプションへのアップグレード](#upgrade-users-from-the-office-365-e1-trial-license)など、既存の Office 365 E1 試用版ライセンスを管理します。

[Teams でリモート ワーカーをサポートする](support-remote-work-with-teams.md)ためのガイダンスのすべてをお見逃しなく。

## <a name="manage-the-e1-trial"></a>E1 試用版の管理

Office 365 E1 試用版のライセンス認証が完了したら、ライセンスが必要なユーザーに対してライセンスを有効にします。 方法については、「[Teams へのユーザー アクセスを管理する](user-access.md)」を参照してください。


E1 試用版が必要なユーザーに対して有効にした後は、有料ライセンスを持っているユーザーを管理するのと同じように、これらのユーザーを管理します。 詳細については、「[組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)」を参照してください。



### <a name="upgrade-users-from-the-office-365-e1-trial-license"></a>Office 365 E1 試用版ライセンスからユーザーをアップグレードする

E1 試用版のユーザーを有料サブスクリプションにアップグレードするには:

1. Teams が含まれているサブスクリプションを購入します。

2. ユーザーから Office 365 E1 試用版のサブスクリプションを削除します。

3. 新しく購入したライセンスを割り当てます。

詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。

> [!NOTE]
> E1 試用版のライセンス期間が終了し、Teams を含むサブスクリプションにユーザーがすぐにアップグレードされない場合は、ユーザー データは削除されません。 ユーザーは引き続き Azure Active Directory に残り、Teams 内のすべてのデータが残されたままになります。 ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、すべてのコンテンツが残ります。 

### <a name="remove-an-office-365-e1-trial-license"></a>Office 365 E1 試用版ライセンスを削除する

- Powershell を使用してこのライセンスを削除する場合は、次を参照してください :「[Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」

- 管理ポータルからこのライセンスを削除する場合は、「[組織からユーザーを削除する](/microsoft-365/admin/add-users/delete-a-user)」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams へのユーザー アクセスを管理する](user-access.md)

[組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)

[Teams Exploratory エクスペリエンスを管理する](teams-exploratory.md)

[Microsoft 365 Nonprofit または Office 365 Nonprofit](https://www.microsoft.com/microsoft-365/nonprofit/office-365-nonprofit)

[Teams の展開のサポートを利用する](https://go.microsoft.com/fwlink/?linkid=780698)