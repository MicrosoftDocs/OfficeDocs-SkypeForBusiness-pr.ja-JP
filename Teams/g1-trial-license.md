---
title: 米国政府機関向けの無料の Office 365 G1 試用版を管理する
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: a6ae8079ba3ccd498936c5d17740ea2e5bafb514
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858722"
---
<a name="manage-the-office-365-g1-trial-for-us-government"></a>米国政府機関向けの Office 365 G1 試用版を管理する 
==============================

2020 年 3 月、Microsoft Teams を含む 6 か月無料の Office 365 G1 試用版が新たにご利用いただけるようになりました。 Microsoft では、COVID-19 (コロナウィルス) の発生により、在宅勤務 (WFH) の従業員の必要の拡大に対応できるように、この度の特別な G1 試用板ライセンスを米国政府機関向けにご用意しています。

G1 ライセンスで利用できる機能については、「[Microsoft 365 Government Plans (Microsoft 365 政府機関向けプラン)](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans)」および「[Microsoft Teams capabilities available in the GCC Cloud (GCC クラウドで利用可能な Microsoft Teams の機能)](plan-for-government-gcc.md)」をご覧ください。

 [Teams でリモート ワーカーをサポートする](support-remote-work-with-teams.md)ためのガイダンスのすべてをお見逃しなく。

## <a name="how-to-get-an-g1-trial-license"></a>G1 試用版ライセンスを取得する方法

Microsoft アカウントの担当者にお問い合わせください。 担当者から G1 試用版へのサインアップに使用できるプロモーション コードをご提供します。

## <a name="how-to-sign-up-for-the-g1-trial"></a>G1 試用版へのサインアップ方法

アカウント担当者から送信されたメールにある手順に従ってください。

## <a name="whos-eligible"></a>対象者

このオファーは、GCC クラウドを利用し、Microsoft アカウントの担当者が管理する米国政府機関のお客様を対象としています。過去に他の Office 365 G1 試用版をライセンス認証したことのない組織が対象となります。

G1 試用版のプロモーション コードを使い終わってからもう一度使用したり、別の G1 試用版コードでライセンス認証したりすることはできません。

## <a name="who-isnt-eligible"></a>対象外

  - このオファーでは、商用版、GCC High、DoD、EDU のお客様はご利用いただけません。

  - 商用のお客様は、Office 365 E1 試用版を使用してください。

  - EDU のお客様は、無料の Office 365 A1 ライセンスを使用する必要があります。

## <a name="manage-the-g1-trial"></a>E1 試用版を管理する

Office 365 G1 試用版のライセンス認証が完了したら、ライセンスが必要なユーザーに対してライセンスを有効にします。 方法については、「 [Teams へのユーザー アクセスを管理する](user-access.md#manage-teams-through-the-microsoft-365-admin-center)」を参照してください。

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

  - 管理ポータルからこのライセンスを削除する場合は、次を参照してください :「 [Remove licenses from users in Office 365 (Office 365 のユーザーからライセンスを削除する)](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)」

## <a name="related-topics"></a>関連項目

[Teams へのユーザー アクセスを管理する](user-access.md#manage-teams-through-the-microsoft-365-admin-center)

[組織のMicrosoft Teams の設定を管理します](enable-features-office-365.md)

