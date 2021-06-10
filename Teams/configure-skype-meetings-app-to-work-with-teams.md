---
title: Teams と連動するように Skype 会議アプリを構成する
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
description: 管理者は、Microsoft Teams 管理センターを使用して、Teams と連携するように Skype 会議アプリを構成することができます。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29887ee89c8db36e6d5116118e0ec4fbc2a3e0ff
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856446"
---
# <a name="configure-the-skype-meetings-app-to-work-with-teams"></a><span data-ttu-id="e72cc-103">Teams と連動するように Skype 会議アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="e72cc-103">Configure the Skype Meetings App to work with Teams</span></span>

<span data-ttu-id="e72cc-104">ユーザーが Microsoft Teams にアップグレードされた後、管理者は、Microsoft Teams 管理センターを使用して、ユーザーが Skype for Business 会議に参加するために使用する優先アプリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e72cc-104">After a user is upgraded to Microsoft Teams, admins can use the Microsoft Teams admin center to specify the preferred app that users will use to join Skype for Business meetings.</span></span>

<span data-ttu-id="e72cc-105">Skype 会議アプリを優先アプリとして指定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e72cc-105">To specify the Skype for Meetings App as the preferred app:</span></span>

1. <span data-ttu-id="e72cc-106">Microsoft Teams 管理センターにサインインする。</span><span class="sxs-lookup"><span data-stu-id="e72cc-106">Sign in to the Microsoft Teams admin center.</span></span>
2. <span data-ttu-id="e72cc-107">左側のウィンドウで、**[組織全体の設定]** の下にある **[Teams のアップグレード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e72cc-107">In the left pane, under **Org-wide settings**, select **Teams upgrade**.</span></span>
3. <span data-ttu-id="e72cc-108">Teams のアップグレード ページの **[アプリの環境設定]** で、**[Skype for Business 会議に参加するユーザー向けの優先アプリ]** ドロップダウンリストから、**[Skype 会議アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e72cc-108">On the Teams upgrade page, under **App preferences**, select **Skype Meetings App**  from the **Preferred app for users to join Skype for Business meetings** drop-down list.</span></span>

    ![[Skype for Business 会議に参加するユーザー向けの優先アプリ] を選択する](media/teams-configure-skype-meetings-app-to-work-with-teams-image1.png)

## <a name="known-limitations"></a><span data-ttu-id="e72cc-110">既知の制限</span><span class="sxs-lookup"><span data-stu-id="e72cc-110">Known limitations</span></span>

<span data-ttu-id="e72cc-111">Teams と Skype 会議アプリを使うユーザーには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="e72cc-111">Users who use the Skype Meetings App with Teams are subject to the following limitations:</span></span>

- <span data-ttu-id="e72cc-112">ユーザーがビデオ デバイスを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e72cc-112">Users have no option to change their video device.</span></span>
- <span data-ttu-id="e72cc-113">ユーザーが Teams にアップグレードした後、ユーザーが Skype 会議アプリを使用して会議を行っているときに Teams で通話を受信した場合、Skype 会議アプリの会議は保留にされません。</span><span class="sxs-lookup"><span data-stu-id="e72cc-113">After a user is upgraded to Teams, if the user is in a meeting using the Skype Meetings App and then receives a call on Teams, the meeting in Skype Meetings App is not placed on hold.</span></span> <span data-ttu-id="e72cc-114">代わりに、ユーザーは両方の呼び出しに接続されます。</span><span class="sxs-lookup"><span data-stu-id="e72cc-114">Instead, the user is connected to both calls.</span></span>

## <a name="more-information"></a><span data-ttu-id="e72cc-115">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e72cc-115">More information</span></span>

- [<span data-ttu-id="e72cc-116">Skype 会議アプリ (Skype for Business Web アプリ) とは</span><span class="sxs-lookup"><span data-stu-id="e72cc-116">What is Skype Meetings App (Skype for Business Web App)</span></span>](https://support.office.microsoft.com/article/what-is-skype-meetings-app-skype-for-business-web-app-1ff3d412-718a-4982-8ff2-a4992608cdb5)
- <span data-ttu-id="e72cc-117">[Skype 会議アプリの最小ネットワーク要件](/previous-versions/office/communications/mt845808(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="e72cc-117">[Skype Meetings App minimum network requirements](/previous-versions/office/communications/mt845808(v=ocs.16))</span></span>