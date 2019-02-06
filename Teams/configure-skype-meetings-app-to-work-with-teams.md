---
title: チームで動作する Skype の会議アプリケーションを構成します。
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.date: 09/21/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 管理者は、マイクロソフトのチームの管理センターを使用して、チームで動作する Skype の会議アプリケーションを構成するのには
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e94598822ab321ea514bb41af2fa0e4f8ee57ff0
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754576"
---
<a name="configure-the-skype-meetings-app-to-work-with-teams"></a><span data-ttu-id="65ad8-103">チームで動作する Skype の会議アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="65ad8-103">Configure the Skype Meetings App to work with Teams</span></span>
===================================================

<span data-ttu-id="65ad8-104">マイクロソフトのチームにユーザーをアップグレードすると、管理者は Skype のビジネス ・ ミーティングに参加するのにユーザーが使用する優先のアプリケーションを指定するのにはマイクロソフト チームの管理センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="65ad8-104">After a user is upgraded to Microsoft Teams, admins can use the Microsoft Teams admin center to specify the preferred app that users will use to join Skype for Business meetings.</span></span>

<span data-ttu-id="65ad8-105">会議アプリケーションの優先アプリケーションとして、Skype を指定します。</span><span class="sxs-lookup"><span data-stu-id="65ad8-105">To specify the Skype for Meetings App as the preferred app:</span></span>

1. <span data-ttu-id="65ad8-106">マイクロソフトのチームの管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="65ad8-106">Sign in to the Microsoft Teams admin center.</span></span>
2. <span data-ttu-id="65ad8-107">**組織全体の設定**] の下の左側のウィンドウで [**チームのアップグレード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ad8-107">In the left pane, under **Org-wide settings**, select **Teams upgrade**.</span></span>
3. <span data-ttu-id="65ad8-108">チームに] ページの [**アプリケーションの環境設定**のアップグレードは、 **Skype のビジネス ・ ミーティングに参加するユーザーの優先アプリケーション**のドロップ ダウン リストから**Skype の会議アプリケーション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ad8-108">On the Teams upgrade page, under **App preferences**, select **Skype Meetings App**  from the **Preferred app for users to join Skype for Business meetings** drop-down list.</span></span>

![Skype をビジネス ・ ミーティングに参加するユーザーのアプリケーションを優先」を選択します。](media/configure-skype-meetings-app-to-work-with-teams.png)

## <a name="known-limitations"></a><span data-ttu-id="65ad8-110">既知の制限</span><span class="sxs-lookup"><span data-stu-id="65ad8-110">Known limitations</span></span>

<span data-ttu-id="65ad8-111">チームと Skype 会議アプリケーションを使用するユーザーは、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="65ad8-111">Users who use the Skype Meetings App with Teams are subject to the following limitations:</span></span>

- <span data-ttu-id="65ad8-112">ユーザーのビデオ デバイスを変更するオプションがあるないです。</span><span class="sxs-lookup"><span data-stu-id="65ad8-112">Users have no option to change their video device.</span></span>
- <span data-ttu-id="65ad8-113">ユーザー、チーム、ユーザーが Skype の会議アプリケーションを使用して会議に参加してチームの呼び出しを受信し、場合にアップグレードした後、保留中の Skype 会議アプリケーションでの会議は配置されません。</span><span class="sxs-lookup"><span data-stu-id="65ad8-113">After a user is upgraded to Teams, if the user is in a meeting using the Skype Meetings App and then receives a call on Teams, the meeting in Skype Meetings App is not placed on hold.</span></span> <span data-ttu-id="65ad8-114">代わりに、ユーザーは、両方の呼び出しに接続されます。</span><span class="sxs-lookup"><span data-stu-id="65ad8-114">Instead, the user is connected to both calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="65ad8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="65ad8-115">See also</span></span>

<span data-ttu-id="65ad8-116">Skype 会議アプリケーションの詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65ad8-116">For more information about the Skype Meetings App, see:</span></span>

- [<span data-ttu-id="65ad8-117">Skype 会議アプリケーション (Web アプリケーションのビジネスの Skype) とは</span><span class="sxs-lookup"><span data-stu-id="65ad8-117">What is Skype Meetings App (Skype for Business Web App)</span></span>](https://support.office.microsoft.com/article/what-is-skype-meetings-app-skype-for-business-web-app-1ff3d412-718a-4982-8ff2-a4992608cdb5)
- [<span data-ttu-id="65ad8-118">Skype 会議アプリの最小ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="65ad8-118">Skype Meetings App minimum network requirements</span></span>](https://technet.microsoft.com/library/mt845808.aspx)