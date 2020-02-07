---
title: Teams と連動するように Skype 会議アプリを構成する
ms.reviewer: ''
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
description: 管理者は、Microsoft Teams 管理センターを使用して、チームと連携するように Skype 会議アプリを構成することができます。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6d2725b3419283d5588882356c7334bb3d33405
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825525"
---
<a name="configure-the-skype-meetings-app-to-work-with-teams"></a><span data-ttu-id="63e59-103">Teams と連動するように Skype 会議アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="63e59-103">Configure the Skype Meetings App to work with Teams</span></span>
===================================================

<span data-ttu-id="63e59-104">ユーザーを Microsoft Teams にアップグレードした後、管理者は Microsoft Teams 管理センターを使用して、ユーザーが Skype for Business 会議に参加するために使用する優先アプリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="63e59-104">After a user is upgraded to Microsoft Teams, admins can use the Microsoft Teams admin center to specify the preferred app that users will use to join Skype for Business meetings.</span></span>

<span data-ttu-id="63e59-105">Skype for 会議アプリを優先アプリとして指定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63e59-105">To specify the Skype for Meetings App as the preferred app:</span></span>

1. <span data-ttu-id="63e59-106">Microsoft Teams 管理センターにサインインする。</span><span class="sxs-lookup"><span data-stu-id="63e59-106">Sign in to the Microsoft Teams admin center.</span></span>
2. <span data-ttu-id="63e59-107">左側のウィンドウで、[**組織全体の設定**] の下の [**チームのアップグレード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63e59-107">In the left pane, under **Org-wide settings**, select **Teams upgrade**.</span></span>
3. <span data-ttu-id="63e59-108">チームのアップグレードページの [**アプリの環境設定**] で、[ユーザーが**skype for business 会議に参加するための優先アプリ**] ドロップダウンリストから [ **skype 会議アプリ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="63e59-108">On the Teams upgrade page, under **App preferences**, select **Skype Meetings App**  from the **Preferred app for users to join Skype for Business meetings** drop-down list.</span></span>

    ![ユーザーが Skype for Business 会議に参加するための優先アプリを選ぶ](media/teams-configure-skype-meetings-app-to-work-with-teams-image1.png)

## <a name="known-limitations"></a><span data-ttu-id="63e59-110">既知の制限</span><span class="sxs-lookup"><span data-stu-id="63e59-110">Known limitations</span></span>

<span data-ttu-id="63e59-111">チームで Skype 会議アプリを使用するユーザーには、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="63e59-111">Users who use the Skype Meetings App with Teams are subject to the following limitations:</span></span>

- <span data-ttu-id="63e59-112">ユーザーには、ビデオデバイスを変更するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="63e59-112">Users have no option to change their video device.</span></span>
- <span data-ttu-id="63e59-113">ユーザーが Teams にアップグレードされた後、ユーザーが Skype 会議アプリを使用して会議に参加していて、チームで通話を受信した場合、Skype 会議アプリの会議は保留になりません。</span><span class="sxs-lookup"><span data-stu-id="63e59-113">After a user is upgraded to Teams, if the user is in a meeting using the Skype Meetings App and then receives a call on Teams, the meeting in Skype Meetings App is not placed on hold.</span></span> <span data-ttu-id="63e59-114">代わりに、ユーザーは両方の通話に接続されます。</span><span class="sxs-lookup"><span data-stu-id="63e59-114">Instead, the user is connected to both calls.</span></span>

## <a name="more-information"></a><span data-ttu-id="63e59-115">More information</span><span class="sxs-lookup"><span data-stu-id="63e59-115">More information</span></span>

- [<span data-ttu-id="63e59-116">Skype 会議アプリ (Skype for Business Web App) とは</span><span class="sxs-lookup"><span data-stu-id="63e59-116">What is Skype Meetings App (Skype for Business Web App)</span></span>](https://support.office.microsoft.com/article/what-is-skype-meetings-app-skype-for-business-web-app-1ff3d412-718a-4982-8ff2-a4992608cdb5)
- [<span data-ttu-id="63e59-117">Skype 会議アプリの最小ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="63e59-117">Skype Meetings App minimum network requirements</span></span>](https://technet.microsoft.com/library/mt845808.aspx)
