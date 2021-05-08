---
title: インライン メッセージ翻訳を有効にする
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
description: 管理センターまたは PowerShell を使用して、Microsoft TeamsインラインMicrosoft Teamsを有効にする方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120628"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="155b1-103">メッセージのインライン翻訳をオフMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="155b1-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="155b1-104">インライン メッセージ翻訳は、ユーザー Microsoft Teamsの言語設定で指定された言語にTeamsメッセージ[](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)を翻訳できる機能です。</span><span class="sxs-lookup"><span data-stu-id="155b1-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="155b1-105">インライン メッセージの翻訳は、組織に対して既定で展開されます。</span><span class="sxs-lookup"><span data-stu-id="155b1-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="155b1-106">クライアント内でユーザーにこの機能の使用を許可する場合は、変更を加えるTeams必要があります。</span><span class="sxs-lookup"><span data-stu-id="155b1-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="155b1-107">このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。</span><span class="sxs-lookup"><span data-stu-id="155b1-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="155b1-108">PowerShell を使用してインライン メッセージ変換をオフにする</span><span class="sxs-lookup"><span data-stu-id="155b1-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="155b1-109">メッセージング ポリシーを使用して、インライン メッセージ変換をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="155b1-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="155b1-110">[Set-CsTeamsMessagingPolicy コマンドレットを使用してポリシーをオフ](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)にします。</span><span class="sxs-lookup"><span data-stu-id="155b1-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="155b1-111">ポリシーが適用されるには数分間かかります。</span><span class="sxs-lookup"><span data-stu-id="155b1-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="155b1-112">ユーザーは、サインアウトして再び Teams にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="155b1-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="155b1-113">管理センター Microsoft Teamsを使用して、インライン メッセージの翻訳をオフにする</span><span class="sxs-lookup"><span data-stu-id="155b1-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="155b1-114">Microsoft Teams **管理** センター で、左側のナビゲーションから [**メッセージング** ポリシー] を選択し、新しいポリシーを作成するか、既存のポリシーを編集し、[メッセージの翻訳] オプションを [オフ] に設定 **します**。</span><span class="sxs-lookup"><span data-stu-id="155b1-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="155b1-115">サービスは翻訳を行い、コンプライアンス レコードにキャプチャされたコンテンツに影響を与え、クライアントに配信します。</span><span class="sxs-lookup"><span data-stu-id="155b1-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="155b1-116">翻訳の詳細については、「Microsoft 翻訳とは[」を翻訳ツール。](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="155b1-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>