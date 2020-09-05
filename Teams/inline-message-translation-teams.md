---
title: インラインメッセージの翻訳を有効にする
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
description: Microsoft Teams 管理センターまたは PowerShell を使用して、Microsoft Teams でインライン翻訳を有効にする方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395386"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="58893-103">Microsoft Teams でのインラインメッセージの翻訳を無効にする</span><span class="sxs-lookup"><span data-stu-id="58893-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="58893-104">インラインメッセージの翻訳は、ユーザーがチームのメッセージを個人の言語設定で指定された [言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) に翻訳できる Microsoft Teams の機能です。</span><span class="sxs-lookup"><span data-stu-id="58893-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="58893-105">組織に対しては、インラインメッセージの翻訳が既定で展開されます。</span><span class="sxs-lookup"><span data-stu-id="58893-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="58893-106">ユーザーが Teams クライアント内でこの機能を使用できるようにする場合は、変更を加える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="58893-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="58893-107">このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。</span><span class="sxs-lookup"><span data-stu-id="58893-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="58893-108">PowerShell を使用してインラインメッセージの翻訳を無効にする</span><span class="sxs-lookup"><span data-stu-id="58893-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="58893-109">メッセージポリシーを使って、インラインメッセージの翻訳を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="58893-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="58893-110">ポリシーを無効にするには、 [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="58893-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="58893-111">ポリシーが適用されるには数分間かかります。</span><span class="sxs-lookup"><span data-stu-id="58893-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="58893-112">ユーザーは、サインアウトして再び Teams にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58893-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="58893-113">Microsoft Teams 管理センターを使用して、インラインメッセージの翻訳を無効にする</span><span class="sxs-lookup"><span data-stu-id="58893-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="58893-114">**Microsoft Teams 管理センター**で、左のナビゲーションから [**メッセージポリシー** ] を選び、新しいポリシーを作成するか、既存のポリシーを編集して、[**メッセージの翻訳**] オプションを [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="58893-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="58893-115">サービスは翻訳を行ってクライアントに配信し、コンプライアンスレコードでキャプチャされたコンテンツには影響しません。</span><span class="sxs-lookup"><span data-stu-id="58893-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="58893-116">翻訳の詳細については、「 [Microsoft Translator とは](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58893-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
