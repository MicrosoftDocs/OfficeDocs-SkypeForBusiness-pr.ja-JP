---
title: Microsoft Teams でインライン メッセージの翻訳を使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でインラインの翻訳を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69c6e8046b185cc8dbc85ac0c99dc5b4cfa6fe2a
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851569"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="71f2e-103">Microsoft Teams でインライン メッセージの翻訳を使用する</span><span class="sxs-lookup"><span data-stu-id="71f2e-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="71f2e-104">インライン メッセージの翻訳は、新しい Microsoft Teams の機能で、ユーザーが Teams のメッセージを、Office 365 のパーソナル言語設定で指定した[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に自動的に翻訳できるようになります。</span><span class="sxs-lookup"><span data-stu-id="71f2e-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="71f2e-105">インライン メッセージの翻訳は、所属する組織に対しては既定でロール アウトされています。</span><span class="sxs-lookup"><span data-stu-id="71f2e-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="71f2e-106">Teams クライアント内でユーザーがこの機能を使用することができるようにする場合、PowerShell を使用してこの設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f2e-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="71f2e-107">現在、このオプションは Microsoft Teams と Skype for Business の管理センターでは利用できませんが、近日中に利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="71f2e-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="71f2e-108">このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。</span><span class="sxs-lookup"><span data-stu-id="71f2e-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="71f2e-109">PowerShell を使用して有効にする</span><span class="sxs-lookup"><span data-stu-id="71f2e-109">Enable by using PowerShell</span></span>

<span data-ttu-id="71f2e-110">メッセージング ポリシーを使用することで、インライン メッセージの翻訳機能をオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="71f2e-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="71f2e-111">[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用して、ポリシーをオンにします。</span><span class="sxs-lookup"><span data-stu-id="71f2e-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="71f2e-112">ポリシーが適用されるには数分間かかります。</span><span class="sxs-lookup"><span data-stu-id="71f2e-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="71f2e-113">ユーザーは、サインアウトして再び Teams にサインインする必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71f2e-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="71f2e-114">ビジネス管理センターの Microsoft のチームと Skype を使用して有効にします。</span><span class="sxs-lookup"><span data-stu-id="71f2e-114">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="71f2e-115">ビジネス管理センターの Microsoft のチームと Skype を使用してインライン メッセージの翻訳機能を有効にするオプションがもうすぐ完成です。</span><span class="sxs-lookup"><span data-stu-id="71f2e-115">The option to turn on the inline message translation feature using the Microsoft Teams & Skype for Business Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="71f2e-116">翻訳は完全にクライアント側によるものであり、コンプライアンスの記録で取得されたコンテンツには影響しません。</span><span class="sxs-lookup"><span data-stu-id="71f2e-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="71f2e-117">翻訳の詳細については、「[Microsoft Translator とは](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="71f2e-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>