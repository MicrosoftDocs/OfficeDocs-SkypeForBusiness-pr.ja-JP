---
title: Microsoft Teams での Cortana 音声アシスタンス
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Teams で Cortana 音声アシスタンスを使用する方法について
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886736"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="b56c7-103">Teams での Cortana の音声アシスタンス</span><span class="sxs-lookup"><span data-stu-id="b56c7-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="b56c7-104">Cortana の音声アシスタントは、iOS および Android 用の Microsoft Teams モバイル アプリでサポートされ、Microsoft Teams の表示は米国、英国、カナダ、インド、およびオーストラリアのユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="b56c7-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span>  <span data-ttu-id="b56c7-105">Windows 上の Microsoft Teams の会議室は、米国内のユーザーにのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="b56c7-106">Cortana の音声アシスタンスは現在、GCC、GCC-High、DoD、EDU テナントでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="b56c7-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="b56c7-107">追加の言語と地域への拡張は、将来のリリースの一環として行います。</span><span class="sxs-lookup"><span data-stu-id="b56c7-107">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="b56c7-108">Microsoft Teams Rooms の Cortana 音声アシスタンスは、プレビューでリリースされます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-108">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="b56c7-109">プレビュー 版リリースでは、Cortana は米国でのみサポートされています。Cortana は、Cortana マイクを接続しているデバイスで EN-US の言語を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b56c7-109">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="b56c7-110">Microsoft 365 Enterprise ユーザーは、Teams モバイル アプリ、Windows の Microsoft Teams 会議室、および Microsoft Teams ディスプレイ デバイスで Cortana の音声アシスタンスを使用して、音声自然言語を使用して、コミュニケーション、コラボレーション、会議関連のタスクを合理化できます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-110">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="b56c7-111">ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams Room で &#8220;Cortana&#8221; と言うか、Microsoft Teams のディスプレイを使用して Cortana と話します。</span><span class="sxs-lookup"><span data-stu-id="b56c7-111">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="b56c7-112">チームとハンズフリーで簡単につながって、移動中に、ユーザーは &#8220;通話メーガン&#8221; や &#8220;などのクエリを言って、次の会議&#8221; にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-112">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="b56c7-113">ユーザーは、次の会議に参加&#8220;、音声&#8221;を使用してファイルの共有、予定表の確認などについて話し合って、会議に参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-113">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="b56c7-114">これらの音声アシスタンスエクスペリエンスは、オンライン サービス規約[(OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映される Office 365 のプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠する[、Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)のエンタープライズ レベルのサービスを使用して配信されます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-114">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="b56c7-115">画像は、モバイル デバイスで Cortana を使用してチャットを送信する場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="b56c7-115">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Cortana チャット セッションを表示する一連のモバイル画面](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="b56c7-117">管理者の制御と制限事項</span><span class="sxs-lookup"><span data-stu-id="b56c7-117">Admin control and limitations</span></span>

