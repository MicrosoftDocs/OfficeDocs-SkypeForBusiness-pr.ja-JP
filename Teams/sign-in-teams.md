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
ms.openlocfilehash: 2d6e4e8989bf26e4a907deec550d18f344728129
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868304"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="b92b1-104">先進認証を使用して Microsoft Teams にサインインする</span><span class="sxs-lookup"><span data-stu-id="b92b1-104">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="b92b1-105">Microsoft は、組織が ハイブリッド ドメイン参加構成か Azure AD 参加構成のいずれかで Windows 10 の最新バージョンを使用することを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="b92b1-105">Microsoft recommends that organizations use recent versions of Windows 10 with either Hybrid Domain Join or Azure AD Join configuration.</span></span> <span data-ttu-id="b92b1-106">これにより、Windows の Web アカウント マネージャーでユーザーのアカウントが準備され、Teams や他の Microsoft アプリケーションへのシングル サインオンが可能になります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-106">This ensures that users’ accounts are primed in Windows’ Web Account Manager, which in turns enables single sign-on to Teams and other Microsoft applications.</span></span> <span data-ttu-id="b92b1-107">これにより、ユーザー エクスペリエンス (サイレント サインイン) と、セキュリティに対する姿勢を改善します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-107">This provides a better user experience (silent sign-in) and a better security posture.</span></span>

