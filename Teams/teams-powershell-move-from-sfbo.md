---
title: Skype for Business Online Connector から PowerShell モジュールへのTeams移行
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Skype for Business Online Connector から Teams PowerShell モジュールに移動して、Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b08505ca97672d5285c8ff46b0e5d3cf58e9f84
ms.sourcegitcommit: 56bebf42f545af57fdf387faa90e555abc8acd40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2021
ms.locfileid: "52513870"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="3d341-103">Skype for Business Online Connector から PowerShell モジュールへのTeams移行</span><span class="sxs-lookup"><span data-stu-id="3d341-103">Migrating from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="3d341-104">TeamsPowerShell モジュールには、PowerShell コマンド ラインから直接管理Teamsコマンドレットの完全なセットが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3d341-104">Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="3d341-105">管理者は、ユーザー管理Skype For Business Online Connector を使用Teams必要とします。</span><span class="sxs-lookup"><span data-stu-id="3d341-105">Administrators do not require Skype For Business Online Connector for their Teams administration.</span></span>

> [!NOTE]
> <span data-ttu-id="3d341-106">Teamsセンターの投稿 (MC244740、2021 年 3 月 16 日付け) を通じて管理者に通知されました。この変更に関する MC250940 (2021 年 4 月 16 日付け)。</span><span class="sxs-lookup"><span data-stu-id="3d341-106">Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.</span></span>
>
> <span data-ttu-id="3d341-107">TeamsPowerShell モジュールは最新の認証を使用しますが、基本認証Windows基になるリモート管理 (WinRM) クライアントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d341-107">Teams PowerShell Module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span> <span data-ttu-id="3d341-108">WinRM [for Basic 認証を有効Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)方法については、ダウンロードとインストールに関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d341-108">See [Download and install Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

> [!WARNING]
> <span data-ttu-id="3d341-109">Skype for Businessオンライン コネクタ接続は、2021 年 5 月 17 日から拒否されます。</span><span class="sxs-lookup"><span data-stu-id="3d341-109">Skype for Business Online Connector connections will be rejected starting May 17, 2021.</span></span> <span data-ttu-id="3d341-110">PowerShell モジュールへの移行については、Microsoft サポートTeams問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="3d341-110">Please contact Microsoft Support for help and support for migrating to Teams PowerShell Module.</span></span>

## <a name="how-to-migrate"></a><span data-ttu-id="3d341-111">移行方法</span><span class="sxs-lookup"><span data-stu-id="3d341-111">How to Migrate</span></span>

<span data-ttu-id="3d341-112">Skype for Business Online Connector を使用して PowerShell モジュールTeamsに移行するのは簡単で簡単です。</span><span class="sxs-lookup"><span data-stu-id="3d341-112">Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple.</span></span> <span data-ttu-id="3d341-113">次の手順では、これを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d341-113">The below steps explains how to do this.</span></span>

1. <span data-ttu-id="3d341-114">最新の PowerShell モジュールTeamsインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d341-114">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="3d341-115">手順については[、「PowerShell のインストール」Microsoft Teams参照してください](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="3d341-115">For steps, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

2. <span data-ttu-id="3d341-116">For Business Online コネクタSkypeをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d341-116">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="3d341-117">これを行うには、コントロール パネルで [プログラムと機能]**に移動** し、[オンライン] **Skype for Business、[** モジュール] の順Windows PowerShell選択し、[アンインストール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3d341-117">To do this, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span>

3. <span data-ttu-id="3d341-118">PowerShell スクリプトで、 で参照されているモジュール名を ```Import-Module```</span><span class="sxs-lookup"><span data-stu-id="3d341-118">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from</span></span>

    <span data-ttu-id="3d341-119">`SkypeOnlineConnector` または `LyncOnlineConnector` `MicrosoftTeams` に設定します。</span><span class="sxs-lookup"><span data-stu-id="3d341-119">`SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.</span></span>

    <span data-ttu-id="3d341-120">たとえば、 に `Import-Module -Name SkypeOnlineConnector` 変更します `Import-Module -Name MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="3d341-120">For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.</span></span>

4. <span data-ttu-id="3d341-121">PowerShell モジュール 2.0 Teamsを使用する場合は、 を参照するスクリプトを更新 `New-CsOnlineSession` します `Connect-MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="3d341-121">When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`.</span></span> <span data-ttu-id="3d341-122">`Import-PsSession`を使用するときに暗黙的に行われるSkype for Businessオンライン リモート PowerShell セッションを確立する必要はなくなりました `Connect-MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="3d341-122">`Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session as that is done implicit when using `Connect-MicrosoftTeams`.</span></span>

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a><span data-ttu-id="3d341-123">オンライン サポート</span><span class="sxs-lookup"><span data-stu-id="3d341-123">Online Support</span></span>

<span data-ttu-id="3d341-124">サービス要求をオンラインで開始することで時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="3d341-124">Save time by starting your service request online.</span></span> <span data-ttu-id="3d341-125">ソリューションの検索やテクニカル サポートへの接続をお手伝いします。</span><span class="sxs-lookup"><span data-stu-id="3d341-125">We'll help you find a solution or connect you to technical support.</span></span>

1.  <span data-ttu-id="3d341-126">[https://admin.microsoft.com](https://admin.microsoft.com) で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3d341-126">Go to the admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span> <span data-ttu-id="3d341-127">このページにアクセスしたり、この操作を実行したりするためのアクセス許可が付与されていないというメッセージが表示された場合は、管理者ではない場合があります。Whoは、私のビジネスで管理者アクセス許可を持っていますか?</span><span class="sxs-lookup"><span data-stu-id="3d341-127">If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. Who has admin permissions in my business?</span></span>

2.  <span data-ttu-id="3d341-128">[ヘルプが **必要ですか?] を選択します**。ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d341-128">Select the **Need help**? button.</span></span>

3.  <span data-ttu-id="3d341-129">「ヘルプ **が必要ですか?」を参照してください**。ウィンドウで、ヘルプが必要な情報を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3d341-129">In the **Need help**? pane, tell us what you need help with, and then press Enter.</span></span>

4.  <span data-ttu-id="3d341-130">結果が問題ない場合は、[サポートに問い合わせ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3d341-130">If the results don't help, select **Contact support**.</span></span>

5.  <span data-ttu-id="3d341-131">問題の説明を入力し、連絡先番号とメール アドレスを確認し、希望する連絡方法を選び、[連絡してください] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3d341-131">Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.</span></span> <span data-ttu-id="3d341-132">予想される待機時間は、「ヘルプが必要ですか?」に示されています。ウィンドウに移動します。</span><span class="sxs-lookup"><span data-stu-id="3d341-132">The expected wait time is indicated in the Need help? pane.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d341-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d341-133">Related topics</span></span>

[<span data-ttu-id="3d341-134">PowerShell Microsoft Teamsインストールする</span><span class="sxs-lookup"><span data-stu-id="3d341-134">Install Microsoft Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="3d341-135">PowerShell Teamsを使用Teams管理する</span><span class="sxs-lookup"><span data-stu-id="3d341-135">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="3d341-136">TeamsPowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="3d341-136">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="3d341-137">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="3d341-137">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="3d341-138">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="3d341-138">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
