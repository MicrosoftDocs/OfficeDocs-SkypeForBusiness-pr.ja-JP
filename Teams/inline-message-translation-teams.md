---
title: Microsoft Teams でインラインメッセージの翻訳を有効にする
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でインラインの翻訳を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f6c6a2eca313b70640dbf61a87c6c5742ea318
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570737"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="ab102-103">Microsoft Teams でインラインメッセージの翻訳を有効にする</span><span class="sxs-lookup"><span data-stu-id="ab102-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="ab102-104">インラインメッセージの翻訳は、ユーザーが Office 365 の個人の言語設定で指定された[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)にチームのメッセージを翻訳できるようにする、Microsoft Teams の新機能です。</span><span class="sxs-lookup"><span data-stu-id="ab102-104">Inline message translation is a new Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="ab102-105">インライン メッセージの翻訳は、所属する組織に対しては既定でロール アウトされています。</span><span class="sxs-lookup"><span data-stu-id="ab102-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="ab102-106">Teams クライアント内でユーザーがこの機能を使用することができるようにする場合、この設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab102-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="ab102-107">このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。</span><span class="sxs-lookup"><span data-stu-id="ab102-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="ab102-108">PowerShell を使用してインラインメッセージの翻訳を有効にする</span><span class="sxs-lookup"><span data-stu-id="ab102-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="ab102-109">メッセージポリシーを使って、インラインメッセージの翻訳を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab102-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="ab102-110">[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用して、ポリシーをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ab102-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="ab102-111">ポリシーが適用されるには数分間かかります。</span><span class="sxs-lookup"><span data-stu-id="ab102-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="ab102-112">ユーザーは、サインアウトして再び Teams にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab102-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="ab102-113">Microsoft Teams 管理センターを使用して、インラインメッセージの翻訳を有効にする</span><span class="sxs-lookup"><span data-stu-id="ab102-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="ab102-114">**Microsoft Teams 管理センター**で、左のナビゲーションから [**メッセージポリシー** ] を選び、新しいポリシーを作成するか、既存のポリシーを編集して、[**メッセージの翻訳を許可**する] オプションを **[オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="ab102-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="ab102-115">サービスは翻訳を行ってクライアントに配信し、コンプライアンスレコードでキャプチャされたコンテンツには影響しません。</span><span class="sxs-lookup"><span data-stu-id="ab102-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="ab102-116">翻訳の詳細については、「[Microsoft Translator とは](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ab102-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>