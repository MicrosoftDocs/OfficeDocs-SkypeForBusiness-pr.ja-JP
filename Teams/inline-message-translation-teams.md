---
title: インライン メッセージの変換を使用して、マイクロソフトのチームで
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Priority
search.appverid: MET150
description: マイクロソフトのチームでのインライン変換を使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb7876d015fb736785fdaab99b1ed71b8e05b9dc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855822"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="fddf3-103">インライン メッセージの変換を使用して、マイクロソフトのチームで</span><span class="sxs-lookup"><span data-stu-id="fddf3-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="fddf3-104">インライン メッセージの変換は、自動的にチームのメッセージを Office 365 の場合は、その個人の言語設定で指定された[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に翻訳することができる新しいマイクロソフトのチーム機能です。</span><span class="sxs-lookup"><span data-stu-id="fddf3-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="fddf3-105">インライン メッセージ変換されていました、組織の既定の設定をします。</span><span class="sxs-lookup"><span data-stu-id="fddf3-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="fddf3-106">チーム クライアント内でこの機能を使用するユーザーを許可する場合を有効にしてこの設定で、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="fddf3-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="fddf3-107">現時点では、このオプションは、マイクロソフトのチームとのビジネス管理センターでは、Skype では使用できませんが、すぐにします。</span><span class="sxs-lookup"><span data-stu-id="fddf3-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="fddf3-108">このロールアウトは、Office 365 の政府コミュニティ クラウドと Office 365 のドイツの環境での Office 365 サブスクリプションから除外されます。</span><span class="sxs-lookup"><span data-stu-id="fddf3-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="fddf3-109">PowerShell を使用して有効にします。</span><span class="sxs-lookup"><span data-stu-id="fddf3-109">Enable by using PowerShell</span></span>

<span data-ttu-id="fddf3-110">インライン メッセージの翻訳機能をオンするには、メッセージング ポリシーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="fddf3-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="fddf3-111">[セット CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)コマンドレットを使用してポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fddf3-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="fddf3-112">ポリシーは、適用には数分をかかります。</span><span class="sxs-lookup"><span data-stu-id="fddf3-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="fddf3-113">ユーザーがサインアウトして、チームにもう一度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fddf3-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="fddf3-114">チーム管理センターを使用して有効にします。</span><span class="sxs-lookup"><span data-stu-id="fddf3-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="fddf3-115">チーム管理センターを使用して、インライン メッセージの翻訳機能を有効にするオプションがもうすぐ完成です。</span><span class="sxs-lookup"><span data-stu-id="fddf3-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="fddf3-116">翻訳とは、厳密には、クライアント側とは、コンテンツへの影響はキャプチャされません対応レコードで。</span><span class="sxs-lookup"><span data-stu-id="fddf3-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="fddf3-117">翻訳機能の詳細についてを参照してください[Microsoft Translator は何ですか?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。</span><span class="sxs-lookup"><span data-stu-id="fddf3-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>