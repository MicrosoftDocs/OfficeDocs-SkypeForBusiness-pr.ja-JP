---
title: Teams の音声 Contoso のケース スタディ
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
description: 多国籍企業向け Teams 音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121305"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso のケース スタディ: 電話会議

電話会議の機能、コスト、可用性、動作を理解するために、Contoso は &mdash; &mdash; Office [365](deploy-audio-conferencing-teams-landing-page.md)の電話会議を確認しました。 

## <a name="overview"></a>概要 

電話会議の場合、Contoso は組織内でも外部でもよく知られている電話番号を使用しました。 Contoso は可能な限りこれらの番号を維持する必要がありましたので、電話会議ブリッジに専用の電話番号と共有電話番号を割り当てる方法に関する情報を確認しました。 

Contoso は調査に基づいて、次の決定を行いました。 

- 電話会議の通話を定期的にホストする人口のセグメントだけが、電話会議ライセンスを受け取る必要があります。 

- Contoso は、電話会議で使用するために、専用の電話番号を使用し、既存の番号を移植します。   

Contoso ユーザーが Skype for Business を使用していたため、すべてのユーザーのメールボックスがオンライン上に存在する場合、多くのユーザーが既存の会議をスケジュールしています。 Contoso は [、「Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) を使用して、エンド ユーザーを TeamsOnly モードに変更すると、Contoso の既存の会議が自動的に更新される」を参照してください。  


## <a name="configuration"></a>構成

電話会議に関連付けられている電話番号は、電話システム内のサービス番号と呼ばれます。 

- 通話プランを使用している場所では、携帯電話会社から Office 365 に既存の電話番号を移行するために、Contoso は「サービス電話番号を取得する」の手順に [従](getting-service-phone-numbers.md)いました。

- テクニカル パイロットで電話会議ライセンスをエンド ユーザーに割り当てるには、Contoso 管理者が「組織の電話会議設定を管理する」の手順 [に従いました](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)。 

- ビジネス パイロットと移行では、Contoso は、「Azure Active Directory のグループ メンバーシップ別にライセンスをユーザーに割り当てる」の手順に従って、グループベースのライセンス [を使用しました](/azure/active-directory/users-groups-roles/licensing-groups-assign)。  

 

