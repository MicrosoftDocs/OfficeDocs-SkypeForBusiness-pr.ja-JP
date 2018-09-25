---
title: 仮想環境でマイクロソフトのチームを実行します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/28/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jaym
description: 仮想化環境でマイクロソフトのチームを実行する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72c420697b015d3af9cfe6fb9dd96757f1542e80
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016310"
---
<a name="run-microsoft-teams-in-a-virtual-environment"></a><span data-ttu-id="8d692-103">仮想環境でマイクロソフトのチームを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d692-103">Run Microsoft Teams in a virtual environment</span></span>
============================================

<span data-ttu-id="8d692-104">この資料では、要件とチームを使用して仮想化された環境での制限事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d692-104">This article describes requirements and limitations for using Teams in a virtualized environment.</span></span>

<span data-ttu-id="8d692-105">仮想デスクトップ インフラストラクチャ (VDI) 環境は、非常に高度なセキュリティとコンプライアンスが求められる組織で使用します。</span><span class="sxs-lookup"><span data-stu-id="8d692-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="8d692-106">ユーザーは、すべてのデスクトップ アプリケーションやリモート デスクトップ サービスまたはのようなリモート接続を使用してファイルを格納している仮想デスクトップで作業を行います。</span><span class="sxs-lookup"><span data-stu-id="8d692-106">Their users do their work on a virtual desktop containing all their desktop applications and files using Remote Desktop Services or a similar remote connection.</span></span> <span data-ttu-id="8d692-107">アクセスしたり、(ソフトウェア) を追加せずに、ユーザーのローカル デバイス上のオーディオまたはビデオ デバイスを使用して仮想デスクトップ上のチームが最適化されていないため、VDI 環境で作業している通常は通話などのマルチ メディアのシナリオに関連する課題ビデオ通話、画面共有、アプリケーション共有、共同編集などです。</span><span class="sxs-lookup"><span data-stu-id="8d692-107">Since Teams on the virtual desktop has not been optimized to access or use the audio or video devices on the user’s local device (without additional software), working in a VDI environment will usually have challenges related to multimedia scenarios such as calling, video calling, screen sharing, app sharing, co-authoring, and more.</span></span> 

> [!NOTE]
> <span data-ttu-id="8d692-108">組織が VDI でチームを完全に実行を選択できます (Web アプリケーションまたはデスクトップ クライアントを使用して) がお勧め次のポリシーは、オフにするため、ユーザーでは、仮想化環境に不適切な経験がありません。</span><span class="sxs-lookup"><span data-stu-id="8d692-108">Organizations can choose to run Teams fully in VDI (using either the Web App or Desktop Client) but it is recommended that the following policies be turned off, so users don’t have a poor experience in a virtualized environment.</span></span> <span data-ttu-id="8d692-109">これらポリシーの変更を反映するのには時間がかかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8d692-109">Note that it can take some time for these policy changes to propagate.</span></span> <span data-ttu-id="8d692-110">指定したアカウントの変更がすぐに表示されない場合、は、数時間後にもう一度してみてください。</span><span class="sxs-lookup"><span data-stu-id="8d692-110">If you don’t see changes for a given account immediately, try again after a few hours.</span></span> 

## <a name="calling"></a><span data-ttu-id="8d692-111">通話</span><span class="sxs-lookup"><span data-stu-id="8d692-111">Calling</span></span>

<span data-ttu-id="8d692-112">*CsTeamsCallingPolicy*コマンドレットを呼び出すと、プライベートでのオプションを呼び出すかどうかの管理者は、コントロールを有効にして、グループ チャットが有効か無効です。</span><span class="sxs-lookup"><span data-stu-id="8d692-112">The *CsTeamsCallingPolicy* cmdlets enable administrators to control whether calling and calling options in private and group chats are enabled or not.</span></span> 


