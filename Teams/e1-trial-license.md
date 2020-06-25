---
title: 無料の Office 365 E1 試用版を管理する
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 03544095e5189af2f80714151f31648f79e65c8d
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868674"
---
<a name="manage-the-office-365-e1-trial"></a>Office 365 E1 試用版を管理する
==============================

2020 年 3 月、Microsoft Teams を含む 6 か月無料の Office 365 E1 試用版が新たにご利用いただけるようになりました。 Microsoft では、COVID-19 (コロナウィルス) の発生により、在宅勤務 (WFH) の従業員の必要の拡大に対応できるように、この度の特別な E1 試用板ライセンスをご用意しています。 

E1 ライセンスで使用できる機能については、「[Office 365 E1](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e1-business-software)」を参照してください。

[Teams でリモート ワーカーをサポートする](support-remote-work-with-teams.md)ためのガイダンスのすべてをお見逃しなく。

## <a name="how-to-get-an-e1-trial-license"></a>E1 試用版ライセンスを取得する方法

Microsoft アカウントの担当者にお問い合わせください。 担当者から E1 試用版へのサインアップに使用できるプロモーション コードをご提供します。 

Microsoft パートナーと提携している組織の場合、パートナーに連絡して 6 か月の Teams 無料試用版を入手してください。 Microsoft パートナーがまだおらず、提携を望む場合は、[Microsoft ソリューション プロバイダー](https://www.microsoft.com/solution-providers/home) を参照して、Teams で専門知識を持つパートナーを検索してください。


## <a name="how-to-sign-up-for-e1"></a>E1 へのサインアップ方法

アカウント担当者から送信されたメールにあるプロモーション コードをクリックしてください。 


## <a name="whos-eligible"></a>対象者

このオファーは、Microsoft アカウントの担当者が管理するすべてのお客様を対象としています。過去に他の Office 365 E1 試用版をライセンス認証したことのない組織 (非営利団体を含む) が対象となります。 

E1 試用版のプロモーション コードを使い終わってからもう一度使用したり、別の E1 試用版コードでライセンス認証したりすることはできません。 このような場合は、従業員の [Teams Exploratory ライセンス](teams-exploratory.md)の認証を行うことができます。

## <a name="who-isnt-eligible"></a>対象外

- このプランは、GCC、GCC High、DoD、EDU のお客様はご利用いただけません。 

- GCC の場合、[Office 365 G1 試用版](g1-trial-license.md)をご確認ください。 

- EDU のお客様は、無料の Office 365 A1 ライセンスを使用する必要があります。

## <a name="manage-the-e1-trial"></a>E1 試用版の管理

Office 365 E1 試用版のライセンス認証が完了したら、ライセンスが必要なユーザーに対してライセンスを有効にします。 方法については、「[Teams へのユーザー アクセスを管理する](user-access.md)」を参照してください。


E1 試用版が必要なユーザーに対して有効にした後は、有料ライセンスを持っているユーザーを管理するのと同じように、これらのユーザーを管理します。 詳細については、「[組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)」を参照してください。



### <a name="upgrade-users-from-the-office-365-e1-trial-license"></a>Office 365 E1 試用版ライセンスからユーザーをアップグレードする

E1 試用版のユーザーを有料サブスクリプションにアップグレードするには:

1. Teams が含まれているサブスクリプションを購入します。

2. ユーザーから Office 365 E1 試用版のサブスクリプションを削除します。

3. 新しく購入したライセンスを割り当てます。

詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。

> [!NOTE]
> E1 試用版のライセンス期間が終了し、Teams を含むサブスクリプションにユーザーがすぐにアップグレードされない場合は、ユーザー データは削除されません。 ユーザーは引き続き Azure Active Directory に残り、Teams 内のすべてのデータが残されたままになります。 ユーザーに新しいライセンスが割り当てられると、Teams の機能は再び有効になり、すべてのコンテンツが残ります。 

### <a name="remove-an-office-365-e1-trial-license"></a>Office 365 E1 試用版ライセンスを削除する

- Powershell を使用してこのライセンスを削除する場合は、次を参照してください :「[Office 365 PowerShell を使用してユーザー アカウントからライセンスを削除する](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)」

- 管理ポータルからこのライセンスを削除する場合は、「[組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams へのユーザー アクセスを管理する](user-access.md)

[組織の Microsoft Teams の設定を管理する](enable-features-office-365.md)

[Teams Exploratory エクスペリエンスを管理する](teams-exploratory.md)

[Microsoft 365 Nonprofit または Office 365 Nonprofit](https://www.microsoft.com/microsoft-365/nonprofit/office-365-nonprofit)

[Teams の展開のサポートを利用する](https://go.microsoft.com/fwlink/?linkid=780698)
