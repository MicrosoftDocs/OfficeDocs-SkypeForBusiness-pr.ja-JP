---
title: 先進認証を使用して Microsoft Teams にサインインする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 先進認証を使用して Microsoft Teams にサインインする方法について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9911a014fe3bd3e3ede151e2a85e8181c399e463
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790615"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="8f2a5-103">先進認証を使用して Microsoft Teams にサインインする</span><span class="sxs-lookup"><span data-stu-id="8f2a5-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="8f2a5-104">Microsoft Teams は先進認証を使用して、サインインエクスペリエンスをシンプルかつ安全な状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="8f2a5-105">ユーザーがチームにサインインする方法を確認するには、「 [teams にサインイン](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="8f2a5-106">先進認証のしくみ</span><span class="sxs-lookup"><span data-stu-id="8f2a5-106">How modern authentication works</span></span>

<span data-ttu-id="8f2a5-107">先進認証とは、ユーザーが既に資格情報 (仕事用のメールとパスワードなど) を別の場所に入力したことをチームに知らせるプロセスであり、アプリを開始するために再度入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="8f2a5-108">エクスペリエンスは、ユーザーが Windows または Mac で作業している場合など、いくつかの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="8f2a5-109">また、組織が単一要素認証を有効にしているか、多要素認証を有効にしているかによっても異なります (多要素認証では、通常、電話で資格情報を確認したり、固有のコードを提供したり、PIN を入力したりする必要があります)。拇印の提示。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="8f2a5-110">最新の認証シナリオの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="8f2a5-111">Windows ユーザー:</span><span class="sxs-lookup"><span data-stu-id="8f2a5-111">Windows users</span></span> 

- <span data-ttu-id="8f2a5-112">ユーザーが Office 365 エンタープライズアカウントを使用して他の Office アプリに既にサインインしている場合、チームを起動すると、そのアプリに直接移動します。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="8f2a5-113">資格情報を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="8f2a5-114">ユーザーが自分の Office 365 Enterprise アカウントにサインインしていない場合、そのユーザーが Teams を開始すると、組織での決定に応じて、単一要素認証または多要素認証 (SFA または MFA) を提供するように求められます。処理を行います。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="8f2a5-115">ユーザーがドメインに参加しているコンピューターにサインインしている場合、Teams を開始すると、組織で MFA を要求するか、またはコンピューターで既に MFA を要求しているかどうかによって、もう1つの認証手順を実行するように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="8f2a5-116">お客様のコンピューターに、サインインのために既に MFA が必要な場合は、チームを開くときにアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="8f2a5-117">ユーザーがドメインに参加しているコンピューターにサインインしていて、そのユーザー名が Teams のサインイン画面に事前に入力されていない場合、管理者は次の Windows レジストリを設定してユーザー名の事前作成を無効にすることができます。コンピューター \ HKEY_CURRENT_USER \ ソフトウェア \Microsoft\Office\Teams DisableUpnSuffixCheck (REG_DWORD) 0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="8f2a5-117">If users are signed in to a domain-joined computer and you don't want their user name pre-populated on the Teams sign-in screen, admins can set the following Windows registry to turn off pre-population of the user name: Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams DisableUpnSuffixCheck(REG_DWORD) 0x00000001 (1)</span></span>

  <span data-ttu-id="8f2a5-118">注: ユーザー名が ".local" または "corp" で終わるユーザー名の入力を省略すると、既定ではオンになっているため、レジストリキーを設定しなくても無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-118">Note: Skipping user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="8f2a5-119">Mac ユーザー</span><span class="sxs-lookup"><span data-stu-id="8f2a5-119">Mac users</span></span> 

<span data-ttu-id="8f2a5-120">ユーザーが Teams を開始すると、そのコンピューターは、Office 365 エンタープライズアカウントまたは他の Office アプリケーションから資格情報を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-120">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="8f2a5-121">代わりに、組織の設定に応じて、SFA または MFA の入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-121">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="8f2a5-122">ユーザーが資格情報を入力すると、もう一度提供する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-122">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="8f2a5-123">この時点で、チームは同じコンピューターで作業しているときに自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-123">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="8f2a5-124">先進認証が完了した後でアカウントを切り替える</span><span class="sxs-lookup"><span data-stu-id="8f2a5-124">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="8f2a5-125">ユーザーがドメインに参加しているコンピューターで作業している場合 (たとえば、テナントが Kerberos を有効にしている場合)、先進認証を完了した後でユーザーアカウントを切り替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-125">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="8f2a5-126">ドメインに参加しているコンピューターでユーザーが作業していない場合は、アカウントを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-126">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="8f2a5-127">先進認証が完了した後に Microsoft Teams からサインアウトする</span><span class="sxs-lookup"><span data-stu-id="8f2a5-127">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="8f2a5-128">Teams からサインアウトするには、アプリの上部にあるプロフィール写真をクリックして、[**サインアウト**] を選択します。また、タスクバーのアプリアイコンを右クリックし、[**ログアウト**] を選択することもできます。チームからサインアウトすると、アプリを起動するために資格情報を再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-128">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="8f2a5-129">Url と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="8f2a5-129">URLs and IP address ranges</span></span>
<span data-ttu-id="8f2a5-130">チームにはインターネットへの接続が必要。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-130">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="8f2a5-131">Office 365 プラン、行政機関、その他のクラウドで Teams を使用するユーザーにとって到達可能なエンドポイントについて理解するには、[次のガイダンス](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-131">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, please read the [guidance available here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="8f2a5-132">これに加えて、へのアクセスも許可する必要がhttps://ssl.gstatic.comあります。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-132">In addition to this, you'd need to also allow access to https://ssl.gstatic.com.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="8f2a5-133">先進認証のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8f2a5-133">Troubleshooting modern authentication</span></span>

<span data-ttu-id="8f2a5-134">新しい認証は Teams を使用するすべての組織で利用できます。そのため、ユーザーが処理を完了できない場合は、自分のドメインまたは組織の Office 365 エンタープライズアカウントに問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-134">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="8f2a5-135">詳細については、「 [Microsoft Teams へのサインインで問題が発生するのはなぜですか?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f2a5-135">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