<span data-ttu-id="b56c7-118">Teams の Cortana 音声アシスタンスは、オンライン サービス規約 (OST) に反映される Office 365 エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠したサービスを使用して配信されます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-118">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="b56c7-119">この機能は、テナントに対して既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="b56c7-119">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="b56c7-120">テナント管理者は、ポリシー (TeamsCortanaPolicy) を使用して、テナント内のユーザーが Teams で Cortana 音声アシスタンスを使用できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-120">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="b56c7-121">このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-121">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="b56c7-122">管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana が無効になっているか、プッシュ ボタン呼び出しでのみ有効になっているか、スリープ解除の単語呼び出しを有効にするか (Microsoft Teams の表示など、サポートしているデバイスに適用されます) を判断できます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-122">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="b56c7-123">管理者は、次の PowerShell コマンドレットを使用してこのポリシーを管理できます (ポリシーは現在、Microsoft Teams 管理センターでは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="b56c7-123">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="b56c7-124">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b56c7-124">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="b56c7-125">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b56c7-125">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="b56c7-126">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b56c7-126">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="b56c7-127">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b56c7-127">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="b56c7-128">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b56c7-128">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="b56c7-129">たとえば、次のコマンドを実行すると、Microsoft Teams の Cortana 音声アシスタンスが無効&#8220;EmployeeCortanaPolicy&#8221; という名前の新しいポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-129">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="b56c7-130">この例では、名前 &#8220;EmployeeCortanaPolicy&#8221; を使用して既存のポリシーを更新し、プッシュ ボタン呼び出しのみを使用して Microsoft Teams で Cortana 音声アシスタンスを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="b56c7-130">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="b56c7-131">ユーザーは、Teams で Cortana のマイク ボタンを選択して Cortana を起動できます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-131">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="b56c7-132">単語を覚ます (&#8220;Cortana&#8221; または cortana &#8220;&#8221;) 呼び出しは無効になります。</span><span class="sxs-lookup"><span data-stu-id="b56c7-132">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="b56c7-133">この例では、ポリシーを更新し、プッシュ ボタンとスリープ解除の両方の単語呼び出しで Cortana 音声アシスタンスを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="b56c7-133">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="b56c7-134">米国英語の Microsoft 365 Enterprise ユーザー向け最初のリリースでは、次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-134">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="b56c7-135">Teams モバイル アプリではスリープ解除の単語のアクティブ化はサポートされませんが、今後サポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="b56c7-135">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="b56c7-136">Windows および Microsoft Teams の表示デバイス上の Microsoft Teams の会議室は、スリープ解除の単語のアクティブ化をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b56c7-136">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="b56c7-137">ユーザー コントロール</span><span class="sxs-lookup"><span data-stu-id="b56c7-137">User control</span></span>

<span data-ttu-id="b56c7-138">個々のユーザーは、さまざまなデバイスで Cortana 音声アシスタンスを試しに行えます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-138">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="b56c7-139">Teams モバイル アプリでマイク ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b56c7-139">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="b56c7-140">Microsoft Teams の会議室でマイク ボタンを選択するか、"Cortana" と言います。</span><span class="sxs-lookup"><span data-stu-id="b56c7-140">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="b56c7-141">Microsoft Teams のディスプレイ デバイスで 「Cortana」と言います。</span><span class="sxs-lookup"><span data-stu-id="b56c7-141">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="b56c7-142">デバイスの設定を使用して、Teams の Cortana をデバイスで有効にするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-142">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="b56c7-143">Teams モバイル アプリまたは Microsoft Teams の表示</span><span class="sxs-lookup"><span data-stu-id="b56c7-143">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="b56c7-144">Teams モバイル アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-144">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="b56c7-145">[設定  >  **] Cortana を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b56c7-145">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="b56c7-146">[オン] または [ **オフ] を** 切り **替えます**。</span><span class="sxs-lookup"><span data-stu-id="b56c7-146">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="b56c7-147">Microsoft Teams の表示</span><span class="sxs-lookup"><span data-stu-id="b56c7-147">Microsoft Teams display</span></span>

  1. <span data-ttu-id="b56c7-148">Microsoft Teams ディスプレイの環境 (ホーム) 画面に移動します。</span><span class="sxs-lookup"><span data-stu-id="b56c7-148">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="b56c7-149">ユーザー アバターを選択し、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b56c7-149">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="b56c7-150">Cortana が有効になっている場合は、"Cortana、設定に移動" と言います。</span><span class="sxs-lookup"><span data-stu-id="b56c7-150">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="b56c7-151">[オン] または [ **オフ] を** 切り **替えます**。</span><span class="sxs-lookup"><span data-stu-id="b56c7-151">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="b56c7-152">Windows 上の Microsoft Teams の会議室</span><span class="sxs-lookup"><span data-stu-id="b56c7-152">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="b56c7-153">デバイス レベルでの変更は、テナント レベルで Cortana が有効になっている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-153">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="b56c7-154">Cortana は既定でオフにリリースされます。</span><span class="sxs-lookup"><span data-stu-id="b56c7-154">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="b56c7-155">デバイス レベルで Cortana を有効にするには、次の XML 属性を SkypeSettings XML ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b56c7-155">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="b56c7-156">デバイス レベルで Cortana が有効になっている場合は、会議レベルで変更を行います。</span><span class="sxs-lookup"><span data-stu-id="b56c7-156">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="b56c7-157">会議中に Cortana の音声アシスタンスを有効にするには、[オン] または [オフ] を **切り** 替 **えます**。</span><span class="sxs-lookup"><span data-stu-id="b56c7-157">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="b56c7-158">会議が終了すると、Cortana はデバイス レベルの設定セットに戻ります。</span><span class="sxs-lookup"><span data-stu-id="b56c7-158">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
