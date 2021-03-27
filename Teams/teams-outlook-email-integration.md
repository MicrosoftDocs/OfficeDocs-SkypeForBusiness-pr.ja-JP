---
title: Teams と Outlook のメールの統合
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: ユーザーが Outlook のメールと Teams のチャットまたはチャネルの会話の間で情報を共有できる機能を含む、Teams と Outlook のメール統合機能について説明します。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc1ce6eec084dfe2f4bb736f018352e0eb0e2c88
ms.sourcegitcommit: e55d1623e686db2b183e02052bfe10a0269abb5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2021
ms.locfileid: "51397560"
---
# <a name="teams-and-outlook-email-integration"></a><span data-ttu-id="63bd2-103">Teams と Outlook のメールの統合</span><span class="sxs-lookup"><span data-stu-id="63bd2-103">Teams and Outlook email integration</span></span>

<span data-ttu-id="63bd2-104">Microsoft Teams には、組織内のユーザーが Outlook のメールと Teams のチャットまたはチャネル会話の間で情報を簡単に共有し、見逃した会話を簡単に把握できる機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63bd2-104">Microsoft Teams includes features that make it easy for users in your organization to share information between email in Outlook and chat or channel conversations in Teams and to stay on top of missed conversations.</span></span> <span data-ttu-id="63bd2-105">この記事では、これらの機能と、適用される管理者のコントロールの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="63bd2-105">This article gives you an overview of these features and the admin controls that apply.</span></span>

## <a name="share-to-outlook"></a><span data-ttu-id="63bd2-106">Outlook と共有</span><span class="sxs-lookup"><span data-stu-id="63bd2-106">Share to Outlook</span></span>

