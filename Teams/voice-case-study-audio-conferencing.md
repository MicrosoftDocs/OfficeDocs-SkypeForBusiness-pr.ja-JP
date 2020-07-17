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
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="e174c-103">Contoso のケーススタディ: 電話会議</span><span class="sxs-lookup"><span data-stu-id="e174c-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="e174c-104">電話会議について理解を深めるために、どのような費用がかかるか、どのように機能しているか、 &mdash; &mdash; Contoso が[Office 365 の電話会議に](deploy-audio-conferencing-teams-landing-page.md)どのように対応しているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e174c-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="e174c-105">概要</span><span class="sxs-lookup"><span data-stu-id="e174c-105">Overview</span></span> 

<span data-ttu-id="e174c-106">電話会議の場合、Contoso では、組織内でも外部とよく知られている電話番号を使用していました。</span><span class="sxs-lookup"><span data-stu-id="e174c-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="e174c-107">Contoso はこれらの番号を可能な限り維持する必要があるため、専用の電話番号と共有電話番号を電話会議ブリッジに割り当てる方法についての情報を確認しました。</span><span class="sxs-lookup"><span data-stu-id="e174c-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="e174c-108">Contoso は、調査に基づいて次の決定を行いました。</span><span class="sxs-lookup"><span data-stu-id="e174c-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="e174c-109">電話会議の通話を定期的にホストしている人口のセグメントのみが電話会議のライセンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e174c-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="e174c-110">Contoso は、電話会議で使用するために、専用の電話番号を使用し、既存の電話番号を移植します。</span><span class="sxs-lookup"><span data-stu-id="e174c-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="e174c-111">Contoso ユーザーは Skype for Business を使用しており、すべてのユーザーのメールボックスがオンラインであるため、多くのユーザーが既存の会議をスケジュールしています。</span><span class="sxs-lookup"><span data-stu-id="e174c-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="e174c-112">Contoso は、[会議移行サービス (MMS) を使用して](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)、既存の会議が、Contoso について自動的に更新されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e174c-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="e174c-113">構成</span><span class="sxs-lookup"><span data-stu-id="e174c-113">Configuration</span></span>

<span data-ttu-id="e174c-114">電話会議に関連付けられている電話番号は、電話システム内のサービス番号として参照されます。</span><span class="sxs-lookup"><span data-stu-id="e174c-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="e174c-115">通話プランを使用している場所で、既存の電話番号を電話会社から Office 365 に移植する方法については、「[サービス電話番号を取得](getting-service-phone-numbers.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="e174c-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="e174c-116">テクニカルパイロットのエンドユーザーに電話会議ライセンスを割り当てるには、Contoso 管理者が「[組織の電話会議の設定を管理](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e174c-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="e174c-117">ビジネスパイロットと移行の場合、Contoso は、「 [Azure Active Directory のグループメンバーシップによってユーザーにライセンスを割り当てる](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)」の手順に従って、グループベースのライセンスを使用していました。</span><span class="sxs-lookup"><span data-stu-id="e174c-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 