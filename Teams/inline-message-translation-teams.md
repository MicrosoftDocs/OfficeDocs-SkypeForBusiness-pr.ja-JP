---
title: Microsoft Teams でインライン メッセージの翻訳を使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
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
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016838"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="84382-103">Microsoft Teams でインライン メッセージの翻訳を使用する</span><span class="sxs-lookup"><span data-stu-id="84382-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="84382-104">インライン メッセージの翻訳は、新しい Microsoft Teams の機能で、ユーザーが Teams のメッセージを、Office 365 のパーソナル言語設定で指定した[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に自動的に翻訳できるようになります。</span><span class="sxs-lookup"><span data-stu-id="84382-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="84382-105">インライン メッセージ変換されていました、組織の既定の設定をします。</span><span class="sxs-lookup"><span data-stu-id="84382-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="84382-106">チーム クライアント内でこの機能を使用するユーザーを許可する場合を有効にしてこの設定で、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="84382-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="84382-107">現時点では、このオプションは、マイクロソフトのチームとのビジネス管理センターでは、Skype では使用できませんが、すぐにします。</span><span class="sxs-lookup"><span data-stu-id="84382-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="84382-108">このロールアウトは、Office 365 Government Community Cloud および Office 365 Germany の環境での Office 365 サブスクリプションから除外されています。</span><span class="sxs-lookup"><span data-stu-id="84382-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="84382-109">PowerShell を使用して有効にする</span><span class="sxs-lookup"><span data-stu-id="84382-109">Enable by using PowerShell</span></span>

<span data-ttu-id="84382-110">メッセージング ポリシーを使用することで、インライン メッセージの翻訳機能をオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="84382-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="84382-111">[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) コマンドレットを使用して、ポリシーをオンにします。</span><span class="sxs-lookup"><span data-stu-id="84382-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="84382-112">ポリシーは、適用には数分をかかります。</span><span class="sxs-lookup"><span data-stu-id="84382-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="84382-113">ユーザーがサインアウトして、チームにもう一度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84382-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="84382-114">Teams 管理センターを使用して有効にする</span><span class="sxs-lookup"><span data-stu-id="84382-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="84382-115">Teams 管理センターを使用してインライン メッセージの翻訳機能をオンにするオプションは、近日中に利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="84382-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="84382-116">翻訳とは、厳密には、クライアント側とは、コンテンツへの影響はキャプチャされません対応レコードで。</span><span class="sxs-lookup"><span data-stu-id="84382-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="84382-117">翻訳機能の詳細についてを参照してください[Microsoft Translator は何ですか?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。</span><span class="sxs-lookup"><span data-stu-id="84382-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>