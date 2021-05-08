---
title: Teams Contoso のケース スタディ
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
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121305"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="5b12e-103">Contoso のケース スタディ: 電話会議</span><span class="sxs-lookup"><span data-stu-id="5b12e-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="5b12e-104">電話会議の機能、コスト、可用性、および機能について理解するために、Contoso は、電話会議を Office 365 &mdash; &mdash; で確認[しました](deploy-audio-conferencing-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="5b12e-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="5b12e-105">概要</span><span class="sxs-lookup"><span data-stu-id="5b12e-105">Overview</span></span> 

<span data-ttu-id="5b12e-106">電話会議では、組織内だけでなく外部でもよく知られている電話番号を使用しました。</span><span class="sxs-lookup"><span data-stu-id="5b12e-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="5b12e-107">Contoso は、可能な限りこれらの番号を維持したいと考えたため、電話会議ブリッジへの専用電話番号と共有電話番号の割り当てに関する情報を確認しました。</span><span class="sxs-lookup"><span data-stu-id="5b12e-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="5b12e-108">Contoso は調査に基づいて、次の決定を行いました。</span><span class="sxs-lookup"><span data-stu-id="5b12e-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="5b12e-109">電話会議の呼び出しを定期的にホストする人口のセグメントだけが、電話会議ライセンスを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b12e-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="5b12e-110">Contoso は、電話会議で使用するために、専用の電話番号を使用し、既存の番号を移植します。</span><span class="sxs-lookup"><span data-stu-id="5b12e-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="5b12e-111">Contoso ユーザーはユーザーを使用Skype for Businessすべてのユーザーのメールボックスがオンラインに存在していたため、多くのユーザーは既存の会議をスケジュールしています。</span><span class="sxs-lookup"><span data-stu-id="5b12e-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="5b12e-112">Contoso は [「Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) の使用」を読み、エンド ユーザーを TeamsOnly モードに変更すると、既存の会議が Contoso に対して自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="5b12e-112">Contoso read [Using the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="5b12e-113">構成</span><span class="sxs-lookup"><span data-stu-id="5b12e-113">Configuration</span></span>

<span data-ttu-id="5b12e-114">電話に関連付けられている電話番号は、電話会議内のサービス番号と呼電話システム。</span><span class="sxs-lookup"><span data-stu-id="5b12e-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="5b12e-115">通話プランを使用している場所では、既存の電話番号を携帯電話会社から Office 365 に移行するために、Contoso は「サービスの電話番号を取得する」の手順に[従いました](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="5b12e-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="5b12e-116">技術パイロットのエンド ユーザーに電話会議ライセンスを割り当てるには、Contoso 管理者は「組織の電話会議設定を管理する」の手順 [に従いました](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="5b12e-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="5b12e-117">Contoso は[、Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)ビジネス パイロットと移行のために、グループ ベースのライセンスを使用しました。次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5b12e-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

