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
ms.openlocfilehash: 2afc1d0374333fdbb0bec9246d04224c6a82f032
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532703"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="79760-103">Microsoft Teams でインライン メッセージの翻訳を使用する</span><span class="sxs-lookup"><span data-stu-id="79760-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="79760-104">インライン メッセージの翻訳は、新しい Microsoft Teams の機能で、ユーザーが Teams のメッセージを、Office 365 のパーソナル言語設定で指定した[言語](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)に自動的に翻訳できるようになります。</span><span class="sxs-lookup"><span data-stu-id="79760-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="79760-105">インライン メッセージの翻訳は、所属する組織に対しては既定でロール アウトされています。</span><span class="sxs-lookup"><span data-stu-id="79760-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="79760-106">チーム クライアント内でこの機能を使用するユーザーを許可する場合は、この設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79760-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="79760-107">このロールアウトは、Office 365 の政府コミュニティ クラウドと Office 365 のドイツの環境での Office 365 サブスクリプションから除外されます。</span><span class="sxs-lookup"><span data-stu-id="79760-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="enable-by-using-powershell"></a><span data-ttu-id="79760-108">PowerShell を使用して有効にします。</span><span class="sxs-lookup"><span data-stu-id="79760-108">Enable by using PowerShell</span></span>

<span data-ttu-id="79760-109">インライン メッセージの翻訳機能をオンするには、メッセージング ポリシーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="79760-109">You can turn on the inline message translation feature by using the Messaging Policy.</span></span>

1. <span data-ttu-id="79760-110">[セット CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)コマンドレットを使用してポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="79760-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="79760-111">ポリシーは、適用には数分をかかります。</span><span class="sxs-lookup"><span data-stu-id="79760-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="79760-112">ユーザーがサインアウトして、チームにもう一度サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79760-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="79760-113">ビジネス管理センターの Microsoft のチームと Skype を使用して有効にします。</span><span class="sxs-lookup"><span data-stu-id="79760-113">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="79760-114">**マイクロソフト チームとビジネス管理センターの Skype**で、**メッセージング ポリシー**を選択して、左側のバーからか、新しいポリシーを作成または既存のポリシーを編集し、**に**メッセージを変換するユーザーを許可する**オプションを設定します。**.</span><span class="sxs-lookup"><span data-stu-id="79760-114">In the **Microsoft Teams & Skype for Business Admin Center**, select **Messaging Policies** from the left-hand bar, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
><span data-ttu-id="79760-115">翻訳はサービスによって実行し、対応レコード内でキャプチャされたコンテンツに影響をクライアントに配信します。</span><span class="sxs-lookup"><span data-stu-id="79760-115">Translation is done by the service and delivered to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="79760-116">翻訳機能の詳細についてを参照してください[Microsoft Translator は何ですか?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)。</span><span class="sxs-lookup"><span data-stu-id="79760-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>