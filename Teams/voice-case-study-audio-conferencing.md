---
title: チームボイスの Contoso のケーススタディ
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
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786116"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso のケーススタディ: 電話会議

電話会議について理解を深めるために、どのような費用がかかるか、どのように機能しているか、 &mdash; &mdash; Contoso が[Office 365 の電話会議に](deploy-audio-conferencing-teams-landing-page.md)どのように対応しているかについて説明します。 

## <a name="overview"></a>概要 

電話会議の場合、Contoso では、組織内でも外部とよく知られている電話番号を使用していました。 Contoso はこれらの番号を可能な限り維持する必要があるため、専用の電話番号と共有電話番号を電話会議ブリッジに割り当てる方法についての情報を確認しました。 

Contoso は、調査に基づいて次の決定を行いました。 

- 電話会議の通話を定期的にホストしている人口のセグメントのみが電話会議のライセンスを受け取ります。 

- Contoso は、電話会議で使用するために、専用の電話番号を使用し、既存の電話番号を移植します。   

Contoso ユーザーは Skype for Business を使用しており、すべてのユーザーのメールボックスがオンラインであるため、多くのユーザーが既存の会議をスケジュールしています。 Contoso は、[会議移行サービス (MMS) を使用して](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)、既存の会議が、Contoso について自動的に更新されることを確認します。  


## <a name="configuration"></a>構成

電話会議に関連付けられている電話番号は、電話システム内のサービス番号として参照されます。 

- 通話プランを使用している場所で、既存の電話番号を電話会社から Office 365 に移植する方法については、「[サービス電話番号を取得](getting-service-phone-numbers.md)する」の手順に従ってください。

- テクニカルパイロットのエンドユーザーに電話会議ライセンスを割り当てるには、Contoso 管理者が「[組織の電話会議の設定を管理](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)する」の手順に従います。 

- ビジネスパイロットと移行の場合、Contoso は、「 [Azure Active Directory のグループメンバーシップによってユーザーにライセンスを割り当てる](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)」の手順に従って、グループベースのライセンスを使用していました。  

 

 