|<span data-ttu-id="8d692-113">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="8d692-113">Policy name</span></span> |<span data-ttu-id="8d692-114">説明</span><span class="sxs-lookup"><span data-stu-id="8d692-114">Description</span></span>  |<span data-ttu-id="8d692-115">推奨値</span><span class="sxs-lookup"><span data-stu-id="8d692-115">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8d692-116">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="8d692-116">AllowPrivateCalling</span></span>   |<span data-ttu-id="8d692-117">か通話アプリはチームのクライアントの左側のレールに使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8d692-117">Controls whether the Calling app is available in the left rail of the Teams client or not.</span></span> <span data-ttu-id="8d692-118">プライベート チャットでの通話や映像通話のオプションを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8d692-118">Also controls whether users see Calling and Video Call options in private chat.</span></span> |<span data-ttu-id="8d692-119">**False**とプライベート チャットで通話や映像通話のオプションを削除するのには左側のレールからの通話アプリを削除するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-119">Set this to **False** to remove the Calling app from the left rail and to remove the Calling and Video Call options in private chat.</span></span> |

### <a name="powershell-instructions"></a><span data-ttu-id="8d692-120">PowerShell の指示</span><span class="sxs-lookup"><span data-stu-id="8d692-120">PowerShell instructions</span></span>

1.  <span data-ttu-id="8d692-121">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="8d692-121">Launch PowerShell as an Administrator.</span></span>
2.  <span data-ttu-id="8d692-122">Skype オンラインのコネクタに接続します。</span><span class="sxs-lookup"><span data-stu-id="8d692-122">Connect to Skype Online Connector:</span></span><br>
<span data-ttu-id="8d692-123">\>> *# Office 365 のユーザー名とパスワードを設定します。*</span><span class="sxs-lookup"><span data-stu-id="8d692-123">\>> *# Set Office 365 User Name and Password*</span></span><br>
<span data-ttu-id="8d692-124">\>> *$username$ ="管理者の電子メール アドレス]*</span><span class="sxs-lookup"><span data-stu-id="8d692-124">\>> *$username = “admin email address”*</span></span><br>
<span data-ttu-id="8d692-125">\>> *$password =「パスワード」を寄せ SecureString-AsPlainText-フォース*</span><span class="sxs-lookup"><span data-stu-id="8d692-125">\>> *$password = ConvertTo-SecureString "password" -AsPlainText -Force*</span></span><br>
<span data-ttu-id="8d692-126">\>> *$LiveCred = 新しいオブジェクトの型名 System.Management.Automation.PSCredential の引き数リスト $username$、$password*</span><span class="sxs-lookup"><span data-stu-id="8d692-126">\>> *$LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password*</span></span><br><br>
<span data-ttu-id="8d692-127">\>> *# Skype をオンライン接続します。*</span><span class="sxs-lookup"><span data-stu-id="8d692-127">\>> *# Connect to Skype Online*</span></span><br>
<span data-ttu-id="8d692-128">\>> *インポート モジュール SkypeOnlineConnector*</span><span class="sxs-lookup"><span data-stu-id="8d692-128">\>> *Import-Module SkypeOnlineConnector*</span></span><br>
<span data-ttu-id="8d692-129">\>> *$sfboSession = New CsOnlineSession-資格情報の $LiveCred*</span><span class="sxs-lookup"><span data-stu-id="8d692-129">\>> *$sfboSession = New-CsOnlineSession -Credential $LiveCred*</span></span><br>
<span data-ttu-id="8d692-130">\>> *インポート-PSSession $sfboSession*</span><span class="sxs-lookup"><span data-stu-id="8d692-130">\>> *Import-PSSession $sfboSession*</span></span><br>
3.  <span data-ttu-id="8d692-131">ポリシーのオプションを呼び出すことの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="8d692-131">View list of Calling Policy Options:</span></span><br>
<span data-ttu-id="8d692-132">\>> *Get CsTeamsCallingPolicy*</span><span class="sxs-lookup"><span data-stu-id="8d692-132">\>> *Get-CsTeamsCallingPolicy*</span></span>
4.  <span data-ttu-id="8d692-133">呼び出し元のすべてのポリシーが無効になっている、事前に定義されたオプションになります。</span><span class="sxs-lookup"><span data-stu-id="8d692-133">Look for the pre-canned option where all calling policies are disabled:</span></span><br>
<span data-ttu-id="8d692-134">![無効になっているすべての会議ポリシーを使用して会議のオプションのスクリーン ショットです。](media/virtual-environment-image2.png)</span><span class="sxs-lookup"><span data-stu-id="8d692-134">![Screenshot of meetings option with all meeting policies disabled.](media/virtual-environment-image2.png)</span></span>
5.  <span data-ttu-id="8d692-135">仮想化環境でチームを使用するすべてのユーザーに"DisallowCalling"の事前に定義されたポリシーのオプションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d692-135">Apply the “DisallowCalling” pre-canned policy option to all users who will be using Teams in a virtualized environment:</span></span><br>
<span data-ttu-id="8d692-136">\>> *DisallowCalling を与える CsTeamsCallingPolicy グループのユーザー電子メール id の Id*</span><span class="sxs-lookup"><span data-stu-id="8d692-136">\>> *Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”*</span></span>

