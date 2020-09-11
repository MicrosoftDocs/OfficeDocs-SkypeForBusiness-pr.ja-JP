---
title: チームと Outlook のメールの統合
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: ユーザーが Outlook のメール間で情報を共有できるようにする機能や、Teams でのチャットやチャネルの会話など、チームと Outlook のメール統合機能について説明します。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 675834cd36c4e86d34d179e91fe66905e3860b32
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429443"
---
# <a name="teams-and-outlook-email-integration"></a><span data-ttu-id="84cda-103">チームと Outlook のメールの統合</span><span class="sxs-lookup"><span data-stu-id="84cda-103">Teams and Outlook email integration</span></span>

<span data-ttu-id="84cda-104">Microsoft Teams には、Outlook のメール間で簡単に情報を共有したり、チーム内でチャットやチャネルで会話したりすることができるようにする機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="84cda-104">Microsoft Teams includes features that make it easy for users in your organization to share information between email in Outlook and chat or channel conversations in Teams and to stay on top of missed conversations.</span></span> <span data-ttu-id="84cda-105">この記事では、これらの機能と、適用される管理コントロールの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="84cda-105">This article gives you an overview of these features and the admin controls that apply.</span></span>

## <a name="share-to-outlook"></a><span data-ttu-id="84cda-106">Outlook に共有</span><span class="sxs-lookup"><span data-stu-id="84cda-106">Share to Outlook</span></span>

<span data-ttu-id="84cda-107">[ **Outlook と共有] を**使用すると、チームの会話のコピーを outlook のメールに共有することができます。チームから脱退する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="84cda-107">**Share to Outlook** lets users share a copy of a Teams conversation to an email in Outlook, without having to leave Teams.</span></span> <span data-ttu-id="84cda-108">この機能は、ユーザーがすぐにチーム外のユーザーや組織のユーザーとの会話や状態の更新を共有する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="84cda-108">This feature is handy if users need to share conversations or status updates with users outside their immediate team or even your organization.</span></span> <span data-ttu-id="84cda-109">Teams のスレッドの一番上に移動して、[ **̇̇̇ More] オプション**を選び、[ **Outlook に共有**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="84cda-109">Go to the top of the conversation in Teams, select **˙˙˙ More options**, and then select **Share to Outlook**.</span></span>  <span data-ttu-id="84cda-110">詳細については、「 [Teams から Outlook への共有](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cda-110">To learn more, see [Share to Outlook from Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).</span></span>

![Teams の Outlook の共有機能を示すスクリーンショット](media/share-to-outlook.png)

<span data-ttu-id="84cda-112">この機能を使用するには、ユーザーに対して Outlook on the web を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84cda-112">To use this feature, Outlook on the web must be turned on for the user.</span></span> <span data-ttu-id="84cda-113">Outlook on the web がオフになっている場合、[ **outlook に共有** ] オプションはユーザーの Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="84cda-113">If Outlook on the web is turned off, the **Share to Outlook** option isn't displayed in Teams for the user.</span></span> <span data-ttu-id="84cda-114">Outlook on the web を有効または無効にする手順については、「 [outlook on the web on メールボックスを有効または無効](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cda-114">For steps on how to turn on and turn off Outlook on the web, see [Enable or disable Outlook on the web for a mailbox](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).</span></span>

## <a name="actionable-activity-emails"></a><span data-ttu-id="84cda-115">操作可能なアクティビティのメール</span><span class="sxs-lookup"><span data-stu-id="84cda-115">Actionable activity emails</span></span>

<span data-ttu-id="84cda-116">ユーザーは、チーム内の不在着信した会話を把握するのに役立つ、利用可能な不在時のメールを自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="84cda-116">Users automatically get actionable missed activity emails which help them to catch up on missed conversations in Teams.</span></span> <span data-ttu-id="84cda-117">[不在時のアクティビティ] メールには、不在着信メッセージの後に送信されたメッセージなど、スレッドからの最新の返信が表示されます。ユーザーは [ **返信** ] をクリックして、Outlook 内から直接返信することができます。</span><span class="sxs-lookup"><span data-stu-id="84cda-117">The missed activity emails show the latest replies from a conversation, including messages that were sent after the missed message, and users can click **Reply** to respond directly from within Outlook.</span></span> <span data-ttu-id="84cda-118">詳細については、「 [Outlook からの不在時のメールに返信する](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cda-118">To learn more, see [Reply to missed activity emails from Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).</span></span> 

> [!NOTE]
> <span data-ttu-id="84cda-119">この機能は、Outlook for Mac または古いバージョンの Outlook for Windows ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="84cda-119">This feature isn't supported in Outlook for Mac or some older versions of Outlook for Windows.</span></span> <span data-ttu-id="84cda-120">詳細については、「 [Outlook および Office 365 グループで](https://docs.microsoft.com/outlook/actionable-messages/)操作できるメッセージ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84cda-120">For more information, see [Actionable messages in Outlook and Office 365 Groups](https://docs.microsoft.com/outlook/actionable-messages/).</span></span>

![見逃したアクティビティのメールを示すスクリーンショット](media/missed-activity-email.png)

![不在時のメールに返信する方法を示すスクリーンショット](media/missed-activity-email-reply.png)

<span data-ttu-id="84cda-123">**SmtpActionableMessagesEnabled**パラメーターと共に、設定された[組織構成](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig)コマンドレットを使用して、アクション可能なメールをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="84cda-123">You can use the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet together with the **SmtpActionableMessagesEnabled** parameter to turn off actionable emails.</span></span> <span data-ttu-id="84cda-124">既定では、 **SmtpActionableMessagesEnabled** パラメーターは **true**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="84cda-124">By default, the **SmtpActionableMessagesEnabled** parameter is set to **true**.</span></span> <span data-ttu-id="84cda-125">このパラメーターを **false** に設定すると、Office 365 全体で操作可能なメールメッセージがオフになります。</span><span class="sxs-lookup"><span data-stu-id="84cda-125">Setting the parameter to **false** turns off actionable email messages across Office 365.</span></span> <span data-ttu-id="84cda-126">Teams ユーザーの場合は、Outlook で直接応答する [ **返信** ] オプションは、不在時のメールでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="84cda-126">For Teams users, this means that the **Reply** option to respond directly in Outlook isn't available in missed activity emails.</span></span> <span data-ttu-id="84cda-127">代わりに、不在中のアクティビティのメールには、teams で返信するための **[teams で返信** ] オプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="84cda-127">Instead, the missed activity emails include a **Reply in Teams** option for users to reply in Teams.</span></span>
