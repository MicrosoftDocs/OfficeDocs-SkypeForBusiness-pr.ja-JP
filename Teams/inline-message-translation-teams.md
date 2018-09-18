---
title: Microsoft Teams でインライン メッセージの翻訳を使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でインラインの翻訳を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 191fe1e5517fdce9aba6fd17e084c866df200e82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882909"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="158d8-103">Microsoft Teams でインライン メッセージの翻訳を使用する</span><span class="sxs-lookup"><span data-stu-id="158d8-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="158d8-104">インライン メッセージの翻訳は、新しい Microsoft Teams の機能で、ユーザーが Teams のメッセージを、Office 365 のパーソナル言語設定で指定した[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に自動的に翻訳できるようになります。</span><span class="sxs-lookup"><span data-stu-id="158d8-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="158d8-105">インライン メッセージの翻訳は、所属する組織に対しては既定でロール アウトされています。</span><span class="sxs-lookup"><span data-stu-id="158d8-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="158d8-106">Teams クライアント内でユーザーがこの機能を使用することができるようにする場合、PowerShell を使用してこの設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="158d8-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="158d8-107">現在、このオプションは Microsoft Teams と Skype for Business の管理センターでは利用できませんが、近日中に利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="158d8-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="158d8-108">このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。</span><span class="sxs-lookup"><span data-stu-id="158d8-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="158d8-109">PowerShell を使用して有効にする</span><span class="sxs-lookup"><span data-stu-id="158d8-109">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="158d8-110">メッセージング ポリシーを使用することで、インライン メッセージの翻訳機能をオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="158d8-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="158d8-111">[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用して、ポリシーをオンにします。</span><span class="sxs-lookup"><span data-stu-id="158d8-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="158d8-112">ポリシーが適用されるには数分間かかります。</span><span class="sxs-lookup"><span data-stu-id="158d8-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="158d8-113">ユーザーは、サインアウトして再び Teams にサインインする必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="158d8-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="158d8-114">Teams 管理センターを使用して有効にする</span><span class="sxs-lookup"><span data-stu-id="158d8-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="158d8-115">Teams 管理センターを使用してインライン メッセージの翻訳機能をオンにするオプションは、近日中に利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="158d8-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="158d8-116">翻訳は完全にクライアント側によるものであり、コンプライアンスの記録で取得されたコンテンツには影響しません。</span><span class="sxs-lookup"><span data-stu-id="158d8-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="158d8-117">翻訳の詳細については、「[Microsoft Translator とは](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="158d8-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>