## <a name="meetings"></a><span data-ttu-id="8d692-137">会議</span><span class="sxs-lookup"><span data-stu-id="8d692-137">Meetings</span></span>

<span data-ttu-id="8d692-138">*CsTeamsMeetingPolicy*コマンドレットは、ユーザーが作成したミーティングや会議中にアクセスできる機能の種類を制御する管理者を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8d692-138">The *CsTeamsMeetingPolicy* cmdlets enable administrators to control the type of meetings that users can create or the features that they can access while in a meeting.</span></span> <span data-ttu-id="8d692-139">匿名または外部のユーザーとの会議の処理方法を決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d692-139">It also helps determine how meetings deal with anonymous or external users.</span></span>

|<span data-ttu-id="8d692-140">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="8d692-140">Policy name</span></span> |<span data-ttu-id="8d692-141">説明</span><span class="sxs-lookup"><span data-stu-id="8d692-141">Description</span></span>  |<span data-ttu-id="8d692-142">推奨値</span><span class="sxs-lookup"><span data-stu-id="8d692-142">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8d692-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8d692-143">AllowPrivateMeetingScheduling</span></span>    |<span data-ttu-id="8d692-144">ユーザーが秘密の会議をスケジュールできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-144">Determines whether a user would be allowed to schedule private meetings.</span></span>         |<span data-ttu-id="8d692-145">**False を指定**するユーザーの秘密の会議をスケジュールすることを禁止するのには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-145">Set this to **False** to prohibit the user from being able to schedule private meetings.</span></span>         |
|<span data-ttu-id="8d692-146">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8d692-146">AllowChannelMeetingScheduling</span></span>     |<span data-ttu-id="8d692-147">ユーザーはチャネルのミーティングをスケジュールできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-147">Determines whether a user would be allowed to schedule channel meetings.</span></span>         |<span data-ttu-id="8d692-148">**False**にチャネルの会議をスケジュールすることを禁止するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-148">Set this to **False** to prohibit the user from being able to schedule channel meetings.</span></span>         |
|<span data-ttu-id="8d692-149">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="8d692-149">AllowMeetNow</span></span>     |<span data-ttu-id="8d692-150">ユーザーが作成または、臨時会議を開始できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-150">Determines whether a user would be allowed to create or start ad-hoc meetings.</span></span>         |<span data-ttu-id="8d692-151">**False**に、臨時会議を開始することを禁止するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-151">Set this to **False** to prohibit the user from being able to start ad-hoc meetings.</span></span>         |
|<span data-ttu-id="8d692-152">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="8d692-152">ScreenSharingMode</span></span>     |<span data-ttu-id="8d692-153">ユーザーが通話や会議での画面を共有する許可は、モードを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-153">Determines the mode in which a user would be allowed to share screen in calls or meetings.</span></span>         |<span data-ttu-id="8d692-154">] に**無効な**ユーザーが、画面を共有することを禁止するのには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-154">Set this to **Disabled** to prohibit the user from sharing their screens.</span></span>         |
|<span data-ttu-id="8d692-155">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="8d692-155">AllowIPVideo</span></span>     |<span data-ttu-id="8d692-156">ユーザーの会議または呼び出しにビデオが有効になっているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-156">Determines whether video is enabled in a user's meetings or calls.</span></span>         |<span data-ttu-id="8d692-157">**False**に、ビデオの共有からユーザーを禁止するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-157">Set this to **False** to prohibit the user from sharing their video.</span></span>         |
|<span data-ttu-id="8d692-158">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="8d692-158">AllowAnonymousUsersToDialOut</span></span>     |<span data-ttu-id="8d692-159">匿名ユーザーが PSTN 番号にダイアル アウトできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-159">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span>         |<span data-ttu-id="8d692-160">**False を指定**する匿名ユーザーが発信することを禁止するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-160">Set this to **False** to prohibit anonymous users from dialing out.</span></span>         |
|<span data-ttu-id="8d692-161">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="8d692-161">AllowAnonymousUsersToStartMeeting</span></span>     |<span data-ttu-id="8d692-162">匿名ユーザーが会議を開始できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-162">Determines whether anonymous users can initiate a meeting.</span></span>         |<span data-ttu-id="8d692-163">に**false を指定**して会議を開始することを禁止するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-163">Set this to **False** to prohibit them from initiating a meeting.</span></span>         |
|<span data-ttu-id="8d692-164">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="8d692-164">AllowOutlookAddIn</span></span>     |<span data-ttu-id="8d692-165">ユーザーが Outlook デスクトップ クライアントでチームのミーティングをスケジュールできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-165">Determines whether a user can schedule Teams Meetings in Outlook desktop client.</span></span>         |<span data-ttu-id="8d692-166">**False を指定**すると、ユーザーが Outlook クライアントでのチーム ミーティングをスケジュールすることを禁止するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-166">Set this to **False** to prohibit a user from scheduling Teams meeting in Outlook client.</span></span>         |
|<span data-ttu-id="8d692-167">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="8d692-167">AllowParticipantGiveRequestControl</span></span>     |<span data-ttu-id="8d692-168">参加者が要求または、画面の共有を制御できるようにするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-168">Determines whether participants can request or give control of screen sharing.</span></span>         |<span data-ttu-id="8d692-169">この設定を**False**に、ユーザーを禁止すること、会議の制御を要求します。</span><span class="sxs-lookup"><span data-stu-id="8d692-169">Set this to **False** to prohibit the user from giving, requesting control in a meeting.</span></span>         |
|<span data-ttu-id="8d692-170">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="8d692-170">AllowExternalParticipantGiveRequestControl</span></span>     |<span data-ttu-id="8d692-171">外部の参加者が要求または、画面の共有を制御できるようにするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-171">Determines whether external participants can request or give control of screen sharing.</span></span>         |<span data-ttu-id="8d692-172">この設定を**False**に外部ユーザーを禁止すること、会議の制御を要求します。</span><span class="sxs-lookup"><span data-stu-id="8d692-172">Set this to **False** to prohibit an external user from giving, requesting control in a meeting.</span></span>         |
|<span data-ttu-id="8d692-173">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="8d692-173">AllowPowerPointSharing</span></span>     |<span data-ttu-id="8d692-174">ユーザーの会議で PowerPoint の共有を許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-174">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span>         |<span data-ttu-id="8d692-175">に**true を指定**できるようにするには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-175">Set this to **True** to allow.</span></span><br><span data-ttu-id="8d692-176">**False を指定**するユーザーが会議中の PowerPoint ファイルを共有することを禁止するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-176">Set this to **False** to prohibit user from sharing PowerPoint files in a meeting.</span></span>         |
|<span data-ttu-id="8d692-177">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="8d692-177">AllowWhiteboard</span></span>     |<span data-ttu-id="8d692-178">ユーザーの会議でホワイト ボードを許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-178">Determines whether whiteboard is allowed in a user’s meetings.</span></span>         |<span data-ttu-id="8d692-179">**False**に、会議でホワイト ボード アプリケーションを禁止するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-179">Set this to **False** to prohibit whiteboard application in a meeting.</span></span>         |
|<span data-ttu-id="8d692-180">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="8d692-180">AllowTranscription</span></span>     |<span data-ttu-id="8d692-181">ユーザーの会議で、リアルタイムまたは会議後のキャプションおよびトランスクリプションができるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-181">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>         |<span data-ttu-id="8d692-182">**False**に議事録と会議でキャプションを禁止するには、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d692-182">Set this to **False** to prohibit transcription and captioning in a meeting.</span></span>         |

