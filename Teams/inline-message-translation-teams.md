---
title: Microsoft Teams でインラインメッセージの翻訳を有効にする
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でインラインの翻訳を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: dfd0582837b2e9c9859b44292255e5e42a2f35a4
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222070"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="808a8-103">Microsoft Teams でインラインメッセージの翻訳を有効にする</span><span class="sxs-lookup"><span data-stu-id="808a8-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="808a8-104">インライン メッセージの翻訳は、新しい Microsoft Teams の機能で、ユーザーが Teams のメッセージを、Office 365 のパーソナル言語設定で指定した[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に自動的に翻訳できるようになります。</span><span class="sxs-lookup"><span data-stu-id="808a8-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="808a8-105">インライン メッセージの翻訳は、所属する組織に対しては既定でロール アウトされています。</span><span class="sxs-lookup"><span data-stu-id="808a8-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="808a8-106">Teams クライアント内でユーザーがこの機能を使用することができるようにする場合、この設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="808a8-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="808a8-107">このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。</span><span class="sxs-lookup"><span data-stu-id="808a8-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="808a8-108">PowerShell を使用してインラインメッセージの翻訳を有効にする</span><span class="sxs-lookup"><span data-stu-id="808a8-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="808a8-109">メッセージポリシーを使って、インラインメッセージの翻訳を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="808a8-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="808a8-110">[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用して、ポリシーをオンにします。</span><span class="sxs-lookup"><span data-stu-id="808a8-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="808a8-111">ポリシーが適用されるには数分間かかります。</span><span class="sxs-lookup"><span data-stu-id="808a8-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="808a8-112">ユーザーは、サインアウトして再び Teams にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="808a8-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="808a8-113">Microsoft Teams 管理センターを使用して、インラインメッセージの翻訳を有効にする</span><span class="sxs-lookup"><span data-stu-id="808a8-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="808a8-114">**Microsoft Teams 管理センター**で、左のナビゲーションから [**メッセージポリシー** ] を選び、新しいポリシーを作成するか、既存のポリシーを編集して、[**メッセージの翻訳を許可**する] オプションを **[オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="808a8-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="808a8-115">サービスは翻訳を行ってクライアントに配信し、コンプライアンスレコードでキャプチャされたコンテンツには影響しません。</span><span class="sxs-lookup"><span data-stu-id="808a8-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="808a8-116">翻訳の詳細については、「[Microsoft Translator とは](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="808a8-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>