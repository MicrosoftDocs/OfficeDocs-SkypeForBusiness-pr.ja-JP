---
title: 'Teams Contoso のケース スタディ: 電話会議'
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
description: 'Teams企業向け音声ケース スタディ: 電話会議'
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

電話会議の機能、コスト、可用性、および機能について理解するために、Contoso は、電話会議を Office 365 &mdash; &mdash; で確認[しました](deploy-audio-conferencing-teams-landing-page.md)。 

## <a name="overview"></a>概要 

電話会議では、組織内だけでなく外部でもよく知られている電話番号を使用しました。 Contoso は、可能な限りこれらの番号を維持したいと考えたため、電話会議ブリッジへの専用電話番号と共有電話番号の割り当てに関する情報を確認しました。 

Contoso は調査に基づいて、次の決定を行いました。 

- 電話会議の呼び出しを定期的にホストする人口のセグメントだけが、電話会議ライセンスを受け取る必要があります。 

- Contoso は、電話会議で使用するために、専用の電話番号を使用し、既存の番号を移植します。   

Contoso ユーザーはユーザーを使用Skype for Businessすべてのユーザーのメールボックスがオンラインに存在していたため、多くのユーザーは既存の会議をスケジュールしています。 Contoso は [「Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) の使用」を読み、エンド ユーザーを TeamsOnly モードに変更すると、既存の会議が Contoso に対して自動的に更新されます。  


## <a name="configuration"></a>構成

電話に関連付けられている電話番号は、電話会議内のサービス番号と呼電話システム。 

- 通話プランを使用している場所では、既存の電話番号を携帯電話会社から Office 365 に移行するために、Contoso は「サービスの電話番号を取得する」の手順に[従いました](getting-service-phone-numbers.md)。

- 技術パイロットのエンド ユーザーに電話会議ライセンスを割り当てるには、Contoso 管理者は「組織の電話会議設定を管理する」の手順 [に従いました](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)。 

- Contoso は[、Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)ビジネス パイロットと移行のために、グループ ベースのライセンスを使用しました。次の手順に従います。  

 

