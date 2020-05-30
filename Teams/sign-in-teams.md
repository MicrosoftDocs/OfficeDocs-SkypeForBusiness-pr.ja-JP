---
title: 先進認証を使用して Teams にサインインする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 先進認証のしくみ、アカウントの切り替え方法、先進認証のトラブルシューティングについて説明します。 サインイン時に、事前入力されているユーザーの名前 (UPN) を無視するように Teams に指示する方法についても説明します。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63bfd0cb9fe4292b180dfc6a0c7852b3c90a8bc4
ms.sourcegitcommit: 624bd511b96cf213483d3ea8f27b20a91d955550
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330542"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="0d2cf-104">先進認証を使用して Microsoft Teams にサインインする</span><span class="sxs-lookup"><span data-stu-id="0d2cf-104">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="0d2cf-105">Microsoft は、組織が ハイブリッド ドメイン参加構成か Azure AD 参加構成のいずれかで Windows 10 の最新バージョンを使用することを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-105">Microsoft recommends that organizations use recent versions of Windows 10 with either Hybrid Domain Join or Azure AD Join configuration.</span></span> <span data-ttu-id="0d2cf-106">これにより、Windows の Web アカウント マネージャーでユーザーのアカウントが準備され、Teams や他の Microsoft アプリケーションへのシングル サインオンが可能になります。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-106">This ensures that users’ accounts are primed in Windows’ Web Account Manager, which in turns enables single sign-on to Teams and other Microsoft applications.</span></span> <span data-ttu-id="0d2cf-107">これにより、ユーザー エクスペリエンス (サイレント サインイン) と、セキュリティに対する姿勢を改善します。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-107">This provides a better user experience (silent sign-in) and a better security posture.</span></span>

<span data-ttu-id="0d2cf-108">Microsoft Teams は先進認証を使用して、サインイン操作をシンプルかつ安全なものとしています。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-108">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="0d2cf-109">ユーザーが Teams にサインインする方法については、「[Teams にサインインする](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-109">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="0d2cf-110">先進認証のしくみ</span><span class="sxs-lookup"><span data-stu-id="0d2cf-110">How modern authentication works</span></span>

<span data-ttu-id="0d2cf-111">先進認証とは、ユーザーが資格情報 (職場のメールやパスワードなど) を既に別の場所に入力したことを Teams に知らせ、ユーザーが資格情報を再度入力することを要求されることなくアプリを起動できるようにするためのプロセスです。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-111">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="0d2cf-112">ユーザーが Windows を使用しているのか Mac を使用しているのかなど、いつくかの要因によってエクスペリエンスは異なります。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-112">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="0d2cf-113">また、組織で単一要素認と多要素認証のいずれが有効にされているかによってもエクスペリエンスは異なります (多要素認証では通常、電話での資格情報の確認、一意のコードの提供、PIN の入力、または拇印の提示を行う必要があります)。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-113">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="0d2cf-114">以下は、それぞれの先進認証シナリオの簡単な説明です。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-114">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="0d2cf-115">Windows ユーザー</span><span class="sxs-lookup"><span data-stu-id="0d2cf-115">Windows users</span></span>

- <span data-ttu-id="0d2cf-116">ユーザーが自分の職場または学校アカウントを使用して既に Windows や別の Office アプリにサインインしている場合、ユーザーが Teams を起動すると、直ちにアプリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-116">If users have already signed in to Windows or to other Office apps with their work or school account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="0d2cf-117">ユーザーが資格情報を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-117">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="0d2cf-118">Microsoft では、最高のシングル サインオン エクスペリエンスを得るために、Windows 10 のバージョン 1903 以降の使用を推奨しています。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-118">Microsoft recommends using Windows 10 version 1903 or later for the best Single Sign-On experience.</span></span>