<span data-ttu-id="63bd2-107">**Outlook と共有** すると、Teams を離れることなく、Outlook のメールに Teams の会話のコピーを共有できます。</span><span class="sxs-lookup"><span data-stu-id="63bd2-107">**Share to Outlook** lets users share a copy of a Teams conversation to an email in Outlook, without having to leave Teams.</span></span> <span data-ttu-id="63bd2-108">この機能は、ユーザーが直属のチーム以外のユーザーや組織外のユーザーと会話やステータスの更新を共有する必要がある場合に便利です。 </span><span class="sxs-lookup"><span data-stu-id="63bd2-108">This feature is handy if users need to share conversations or status updates with users outside their immediate team or even your organization.</span></span> <span data-ttu-id="63bd2-109">Teams で会話の一番上に移動し、[ **...その他のオプション**] を選択し、[**Outlook に共有する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63bd2-109">Go to the top of the conversation in Teams, select **˙˙˙ More options**, and then select **Share to Outlook**.</span></span>  <span data-ttu-id="63bd2-110">詳細については、「[Teams から Outlook に共有する](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63bd2-110">To learn more, see [Share to Outlook from Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).</span></span>

![Teams の [Outlook に共有する] 機能を示すスクリーンショット](media/share-to-outlook.png)

<span data-ttu-id="63bd2-112">この機能を使用するには、ユーザーに対して Outlook on the web がオンになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="63bd2-112">To use this feature, Outlook on the web must be turned on for the user.</span></span> <span data-ttu-id="63bd2-113">Outlook on the web がオフになっている場合は、**Teams** のユーザーに対して、[Outlook に共有する] のオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="63bd2-113">If Outlook on the web is turned off, the **Share to Outlook** option isn't displayed in Teams for the user.</span></span> <span data-ttu-id="63bd2-114">Outlook on the web をオンまたはオフにする手順については、「[メールボックスメールボックス用に Outlook on the web を有効または無効にする](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63bd2-114">For steps on how to turn on and turn off Outlook on the web, see [Enable or disable Outlook on the web for a mailbox](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).</span></span>

## <a name="actionable-activity-emails"></a><span data-ttu-id="63bd2-115">操作可能なアクティビティ メール</span><span class="sxs-lookup"><span data-stu-id="63bd2-115">Actionable activity emails</span></span>

<span data-ttu-id="63bd2-116">ユーザーは、Teams で会話を見落としがあった際の助けになる、操作可能な見落としのあるアクティビティ メールを自動的に受け取ります。</span><span class="sxs-lookup"><span data-stu-id="63bd2-116">Users automatically get actionable missed activity emails which help them to catch up on missed conversations in Teams.</span></span> <span data-ttu-id="63bd2-117">見落としがあったアクティビティ メールには、見落としたメッセージの後に送信されたメッセージなど、会話の最新の返信が表示されます。ユーザーは、[**返信**] をクリックして Outlook から直接返信できます。</span><span class="sxs-lookup"><span data-stu-id="63bd2-117">The missed activity emails show the latest replies from a conversation, including messages that were sent after the missed message, and users can click **Reply** to respond directly from within Outlook.</span></span> <span data-ttu-id="63bd2-118">詳細については、「[Outlook から送信された、見落としがあったアクティビティ メールに返信する](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63bd2-118">To learn more, see [Reply to missed activity emails from Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).</span></span> 

> [!NOTE]
> <span data-ttu-id="63bd2-119">この機能は、Outlook for Mac または一部の古いバージョンの Outlook for Windows ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63bd2-119">This feature isn't supported in Outlook for Mac or some older versions of Outlook for Windows.</span></span> <span data-ttu-id="63bd2-120">詳細については、「[Outlook および Office 365 グループの操作可能なメッセージ](/outlook/actionable-messages/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63bd2-120">For more information, see [Actionable messages in Outlook and Office 365 Groups](/outlook/actionable-messages/).</span></span>

![見落としがあったアクティビティ メールを表示したスクリーンショット](media/missed-activity-email.png)

![見落としがあったアクティビティ メールに返信する方法を表示したスクリーンショット](media/missed-activity-email-reply.png)

<span data-ttu-id="63bd2-123">[Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) コマンドレットと **SmtpActionableMessagesEnabled** パラメーターを使用して、操作可能なメールをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="63bd2-123">You can use the [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) cmdlet together with the **SmtpActionableMessagesEnabled** parameter to turn off actionable emails.</span></span> <span data-ttu-id="63bd2-124">既定では、**smtpActionableMessagesEnabled** パラメーターは、**true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="63bd2-124">By default, the **SmtpActionableMessagesEnabled** parameter is set to **true**.</span></span> <span data-ttu-id="63bd2-125">パラメーターを **false** に設定すると、Office 365 全体で操作可能なメール メッセージがオフになります。 </span><span class="sxs-lookup"><span data-stu-id="63bd2-125">Setting the parameter to **false** turns off actionable email messages across Office 365.</span></span> <span data-ttu-id="63bd2-126">Teams ユーザーの場合、Outlook で直接 **返信** するオプションは、見落としがあったアクティビティ メールには利用できません。</span><span class="sxs-lookup"><span data-stu-id="63bd2-126">For Teams users, this means that the **Reply** option to respond directly in Outlook isn't available in missed activity emails.</span></span> <span data-ttu-id="63bd2-127">その代わりに、見落としがあったアクティビティ メールには、[**Teams で返信する**] オプションが含まれ、ユーザーは Teams から返信することができます。</span><span class="sxs-lookup"><span data-stu-id="63bd2-127">Instead, the missed activity emails include a **Reply in Teams** option for users to reply in Teams.</span></span>

<span data-ttu-id="63bd2-128">Outlook および Office [365 グループのアクション可能なメッセージも参照してください](https://docs.microsoft.com/outlook/actionable-messages/)。</span><span class="sxs-lookup"><span data-stu-id="63bd2-128">See also [Actionable messages in Outlook and Office 365 Groups](https://docs.microsoft.com/outlook/actionable-messages/).</span></span>
