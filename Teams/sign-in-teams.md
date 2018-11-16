---
title: マイクロソフト チームの最新の認証を使用してにサインインします。
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 現代の認証を使用して、マイクロソフトのチームにサインインする方法です。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01ca138aebae8d0db731118baf3e340aa3332120
ms.sourcegitcommit: bd32d44d27990e373ce6afa38897159473601113
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "26544373"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="2b982-103">マイクロソフト チームの最新の認証を使用してにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b982-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="2b982-104">マイクロソフトのチームでは、現代の認証を使用して、シンプルかつセキュリティで保護されたサインイン処理をしてください。</span><span class="sxs-lookup"><span data-stu-id="2b982-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="2b982-105">ユーザーがチームにサインインする方法を表示するには、[チームへのサインイン](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b982-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="2b982-106">現在の認証のしくみ</span><span class="sxs-lookup"><span data-stu-id="2b982-106">How modern authentication works</span></span>

<span data-ttu-id="2b982-107">現代の認証は、ユーザー既に入力されている資格情報 (と同様に自分の仕事の電子メールとパスワードを使用して) 別の場所で、し、アプリケーションを起動するには、もう一度入力して必要なされるべきではないことを知っているチームをできるようにするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="2b982-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="2b982-108">経験によって異なりますいくつかの要因のようなユーザーは、windows、または、mac 上に作業している場合</span><span class="sxs-lookup"><span data-stu-id="2b982-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="2b982-109">一元的認証方式、または複数要素の認証、組織が有効になっているかどうかによっても異なります (通常多要素認証では、PIN を入力する、一意のコードを提供する、携帯電話経由で資格情報を確認する必要がありますか拇印を表示) します。</span><span class="sxs-lookup"><span data-stu-id="2b982-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="2b982-110">ここでは、最新の認証シナリオの概要を示してします。</span><span class="sxs-lookup"><span data-stu-id="2b982-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="2b982-111">Windows ユーザーの場合:</span><span class="sxs-lookup"><span data-stu-id="2b982-111">Windows users</span></span> 

- <span data-ttu-id="2b982-112">ユーザーが既に署名されている場合、Office 365 のエンタープライズのアカウントでは、他の Office アプリケーションをアプリケーションに直接、撮影しているチームを起動するとき。</span><span class="sxs-lookup"><span data-stu-id="2b982-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="2b982-113">自分の資格情報を入力するために必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2b982-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="2b982-114">によってどのようなことになりましたかの一元的か、多要素認証 SFA (MFA)、表示された場合、ユーザー、署名のない Office 365 のエンタープライズ アカウントをそれ以外の場所にチームを起動するとき、伴うプロセスです。</span><span class="sxs-lookup"><span data-stu-id="2b982-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="2b982-115">ユーザーは署名されている場合ドメインに参加しているコンピューターでは、チーム、MFA を必要とする組織を選択するかどうかによって、複数の認証手順のいずれかを移動することが求められる場合が、またはかどうかは、コンピューターが必要ですにサインインするのには MFA を起動したとき。</span><span class="sxs-lookup"><span data-stu-id="2b982-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="2b982-116">自分のコンピューターでは、既にサインインして MFA を必要とすると開くチーム、アプリケーションを自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="2b982-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="2b982-117">Mac ユーザー</span><span class="sxs-lookup"><span data-stu-id="2b982-117">Mac users</span></span> 

<span data-ttu-id="2b982-118">ユーザーは、チームを開始するときに自分のコンピューターから Office 365 のエンタープライズ アカウントまたはその他の Office アプリケーションのいずれかの資格情報を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b982-118">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="2b982-119">代わりに、(組織の設定) によって SFA や MFA を要求するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b982-119">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="2b982-120">ユーザーが資格情報を入力するとは、再度説明する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2b982-120">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="2b982-121">その時点から、チームが自動的に開始される同じコンピューターで作業するときに。</span><span class="sxs-lookup"><span data-stu-id="2b982-121">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="2b982-122">現代の認証が完了した後、アカウントを切り替える</span><span class="sxs-lookup"><span data-stu-id="2b982-122">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="2b982-123">ユーザーがドメインに参加しているコンピューター (たとえば、そのテナントが Kerberos を有効にしている場合) で作業している場合、完了した最新の認証ユーザー アカウントの切り替え、ことはできません。</span><span class="sxs-lookup"><span data-stu-id="2b982-123">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="2b982-124">ユーザーがドメインに参加しているコンピューターで動作しない場合は、アカウントに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="2b982-124">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="2b982-125">現代の認証が完了した後、マイクロソフトのチームが署名</span><span class="sxs-lookup"><span data-stu-id="2b982-125">Signing out of Microsoft Teams after completing modern authentication</span></span>

<span data-ttu-id="2b982-126">チームからサインインすると、ユーザーが、アプリの上部にある自分のプロファイル画像をクリックし、**サインアウト**を選択します。アプリケーションのタスク バーにアイコンを右クリックしても、**ログアウト**を選択します。チームのサインアウトをしているアプリケーションを起動するには、再度資格情報を入力するのには、必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b982-126">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="2b982-127">現代の認証のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2b982-127">Troubleshooting modern authentication</span></span>

<span data-ttu-id="2b982-128">現代の認証は、チームを使用して、ユーザーがプロセスを完了することがない場合されること、ドメインまたは組織の Office 365 のエンタープライズ ・ アカウントに問題があるすべての組織で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b982-128">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="2b982-129">詳細についてを参照してください[マイクロソフトのチームへのサインインに問題が生じる理由ですか?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)です。</span><span class="sxs-lookup"><span data-stu-id="2b982-129">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