<span data-ttu-id="b92b1-108">Microsoft Teams は先進認証を使用して、サインイン操作をシンプルかつ安全なものとしています。</span><span class="sxs-lookup"><span data-stu-id="b92b1-108">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="b92b1-109">ユーザーが Teams にサインインする方法については、「[Teams にサインインする](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92b1-109">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="b92b1-110">先進認証のしくみ</span><span class="sxs-lookup"><span data-stu-id="b92b1-110">How modern authentication works</span></span>

<span data-ttu-id="b92b1-111">先進認証とは、ユーザーが資格情報 (職場のメールやパスワードなど) を既に別の場所に入力したことを Teams に知らせ、ユーザーが資格情報を再度入力することを要求されることなくアプリを起動できるようにするためのプロセスです。</span><span class="sxs-lookup"><span data-stu-id="b92b1-111">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="b92b1-112">ユーザーが Windows を使用しているのか Mac を使用しているのかなど、いつくかの要因によってエクスペリエンスは異なります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-112">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="b92b1-113">また、組織で単一要素認と多要素認証のいずれが有効にされているかによってもエクスペリエンスは異なります (多要素認証では通常、電話での資格情報の確認、一意のコードの提供、PIN の入力、または拇印の提示を行う必要があります)。</span><span class="sxs-lookup"><span data-stu-id="b92b1-113">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="b92b1-114">以下は、それぞれの先進認証シナリオの簡単な説明です。</span><span class="sxs-lookup"><span data-stu-id="b92b1-114">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="b92b1-115">Windows ユーザー</span><span class="sxs-lookup"><span data-stu-id="b92b1-115">Windows users</span></span>

- <span data-ttu-id="b92b1-116">ユーザーが自分の職場または学校アカウントを使用して既に Windows や別の Office アプリにサインインしている場合、ユーザーが Teams を起動すると、直ちにアプリに移動します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-116">If users have already signed in to Windows or to other Office apps with their work or school account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="b92b1-117">ユーザーが資格情報を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b92b1-117">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="b92b1-118">Microsoft では、最高のシングル サインオン エクスペリエンスを得るために、Windows 10 のバージョン 1903 以降の使用を推奨しています。</span><span class="sxs-lookup"><span data-stu-id="b92b1-118">Microsoft recommends using Windows 10 version 1903 or later for the best Single Sign-On experience.</span></span>

- <span data-ttu-id="b92b1-119">ユーザーが自分の職場または学校アカウントにいずれのアプリからもサインインしていない場合、ユーザーが Teams を起動すると、組織で単一要素認と多要素認証 (SFA または MFA) のどちらを求める設定になっているかにより、ユーザーはいずれかの認証を提供するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-119">If users are not signed in to their Microsoft work or school account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="b92b1-120">ドメインに参加しているコンピューターにユーザーがサインインしている場合、ユーザーが Teams を起動すると、MFA を要求するように組織で設定されているかどうか、または、ユーザーのコンピューターへのサインインで既に MFA が要求されているのかどうかにより、もう 1 つ別の認証手順を実行するよう求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-120">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="b92b1-121">コンピューターへのサインインで既に MFA が要求されている場合、ユーザーが Teams を開くとアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-121">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="b92b1-122">ドメインに参加している PC では、SSO が利用できない場合に、Teams がログイン画面にユーザー プリンシパル名 (UPN) を事前に入力しておく場合があります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-122">On Domain joined PCs, when SSO isn't possible Teams may pre-fill its login screen with the user principal name (UPN).</span></span> <span data-ttu-id="b92b1-123">特に組織がオンプレミスと Azure Active Directory で異なる UPN を使用している場合に、これを必要としない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-123">There are cases where you may not want this, especially if your organization uses different UPNs on-premises and in Azure Active Directory.</span></span> <span data-ttu-id="b92b1-124">その場合には、次の Windows レジストリ キーを使用して、UPN の事前設定をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-124">If that's the case, you can use the following Windows registry key to turn off pre-population of the UPN:</span></span>

  <span data-ttu-id="b92b1-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="b92b1-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="b92b1-126">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="b92b1-126">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="b92b1-127">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="b92b1-127">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="b92b1-128">「.local」 または 「.corp」 で終わるユーザー名については、ユーザー名の事前入力のスキップは既定でオンになっているため、レジストリ キーを設定してオフにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b92b1-128">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>


### <a name="mac-users"></a><span data-ttu-id="b92b1-129">Mac ユーザー</span><span class="sxs-lookup"><span data-stu-id="b92b1-129">Mac users</span></span>

<span data-ttu-id="b92b1-130">MacOS 上では、Teams はユーザーにユーザー名と資格情報の入力を促し、組織の設定によっては多要素認証を促す場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-130">On MacOS, Teams will prompt users to enter their username and credentials and may prompt for multi-factor authentication depending on your organization's settings.</span></span> <span data-ttu-id="b92b1-131">ユーザーが資格情報を入力すると、入力を再度求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="b92b1-131">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="b92b1-132">これ以降、ユーザーが同じコンピューターで作業している場合は常に、Teams が自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-132">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="teams-for-ios-and-android-users"></a><span data-ttu-id="b92b1-133">iOS と Android の Teams のユーザー</span><span class="sxs-lookup"><span data-stu-id="b92b1-133">Teams for iOS and Android users</span></span>

<span data-ttu-id="b92b1-134">サインインすると、モバイルユーザーには、デバイス上で現在サインインしているまたは以前にサインインしたすべての Microsoft 365 アカウントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-134">Upon sign in, mobile users will see a list of all the Microsoft 365 accounts that are either currently signed in or were previously signed in on their device.</span></span> <span data-ttu-id="b92b1-135">ユーザーは、任意のアカウントをタップしてサインインできます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-135">Users can tap on any of the accounts to sign in.</span></span> <span data-ttu-id="b92b1-136">モバイル サインインには2つのシナリオがあります:</span><span class="sxs-lookup"><span data-stu-id="b92b1-136">There are two scenarios for mobile sign in:</span></span>
    
1. <span data-ttu-id="b92b1-137">選択されたアカウントが他の Office 365 または Microsoft 365 アプリに現在サインインしている場合、そのユーザーは直接 Teams に移動します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-137">If the selected account is currently signed in to other Office 365 or Microsoft 365 apps, then the user will be taken straight to Teams.</span></span> <span data-ttu-id="b92b1-138">ユーザーは資格情報を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b92b1-138">There is no need for the user to enter their credentials.</span></span>
    
2. <span data-ttu-id="b92b1-139">ユーザーが他の場所で Microsoft 365 アカウントにサインインしていない場合は、組織がモバイル サインイン ポリシー用に構成した内容に応じて、単一要素認証または多要素認証 (SFA または MFA) を提供するように求められます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-139">If user isn't signed in to their Microsoft 365 account anywhere else, they will be asked to provide single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has configured for mobile sign in policies.</span></span>

### <a name="adding-multiple-accounts-to-teams"></a><span data-ttu-id="b92b1-140">Teams への複数アカウントの追加</span><span class="sxs-lookup"><span data-stu-id="b92b1-140">Adding multiple accounts to Teams</span></span>

<span data-ttu-id="b92b1-141">IOS と Android の Teams では、1 つのデバイスから Teams に複数のアカウントを追加することをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b92b1-141">Teams for iOS and Android supports adding multiple accounts from a single device to Teams.</span></span> <span data-ttu-id="b92b1-142">次の画像は、ユーザーが複数のアカウントを Teams に追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b92b1-142">The following images show how users can add multiple accounts in Teams.</span></span>
    
:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Teams に複数アカウントを追加":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a><span data-ttu-id="b92b1-144">エンタープライズ モビリティ管理を使用して、Teams にサインインできるアカウントを制御する</span><span class="sxs-lookup"><span data-stu-id="b92b1-144">Use enterprise mobility management to control which accounts can sign in to Teams</span></span>

<span data-ttu-id="b92b1-145">iOS と Android の Teams は、IT 管理者に、アカウント構成を Microsoft 365 アカウントに配布する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-145">Teams for iOS and Android offers IT administrators the ability to push account configurations to Microsoft 365 accounts.</span></span> <span data-ttu-id="b92b1-146">この機能は、iOS の [管理対象アプリ構成](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html)  チャネルまたは Android の  [Android Enterprise](https://developer.android.com/work/managed-configurations)  チャネルを使用するすべてのモバイル デバイス管理 （MDM） プロバイダーで機能します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-146">This capability works with any Mobile Device Management (MDM) provider who uses the [Managed App Configuration](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) channel for iOS or the [Android Enterprise](https://developer.android.com/work/managed-configurations) channel for Android.</span></span>

<span data-ttu-id="b92b1-147">Microsoft Intune に登録されているユーザーは、Azure Portal の Intune を使用してアカウント構成設定を展開できます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-147">For users enrolled in Microsoft Intune, you can deploy the account configuration settings using Intune in the Azure Portal.</span></span>

<span data-ttu-id="b92b1-148">MDM プロバイダーでアカウント セットアップ構成がセットアップされ、ユーザーがデバイスを登録した後、iOS と Android の Teams は、許可されたアカウントのみ Teams ログイン ページに表示します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-148">Once account setup configuration has been setup in the MDM provider, and after the user enrolls their device, on the login pgae, Teams for iOS and Android will only show the allowed account(s) on the Teams login page.</span></span> <span data-ttu-id="b92b1-149">ユーザーはこのページで許可されているアカウントをタップして、サインインできます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-149">The user can tap on any of the allowed accounts on this page to sign in.</span></span>

<span data-ttu-id="b92b1-150">管理対象デバイスの Azure Intune ポータルで次の構成パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-150">Set the following configuration parameters in the Azure Intune portal for managed devices.</span></span>


|<span data-ttu-id="b92b1-151">プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="b92b1-151">Platform</span></span> |<span data-ttu-id="b92b1-152">キー</span><span class="sxs-lookup"><span data-stu-id="b92b1-152">Key</span></span>  |<span data-ttu-id="b92b1-153">値</span><span class="sxs-lookup"><span data-stu-id="b92b1-153">Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b92b1-154">iOS</span><span class="sxs-lookup"><span data-stu-id="b92b1-154">iOS</span></span>     |  <span data-ttu-id="b92b1-155">**IntuneMAMAllowedAccountsOnly**</span><span class="sxs-lookup"><span data-stu-id="b92b1-155">**IntuneMAMAllowedAccountsOnly**</span></span>       | <span data-ttu-id="b92b1-156">**有効**: 使用できるアカウントは、IntuneMAMUPN キーで定義された管理対象ユーザー アカウントのみです。</span><span class="sxs-lookup"><span data-stu-id="b92b1-156">**Enabled**: The only account allowed is the managed user account defined by the IntuneMAMUPN key.</span></span><br> <span data-ttu-id="b92b1-157">**無効** (または、大文字と小文字を区別しない **有効** な任意の値): すべてのアカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-157">**Disabled** (or any value that is not a case insensitive match to **Enabled**): Any account is allowed.</span></span>        |
|<span data-ttu-id="b92b1-158">iOS</span><span class="sxs-lookup"><span data-stu-id="b92b1-158">iOS</span></span>     |   <span data-ttu-id="b92b1-159">**IntuneMAMUPN**</span><span class="sxs-lookup"><span data-stu-id="b92b1-159">**IntuneMAMUPN**</span></span>      |   <span data-ttu-id="b92b1-160">Teams. へのサインインが許可されているアカウントの UPN です。</span><span class="sxs-lookup"><span data-stu-id="b92b1-160">UPN of the account allowed to sign in to Teams.</span></span><br> <span data-ttu-id="b92b1-161">Intune に登録されているデバイスの場合、{{userprincipalname}} トークンを使用して、登録済みのユーザーアカウントを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-161">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>       |
|<span data-ttu-id="b92b1-162">Android</span><span class="sxs-lookup"><span data-stu-id="b92b1-162">Android</span></span>     |<span data-ttu-id="b92b1-163">**com.microsoft.intune.mam.AllowedAccountUPNs**</span><span class="sxs-lookup"><span data-stu-id="b92b1-163">**com.microsoft.intune.mam.AllowedAccountUPNs**</span></span>         |    <span data-ttu-id="b92b1-164">このキーで定義された管理対象ユーザーアカウントのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-164">Only account(s) allowed are the managed user account(s) defined by this key.</span></span><br> <span data-ttu-id="b92b1-165">1つ以上のセミコロン [;] で区切られた UPN です。</span><span class="sxs-lookup"><span data-stu-id="b92b1-165">One or more semi-colon [;]- delmited UPNs.</span></span><br> <span data-ttu-id="b92b1-166">Intune に登録されているデバイスの場合、{{userprincipalname}} トークンを使用して、登録済みのユーザーアカウントを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-166">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>

<span data-ttu-id="b92b1-167">アカウント セットアップ構成が設定されると、Teams はサインイン機能を制限し、登録されたデバイス上の許可されたアカウントのみにアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-167">Once the account setup configuration has been set, Teams will restrict the ability to sign in, so that only allowed accounts on enrolled devices will be granted access.</span></span>

<span data-ttu-id="b92b1-168">管理対象の iOS/iPadOS デバイスのアプリ構成ポリシーを作成するには、「 [管理対象の iOS/iPadOS デバイスのアプリ構成ポリシーの追加](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92b1-168">To create an app configuration policy for managed iOS/iPadOS devices, see [Add app configuration policies for managed iOS/iPadOS devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios).</span></span>

<span data-ttu-id="b92b1-169">管理対象の Android デバイスのアプリ構成ポリシーを作成するには、「 [管理対象の Android デバイスのアプリ構成ポリシーの追加](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92b1-169">To create an app configuration policy for managed Android devices, see [Add app configuration policies for managed Android devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android).</span></span>


## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="b92b1-170">先進認証を行った後のアカウントの切り替え</span><span class="sxs-lookup"><span data-stu-id="b92b1-170">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="b92b1-171">ドメインに参加しているコンピューターでユーザーが作業している場合 (テナントで Kerberos が有効になっている場合など)、先進認証を行った後は、ユーザーはアカウントを切り替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="b92b1-171">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="b92b1-172">ユーザーが作業を行っているのはドメインに参加しているコンピューターではない場合、ユーザーはアカウントを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-172">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="b92b1-173">先進認証を行った後に Teams からサインアウトする</span><span class="sxs-lookup"><span data-stu-id="b92b1-173">Signing out of Teams after completing modern authentication</span></span>

<span data-ttu-id="b92b1-174">Teams からサインアウトするには、アプリの上部にある自分のプロファイル画像をクリックし、[**サインアウト**] を選択します。タスク バーにあるアプリのアイコンを右クリックして [**ログアウト**] を選択することもできます。一旦 Teams からサインアウトすると、アプリを起動するには資格情報をもう一度入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-174">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

### <a name="signing-out-of-teams-for-ios-and-android"></a><span data-ttu-id="b92b1-175">iOS と Android の Teams をサインアウト</span><span class="sxs-lookup"><span data-stu-id="b92b1-175">Signing out of Teams for iOS and Android</span></span>

<span data-ttu-id="b92b1-176">モバイル ユーザーはメニューに移動して [**その他**] メニューを選択し、[**サインアウト**] を選択することで、Teams からサインアウトできます。サインアウトすると、ユーザーは次にアプリを起動するときに、資格情報を再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-176">Mobile users can sign out of Teams by going to the menu and choosing the **More** menu, and then choosing **Sign out**. Once signed out, users will need to re-enter their credentials the next time they launch the app.</span></span>

> [!NOTE]
> <span data-ttu-id="b92b1-177">Android の Teams はシングル サインオン (SSO) を使用して、サインインの操作を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="b92b1-177">Teams for Android uses single sign-on (SSO) to simplify the sign in experience.</span></span> <span data-ttu-id="b92b1-178">ユーザーは、Android プラットフォームで完全にログアウトするために、Teams に加えて **すべての** Microsoft アプリからログアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-178">Users should make sure to log out of **all** Microsoft apps, in addition to Teams, in order to completely log out on the Android platform.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="b92b1-179">URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="b92b1-179">URLs and IP address ranges</span></span>

<span data-ttu-id="b92b1-180">Teams を使用するには、インターネットへの接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="b92b1-180">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="b92b1-181">Office 365 の各プラン、政府機関向けまたはその他のクラウドを使用するユーザーが到達可能である必要があるエンドポイントについては、「[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92b1-181">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b92b1-182">Teams では現在、すべてのユーザーについて、Google の ssl.gstatic.com サービス (<https://ssl.gstatic.com)> への接続 (TCP ポート 443) が要求されています。Gstatic を使用していない場合であってもこれは要求されます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-182">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (<https://ssl.gstatic.com)> for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="b92b1-183">Teams では間もなく (2020 年前半) この要件が削除される予定になっており、そのタイミングに合わせてこの記事も更新されます。</span><span class="sxs-lookup"><span data-stu-id="b92b1-183">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="b92b1-184">先進認証のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b92b1-184">Troubleshooting modern authentication</span></span>

<span data-ttu-id="b92b1-185">先進認証は Office を使用しているすべての組織で利用可能であるため、もしユーザーがこのプロセスを完了できない場合には、組織のドメインまたは組織の職場または学校アカウントに何らかの問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b92b1-185">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Microsoft work or school account.</span></span>

<span data-ttu-id="b92b1-186">詳細については、「[Microsoft Teams へのサインインで問題が発生する理由](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92b1-186">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>