- <span data-ttu-id="0d2cf-119">ユーザーが自分の職場または学校アカウントにいずれのアプリからもサインインしていない場合、ユーザーが Teams を起動すると、組織で単一要素認と多要素認証 (SFA または MFA) のどちらを求める設定になっているかにより、ユーザーはいずれかの認証を提供するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-119">If users are not signed in to their Microsoft work or school account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="0d2cf-120">ドメインに参加しているコンピューターにユーザーがサインインしている場合、ユーザーが Teams を起動すると、MFA を要求するように組織で設定されているかどうか、または、ユーザーのコンピューターへのサインインで既に MFA が要求されているのかどうかにより、もう 1 つ別の認証手順を実行するよう求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-120">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="0d2cf-121">コンピューターへのサインインで既に MFA が要求されている場合、ユーザーが Teams を開くとアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-121">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="0d2cf-122">ドメインに参加している PC では、SSO が利用できない場合に、Teams がログイン画面にユーザー プリンシパル名 (UPN) を事前に入力しておく場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-122">On Domain joined PCs, when SSO isn't possible Teams may pre-fill its login screen with the user principal name (UPN).</span></span> <span data-ttu-id="0d2cf-123">特に組織がオンプレミスと Azure Active Directory で異なる UPN を使用している場合に、これを必要としない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-123">There are cases where you may not want this, especially if your organization uses different UPNs on-premises and in Azure Active Directory.</span></span> <span data-ttu-id="0d2cf-124">その場合には、次の Windows レジストリ キーを使用して、UPN の事前設定をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-124">If that's the case, you can use the following Windows registry key to turn off pre-population of the UPN:</span></span>

  <span data-ttu-id="0d2cf-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="0d2cf-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="0d2cf-126">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="0d2cf-126">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="0d2cf-127">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="0d2cf-127">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d2cf-128">「.local」 または 「.corp」 で終わるユーザー名については、ユーザー名の事前入力のスキップは既定でオンになっているため、レジストリ キーを設定してオフにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-128">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>


### <a name="mac-users"></a><span data-ttu-id="0d2cf-129">Mac ユーザー</span><span class="sxs-lookup"><span data-stu-id="0d2cf-129">Mac users</span></span>

<span data-ttu-id="0d2cf-130">MacOS 上では、Teams はユーザーにユーザー名と資格情報の入力を促し、組織の設定によっては多要素認証を促す場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-130">On MacOS, Teams will prompt users to enter their username and credentials and may prompt for multi-factor authentication depending on your organization's settings.</span></span> <span data-ttu-id="0d2cf-131">ユーザーが資格情報を入力すると、入力を再度求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-131">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="0d2cf-132">これ以降、ユーザーが同じコンピューターで作業している場合は常に、Teams が自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-132">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="0d2cf-133">先進認証を行った後のアカウントの切り替え</span><span class="sxs-lookup"><span data-stu-id="0d2cf-133">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="0d2cf-134">ドメインに参加しているコンピューターでユーザーが作業している場合 (テナントで Kerberos が有効になっている場合など)、先進認証を行った後は、ユーザーはアカウントを切り替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-134">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="0d2cf-135">ユーザーが作業を行っているのはドメインに参加しているコンピューターではない場合、ユーザーはアカウントを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-135">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="0d2cf-136">先進認証を行った後に Teams からサインアウトする</span><span class="sxs-lookup"><span data-stu-id="0d2cf-136">Signing out of Teams after completing modern authentication</span></span>

<span data-ttu-id="0d2cf-137">Teams からサインアウトするには、アプリの上部にある自分のプロファイル画像をクリックし、[**サインアウト**] を選択します。タスク バーにあるアプリのアイコンを右クリックして [**ログアウト**] を選択することもできます。一旦 Teams からサインアウトすると、アプリを起動するには資格情報をもう一度入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-137">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="0d2cf-138">URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="0d2cf-138">URLs and IP address ranges</span></span>

<span data-ttu-id="0d2cf-139">Teams を使用するには、インターネットへの接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-139">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="0d2cf-140">Office 365 の各プラン、政府機関向けまたはその他のクラウドを使用するユーザーが到達可能である必要があるエンドポイントについては、「[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-140">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d2cf-141">Teams では現在、すべてのユーザーについて、Google の ssl.gstatic.com サービス (<https://ssl.gstatic.com)> への接続 (TCP ポート 443) が要求されています。Gstatic を使用していない場合であってもこれは要求されます。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-141">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (<https://ssl.gstatic.com)> for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="0d2cf-142">Teams では間もなく (2020 年前半) この要件が削除される予定になっており、そのタイミングに合わせてこの記事も更新されます。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-142">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="0d2cf-143">先進認証のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0d2cf-143">Troubleshooting modern authentication</span></span>

<span data-ttu-id="0d2cf-144">先進認証は Office を使用しているすべての組織で利用可能であるため、もしユーザーがこのプロセスを完了できない場合には、組織のドメインまたは組織の職場または学校アカウントに何らかの問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-144">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Microsoft work or school account.</span></span>

<span data-ttu-id="0d2cf-145">詳細については、「[Microsoft Teams へのサインインで問題が発生する理由](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d2cf-145">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>
