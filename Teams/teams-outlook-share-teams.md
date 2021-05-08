---
title: 共有を共有Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: ユーザーが Teams からメールやメールの添付ファイルを Outlook 内の任意のチャットまたはチャネルに共有できる共有機能についてTeams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098223"
---
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="81ba6-103">共有してTeamsからOutlook</span><span class="sxs-lookup"><span data-stu-id="81ba6-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="81ba6-104">Outlook から Teams への共有( 共有 ) を使用すると、Outlook から Teams 内の任意のチャットまたはチャネルに添付ファイルを含むメールを共有できます。 Teams</span><span class="sxs-lookup"><span data-stu-id="81ba6-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="81ba6-105">Outlook共有用のアドインのTeams</span><span class="sxs-lookup"><span data-stu-id="81ba6-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="81ba6-106">[共有] Teams機能を使用するには、アプリのアドインがOutlook。</span><span class="sxs-lookup"><span data-stu-id="81ba6-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="81ba6-107">このアドインは、ユーザーが Teams Web アプリまたはデスクトップ クライアントにログオンするたびにTeamsインストールされます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="81ba6-108">Exchange Online の[Exchange Online Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)とクライアント アクセス規則の Outlook の[](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)アドインを確認して、Outlook のアドインが正しく機能Outlookしてください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-108">Be sure to review [Add-ins for Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="81ba6-109">また、接続されたエクスペリエンスを無効にすると、アプリのアドインがOutlook動作しなく場合があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="81ba6-110">詳細については[、「Office 接続](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)エクスペリエンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="81ba6-111">[共有Teamsユーザーがチャネルを電子メールで送信する場合と同じトランスポート メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="81ba6-112">チャットと共有するために、メール (メールの添付ファイルを含む) は送信者のメール アドレスにOneDrive。</span><span class="sxs-lookup"><span data-stu-id="81ba6-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="81ba6-113">チャネルと共有するために、メールと添付ファイルは、SharePoint の[電子メール メッセージ] フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="81ba6-114">Teams への共有用 Outlook アドインでは[、Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)アドインのドキュメントで詳しく説明されている要件セット 1.7 を使用します。このドキュメントには、Outlook アドイン、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定の Outlook クライアントの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="81ba6-115">共有を有効または無効にするTeams</span><span class="sxs-lookup"><span data-stu-id="81ba6-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="81ba6-116">次Outlook PowerShell コマンドレットを使用して、Teams共有アドインをユーザーごとに選択的に無効にしたり、有効にしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="81ba6-117">アドインを無効にできるのは、アドインがインストールされた後のみです。</span><span class="sxs-lookup"><span data-stu-id="81ba6-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="81ba6-118">テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="81ba6-119">Share で使用されるアドインのアドインOutlookを無効にするには、Teams にある[コマンドレットを実行します](/powershell/module/exchange/disable-app?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="81ba6-120">Share が使用するアドインのアドインOutlookを有効にするには、Teams コマンドレット[を実行します](/powershell/module/exchange/enable-app?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="81ba6-121">ブラウザーとシングル サインオン</span><span class="sxs-lookup"><span data-stu-id="81ba6-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="81ba6-122">Web 上Teamsクライアントとデスクトップ Outlookの両方で、ブラウザーの WebView に依存Outlook共有します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="81ba6-123">どの[クライアントが特定のブラウザー Office使用](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)しているかの詳細については、アドインで使用されるブラウザーに関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-123">See [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="81ba6-124">[共有Teams、サード パーティの Cookie とローカル ストレージアクセスの両方をユーザーのブラウザーで有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="81ba6-125">[共有Teams シングル サインオン (SSO) を使用します。つまり、ユーザーは Share から Teams 経由でアドインを使用するときに資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="81ba6-126">Web 上Outlookの SSO では、既定 https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx でサポートおよび応答 URL がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="81ba6-127">バニティ ドメインの場合、管理者は適切な応答 URL をAzure Active Directoryする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>