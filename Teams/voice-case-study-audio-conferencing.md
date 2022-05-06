---
title: 'Teams音声 Contoso のケース スタディ: 電話会議'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams多国籍企業向けの音声ケース スタディ: 電話会議'
appliesto:
- Microsoft Teams
ms.openlocfilehash: f25fa2e81244365d1c0c3dfcacf918f1b35a6fa71d2b619eaaa55c8aa219c310
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335797"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso のケース スタディ: 電話会議

電話会議&mdash;の内容、コスト、可用性、およびどのように機能&mdash;するかを理解するために、Contoso は[Office 365で電話会議を](deploy-audio-conferencing-teams-landing-page.md)確認しました。 

## <a name="overview"></a>概要 

電話会議では、Contoso は組織内だけでなく外部でもよく知られている電話番号を使用しました。 Contoso は可能な限りこれらの番号を維持したいと考えたため、電話会議ブリッジへの専用電話番号と共有電話番号の割り当てに関する情報を確認しました。 

Contoso は調査に基づいて、次の決定を行いました。 

- 電話会議の呼び出しを定期的にホストする母集団のセグメントのみが電話会議ライセンスを受け取ります。 

- Contoso は専用の電話番号を使用し、電話会議で使用するために既存の番号を移植します。   

Contoso ユーザーはSkype for Businessを使用していて、すべてのユーザーのメールボックスがオンラインになっているため、多くのユーザーが既存の会議をスケジュールしています。 Contoso は [、会議移行サービス (MMS) を使用して](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) 、エンド ユーザーを TeamsOnly モードに変更すると、Contoso の既存の会議が自動的に更新されることを確認しました。  


## <a name="configuration"></a>構成

電話会議に関連付けられている電話番号は、電話システム内のサービス番号と呼ばれます。 

- 通話プランを使用している場所の場合、電話会社からOffice 365に既存の電話番号を移植するために、Contoso は[サービス電話番号の取得](getting-service-phone-numbers.md)に関するページの手順に従いました。

- 技術パイロットのエンド ユーザーに電話会議ライセンスを割り当てるには、Contoso 管理者が [組織の電話会議設定の管理](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)に関するページの手順に従いました。 

- ビジネス パイロットと移行の場合、Contoso は「Azure Active Directoryのグループ [メンバーシップでユーザーにライセンスを割り当てる」の手順に従って、グループ ベースのライセンスを](/azure/active-directory/users-groups-roles/licensing-groups-assign)使用しました。  

 

