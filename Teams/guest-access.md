---
title: Microsoft Teams でのゲスト アクセス
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1787d2f310ebf7ed0afafa41e8b730346a54ec
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37565108"
---
<a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス
======================================

ゲスト アクセスは、ユーザーからの要望が最も多かった機能の 1 つです。 ゲスト アクセスの進捗状況に対応する方法と、その機能に関する意見や要望を知らせる方法は、以下に示します。

- ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。
- 今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。
- ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。
- 下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。

## <a name="guest-access-overview"></a>ゲスト アクセスの概要

ゲスト アクセスにより、組織内のチームは、1 つまたは複数のテナントでの既存のチームやチャネルにアクセス権を組織外のユーザーに付与することで、共同作業することができるようになります。 Outlook、Gmail などの勤務先または通常のメール アカウントを持っている全てのユーザーは、チーム チャット、会議、ファイルにフル アクセス権を持つゲストとして Teams に参加することができます。

ゲスト アクセスはさまざまな Office 365 サブスクリプションに含まれており、追加のライセンス要件はありません。 ライセンスに関する詳細については、[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)をご覧ください。

ゲスト アクセスは Microsoft Teams ではテナントレベルの設定であり、既定ではオフになっています。 ゲスト アクセスは Azure AD および Office 365 のサービス制限に適用されます。

> [!NOTE]
> Exchange Online プラン 2 などのスタンドアロン Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。 Teams を使用するこれらのユーザーの場合は、Office 365 Business Premium、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。 

## <a name="who-is-a-guest"></a>ゲストとは何ですか?

ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。 自分の組織に属していないユーザーを Teams のゲストとして追加することができます。 これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または通常のメール アカウント (Outlook.com、Gmail.com、他) を持つすべてのユーザーが、チームとチャネルの操作や機能にフル アクセスできるゲストとして、Teams に参加できることを意味します。 ([Microsoft Teams でのゲスト アクセスを承認する](teams-dependencies.md)をご覧ください。) Teams のすべてのゲストは、Office 365と同じように同じコンプライアンスと監査の保護の対象となり、Azure AD 内で安全に管理されます。

## <a name="why-use-guest-access"></a>ゲスト アクセスを使用する理由を教えてください。

ゲスト アクセスにより、Teams を使用している組織は、企業データに対する完全な制御を維持しながら、パートナーにチーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへの外部アクセスを提供することができます。 Teams のすべてのゲストは、Office 365 と同様のコンプライアンスと監査による保護の対象となります。また、ゲストは Azure AD 内で安全に管理されます。  

Teams は、Office 365 グループに基づき構築されており、Office 365 グループの共有資産への新しいアクセス方法を提供します。 Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。 Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a>ゲスト アクセスを外部アクセス (フェデレーション) と比べるとどのような違いがありますか?

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>詳細情報

[ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[Office 365 グループのゲスト アクセス](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