### <a name="powershell-instructions"></a><span data-ttu-id="8d692-183">PowerShell の指示</span><span class="sxs-lookup"><span data-stu-id="8d692-183">PowerShell instructions</span></span>

1.  <span data-ttu-id="8d692-184">管理者として PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="8d692-184">Launch PowerShell as an Administrator.</span></span>
2.  <span data-ttu-id="8d692-185">Skype オンラインのコネクタに接続します。</span><span class="sxs-lookup"><span data-stu-id="8d692-185">Connect to Skype Online Connector:</span></span><br>
<span data-ttu-id="8d692-186">\>> *# Office 365 のユーザー名とパスワードを設定します。*</span><span class="sxs-lookup"><span data-stu-id="8d692-186">\>> *# Set Office 365 User Name and Password*</span></span><br>
<span data-ttu-id="8d692-187">\>> *$username$ ="管理者の電子メール アドレス]*</span><span class="sxs-lookup"><span data-stu-id="8d692-187">\>> *$username = “admin email address”*</span></span><br>
<span data-ttu-id="8d692-188">\>> *$password =「パスワード」を寄せ SecureString-AsPlainText-フォース*</span><span class="sxs-lookup"><span data-stu-id="8d692-188">\>> *$password = ConvertTo-SecureString "password" -AsPlainText -Force*</span></span><br>
<span data-ttu-id="8d692-189">\>> *$LiveCred = 新しいオブジェクトの型名 System.Management.Automation.PSCredential の引き数リスト $username$、$password*</span><span class="sxs-lookup"><span data-stu-id="8d692-189">\>> *$LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password*</span></span><br><br>
<span data-ttu-id="8d692-190">\>> *# Skype をオンライン接続します。*</span><span class="sxs-lookup"><span data-stu-id="8d692-190">\>> *# Connect to Skype Online*</span></span><br>
<span data-ttu-id="8d692-191">\>> *インポート モジュール SkypeOnlineConnector*</span><span class="sxs-lookup"><span data-stu-id="8d692-191">\>> *Import-Module SkypeOnlineConnector*</span></span><br>
<span data-ttu-id="8d692-192">\>> *$sfboSession = New CsOnlineSession-資格情報の $LiveCred*</span><span class="sxs-lookup"><span data-stu-id="8d692-192">\>> *$sfboSession = New-CsOnlineSession -Credential $LiveCred*</span></span><br>
<span data-ttu-id="8d692-193">\>> *インポート-PSSession $sfboSession*</span><span class="sxs-lookup"><span data-stu-id="8d692-193">\>> *Import-PSSession $sfboSession*</span></span>
3.  <span data-ttu-id="8d692-194">[ミーティング ポリシーのオプションの一覧を表示:</span><span class="sxs-lookup"><span data-stu-id="8d692-194">View list of Meeting Policy Options:</span></span><br>
<span data-ttu-id="8d692-195">\>> *Get CsTeamsMeetingPolicy*</span><span class="sxs-lookup"><span data-stu-id="8d692-195">\>> *Get-CsTeamsMeetingPolicy*</span></span>
4.  <span data-ttu-id="8d692-196">会議のすべてのポリシーが無効になっている事前に定義されたオプションになります。</span><span class="sxs-lookup"><span data-stu-id="8d692-196">Look for the pre-canned option where all meeting policies are disabled:</span></span><br>
<span data-ttu-id="8d692-197">![オプションを無効になっているすべての会議ポリシーを使用して呼び出すことのスクリーン ショットです。](media/virtual-environment-image1.png)</span><span class="sxs-lookup"><span data-stu-id="8d692-197">![Screenshot of calling option with all meeting policies disabled.](media/virtual-environment-image1.png)</span></span>
5.  <span data-ttu-id="8d692-198">仮想化環境でチームを使用するすべてのユーザーに"AllOff"の事前に定義されたポリシーのオプションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d692-198">Apply the “AllOff” pre-canned policy option to all users who will be using Teams in a virtualized environment:</span></span><br>
<span data-ttu-id="8d692-199">\>> *AllOff を与える CsTeamsMeetingPolicy グループのユーザー電子メール id の Id*</span><span class="sxs-lookup"><span data-stu-id="8d692-199">\>> *Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”*</span></span>

##<a name="known-limitations"></a><span data-ttu-id="8d692-200">既知の制限</span><span class="sxs-lookup"><span data-stu-id="8d692-200">Known limitations</span></span>

<span data-ttu-id="8d692-201">以外にも記載されているオーディオとビデオの制限の同は、仮想化環境上のユーザーが直面する可能性がありますいくつか追加の制限があります。</span><span class="sxs-lookup"><span data-stu-id="8d692-201">Besides the audio and video limitations previosly mentioned, there are some additional limitations users on virtualized environments might face:</span></span>

- <span data-ttu-id="8d692-202">**他のユーザーによって作成されたミーティングに参加します。**</span><span class="sxs-lookup"><span data-stu-id="8d692-202">**Joining meetings created by others.**</span></span> <span data-ttu-id="8d692-203">場合でも、上記のポリシーでは、ユーザーが会議の作成を制限では、他のユーザーによって送信された会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="8d692-203">Even though the above policies restrict users from creating meetings, they will still be able to join meetings sent out by other users.</span></span> <span data-ttu-id="8d692-204">これらの会議でホワイト ボードを使用して、ビデオを共有する機能とかどうか管理者それらを無効にしない、または [その他の機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8d692-204">Within these meetings, their ability to share video, use WhiteBoard and other features will depend on whether the admin disabled them or not.</span></span>

- <span data-ttu-id="8d692-205">**関連する問題では、コンテンツがキャッシュされます。**</span><span class="sxs-lookup"><span data-stu-id="8d692-205">**Issues related to cached content.**</span></span> <span data-ttu-id="8d692-206">チームが実行されている仮想環境が永続化されていないかどうか (データがクリーンアップ各ユーザー セッションの終了時)、ユーザーがクライアントのすべてのコンテンツをかどうかに関係なく、もう一度再ダウンロードすることによるパフォーマンスの低下に気付く可能性があります特定のユーザー前のセッションで同じコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8d692-206">If the virtual environment that Teams is running in is not persisted (data is cleaned up at the end of each user session), users might notice performance degradation due to the client having to re-download all content again, regardless of whether the given user accessed the same content in a previous session.</span></span> <span data-ttu-id="8d692-207">FSLogix で提供されるよう、移動のキャッシュ ソリューションを使用して、パフォーマンスへの影響を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="8d692-207">This performance impact can be mitigated by using roaming cache solutions, such as those provided by FSLogix.</span></span>

<span data-ttu-id="8d692-208">チームが仮想デスクトップ環境で使用するため最適化された後、管理者はこれらのポリシーを元に戻すし、通常どおりには、チームを使用するユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="8d692-208">Once Teams has been optimized for use within Virtual Desktop environments, admins can revert these policies and allow users to use Teams as they normally would.</span></span>

         
        
        
        
        
        
        
        
        
        
        


