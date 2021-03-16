---
title: Teams と共有する
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: ユーザーが Outlook から Teams の任意のチャットまたはチャネルにメールやメールの添付ファイルを共有できる Teams への共有機能について学習します。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80882bddae434b66f6a3e5988c08474859b37861
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819479"
---
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="302d7-103">Outlook から Teams と共有する</span><span class="sxs-lookup"><span data-stu-id="302d7-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="302d7-104">Outlook から Teams と共有 (Teams に共有) すると、ユーザーは Outlook から Teams 内の任意のチャットまたはチャネルに添付ファイルを含むメールを共有できます。</span><span class="sxs-lookup"><span data-stu-id="302d7-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="302d7-105">Outlook アドインで Teams と共有する</span><span class="sxs-lookup"><span data-stu-id="302d7-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="302d7-106">Teams への共有機能を使用するには、Outlook 用のアドインが必要です。</span><span class="sxs-lookup"><span data-stu-id="302d7-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="302d7-107">このアドインは、ユーザーが Teams Web アプリまたは Teams デスクトップ クライアントにログオンするたびに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="302d7-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="302d7-108">Outlook のアドインが正しく機能するように [、Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) の Outlook のアドインと [Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) のクライアント アクセス ルールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="302d7-108">Be sure to review [Add-ins for Outlook in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="302d7-109">また、接続エクスペリエンスを無効にすると、Outlook のアドインが正常に機能しなく場合があります。</span><span class="sxs-lookup"><span data-stu-id="302d7-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="302d7-110">詳細 [については、「接続エクスペリエンス」Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="302d7-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="302d7-111">Teams と共有する場合、ユーザーがチャネルをメールで送信する場合と同じトランスポート メカニズムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="302d7-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="302d7-112">チャットで共有するために、メール (メールの添付ファイルを含む) が送信者の OneDrive にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="302d7-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="302d7-113">チャネルと共有するために、メールと添付ファイルは SharePoint の **[電子** メール メッセージ] フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="302d7-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="302d7-114">Teams で共有する Outlook アドインでは、要件セット 1.7 を使用します。詳細については [、Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)アドインのドキュメントを参照してください。これには、Outlook アドインの詳細、Outlook アドインの環境要件、要件セット 1.7 でサポートされている特定の Outlook クライアントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="302d7-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="302d7-115">Teams への共有を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="302d7-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="302d7-116">次の PowerShell コマンドレットを使用して、Teams に共有する Outlook アドインをユーザーごとに選択的に無効または有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="302d7-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="302d7-117">アドインを無効にできるのは、アドインがインストールされた後のみです。</span><span class="sxs-lookup"><span data-stu-id="302d7-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="302d7-118">テナント内のすべてのユーザーに対して無効化を強制する場合は、スクリプトを定期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="302d7-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="302d7-119">Teams に共有するために使用される Outlook のアドインを無効にするには、ここで見つかった [コマンドレットを実行します](https://docs.microsoft.com/powershell/module/exchange/disable-app?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="302d7-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](https://docs.microsoft.com/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="302d7-120">Share to Teams で使用される Outlook のアドインを有効にするには、ここで見つかった [コマンドレットを実行します](https://docs.microsoft.com/powershell/module/exchange/enable-app?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="302d7-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](https://docs.microsoft.com/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="302d7-121">ブラウザーとシングル サインオン</span><span class="sxs-lookup"><span data-stu-id="302d7-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="302d7-122">Outlook on the web と Outlook デスクトップ クライアントの両方で Teams と共有するには、ブラウザーの WebView に依存します。</span><span class="sxs-lookup"><span data-stu-id="302d7-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="302d7-123">特定 [のブラウザーを使用Officeクライアント](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) の詳細については、アドインで使用されるブラウザーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="302d7-123">See [Browsers used by Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="302d7-124">Teams と共有するには、サード パーティの Cookie とローカル ストレージアクセスの両方をユーザーのブラウザーで有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="302d7-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="302d7-125">Teams との共有ではシングル サインオン (SSO) が使用されます。つまり、ユーザーは Teams への共有を介してアドインを使用するときに資格情報を入力する必要が生じます。</span><span class="sxs-lookup"><span data-stu-id="302d7-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="302d7-126">Outlook on the web 用 SSO は、既定 https://outlook.office365.com/owa/extSSO.aspx で https://outlook.office.com/owa/extSSO.aspx サポートされ、URL に返信します。</span><span class="sxs-lookup"><span data-stu-id="302d7-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="302d7-127">バニティ ドメインの場合、管理者は適切な Azure Active Directory 応答 URL を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="302d7-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>