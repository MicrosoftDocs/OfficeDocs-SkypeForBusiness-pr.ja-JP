---
title: マイクロソフトのチームへのサインイン
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 現代の認証を使用して、マイクロソフトのチームに署名するためのガイダンスです。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e44b05bd0daed8867247512d38f22b764351127d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882031"
---
<a name="sign-in-to-microsoft-teams"></a><span data-ttu-id="809f8-103">マイクロソフトのチームへのサインイン</span><span class="sxs-lookup"><span data-stu-id="809f8-103">Sign in to Microsoft Teams</span></span>
==========================

<span data-ttu-id="809f8-104">マイクロソフトのチームでは、現代の認証を使用して、シンプルかつセキュリティで保護されたサインイン処理をしてください。</span><span class="sxs-lookup"><span data-stu-id="809f8-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="809f8-105">現在の認証のしくみ</span><span class="sxs-lookup"><span data-stu-id="809f8-105">How modern authentication works</span></span>

<span data-ttu-id="809f8-106">現代の認証は、ユーザー既に入力されている資格情報 (と同様に自分の仕事の電子メールとパスワードを使用して) 別の場所で、し、アプリケーションを起動するには、もう一度入力して必要なされるべきではないことを知っているチームをできるようにするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="809f8-106">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="809f8-107">経験によって異なりますいくつかの要因のようなユーザーは、windows、または、mac 上に作業している場合</span><span class="sxs-lookup"><span data-stu-id="809f8-107">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="809f8-108">一元的認証方式、または複数要素の認証、組織が有効になっているかどうかによっても異なります (通常多要素認証では、PIN を入力する、一意のコードを提供する、携帯電話経由で資格情報を確認する必要がありますか拇印を表示) します。</span><span class="sxs-lookup"><span data-stu-id="809f8-108">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="809f8-109">ここでは、最新の認証シナリオの概要を示してします。</span><span class="sxs-lookup"><span data-stu-id="809f8-109">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="809f8-110">Windows ユーザーの場合:</span><span class="sxs-lookup"><span data-stu-id="809f8-110">Windows users</span></span> 

- <span data-ttu-id="809f8-111">ユーザーが既に署名されている場合、Office 365 のエンタープライズのアカウントでは、他の Office アプリケーションをアプリケーションに直接、撮影しているチームを起動するとき。</span><span class="sxs-lookup"><span data-stu-id="809f8-111">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="809f8-112">自分の資格情報を入力するために必要はありません。</span><span class="sxs-lookup"><span data-stu-id="809f8-112">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="809f8-113">によってどのようなことになりましたかの一元的か、多要素認証 SFA (MFA)、表示された場合、ユーザー、署名のない Office 365 のエンタープライズ アカウントをそれ以外の場所にチームを起動するとき、伴うプロセスです。</span><span class="sxs-lookup"><span data-stu-id="809f8-113">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="809f8-114">ユーザーは署名されている場合ドメインに参加しているコンピューターでは、チーム、MFA を必要とする組織を選択するかどうかによって、複数の認証手順のいずれかを移動することが求められる場合が、またはかどうかは、コンピューターが必要ですにサインインするのには MFA を起動したとき。</span><span class="sxs-lookup"><span data-stu-id="809f8-114">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="809f8-115">自分のコンピューターでは、既にサインインして MFA を必要とすると開くチーム、アプリケーションを自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="809f8-115">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="809f8-116">Mac ユーザー</span><span class="sxs-lookup"><span data-stu-id="809f8-116">Mac users</span></span> 

<span data-ttu-id="809f8-117">ユーザーは、チームを開始するときに自分のコンピューターから Office 365 のエンタープライズ アカウントまたはその他の Office アプリケーションのいずれかの資格情報を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="809f8-117">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="809f8-118">代わりに、(組織の設定) によって SFA や MFA を要求するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="809f8-118">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="809f8-119">ユーザーが資格情報を入力するとは、再度説明する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="809f8-119">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="809f8-120">その時点から、チームが自動的に開始される同じコンピューターで作業するときに。</span><span class="sxs-lookup"><span data-stu-id="809f8-120">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="809f8-121">現代の認証が完了した後、アカウントを切り替える</span><span class="sxs-lookup"><span data-stu-id="809f8-121">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="809f8-122">ユーザーがドメインに参加しているコンピューター (たとえば、そのテナントが Kerberos を有効にしている場合) で作業している場合、完了した最新の認証ユーザー アカウントの切り替え、ことはできません。</span><span class="sxs-lookup"><span data-stu-id="809f8-122">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="809f8-123">ユーザーがドメインに参加しているコンピューターで動作しない場合は、アカウントに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="809f8-123">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="809f8-124">現代の認証が完了した後、マイクロソフトのチームが署名</span><span class="sxs-lookup"><span data-stu-id="809f8-124">Signing out of Microsoft Teams after completing modern authentication</span></span>

<span data-ttu-id="809f8-125">チームからサインインすると、ユーザーが、アプリの上部にある自分のプロファイル画像をクリックし、**サインアウト**を選択します。アプリケーションのタスク バーにアイコンを右クリックしても、**ログアウト**を選択します。チームのサインアウトをしているアプリケーションを起動するには、再度資格情報を入力するのには、必要があります。</span><span class="sxs-lookup"><span data-stu-id="809f8-125">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="809f8-126">現代の認証のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="809f8-126">Troubleshooting modern authentication</span></span>

<span data-ttu-id="809f8-127">現代の認証は、チームを使用して、ユーザーがプロセスを完了することがない場合されること、ドメインまたは組織の Office 365 のエンタープライズ ・ アカウントに問題があるすべての組織で使用できます。</span><span class="sxs-lookup"><span data-stu-id="809f8-127">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="809f8-128">詳細についてを参照してください[マイクロソフトのチームへのサインインに問題が生じる理由ですか?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)です。</span><span class="sxs-lookup"><span data-stu-id="809f8-128">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

