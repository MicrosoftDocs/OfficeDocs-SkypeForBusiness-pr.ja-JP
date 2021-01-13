---
title: Skype for Business Server でアナウンスを作成または削除する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Skype for Business Server エンタープライズ VoIP でアナウンス アプリケーションのお知らせを作成または削除します。 これは、割り当てられていない番号への呼び出しの処理方法に影響します。
ms.openlocfilehash: 9f2b4fcda8e98d4b939b6b443da875dbe153546c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824907"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="a50a7-104">Skype for Business Server でアナウンスを作成または削除する</span><span class="sxs-lookup"><span data-stu-id="a50a7-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="a50a7-105">Skype for Business Server エンタープライズ VoIP でアナウンス アプリケーションのお知らせを作成または削除します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="a50a7-106">これは、割り当てられていない番号への呼び出しの処理方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="a50a7-107">アナウンスを構成する場合、実際には、割り当てられていない番号への呼び出しの処理方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-107">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled.</span></span> <span data-ttu-id="a50a7-108">音声ファイルや音声合成 (TTS) ファイルなど、音声プロンプトを再生したり、音声プロンプトを再生せずに呼び出しを指定の宛先に転送することができます。</span><span class="sxs-lookup"><span data-stu-id="a50a7-108">You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="a50a7-109">割り当てられていない番号の表を定義する前に、アナウンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a50a7-109">You need to create announcements before you define the unassigned number table.</span></span> <span data-ttu-id="a50a7-110">音声プロンプト、TTS プロンプト、または音声案内を使用するアナウンスすべてについて、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a50a7-110">You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="a50a7-111">ここでは、アナウンスをインポートおよび作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="a50a7-112">割り当てられていない番号の表にアナウンスを割り当てる方法の詳細については、「[Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50a7-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="a50a7-113">割り当てられていない番号の新しいアナウンスを作成する</span><span class="sxs-lookup"><span data-stu-id="a50a7-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="a50a7-114">新しいアナウンスを作成するには、次のステップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a50a7-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="a50a7-115">音声ガイダンスの場合は、好みのオーディオ録音アプリケーションを使用してオーディオ ファイルを録音します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="a50a7-116">音声ガイダンスの場合は、**Import-CsAnnouncementFile** コマンドレットを実行して、ファイル ストアにオーディオ ファイルの内容をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a50a7-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="a50a7-117">**New-CsAnnouncement** コマンドレットを実行して、アナウンスを作成して名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a50a7-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="a50a7-118">このステップを実行して、音声ガイダンス、音声合成 (TTS) による音声ガイダンス、または音声ガイダンスなしのアナウンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="a50a7-119">たとえば、メッセージを再生することなく、指定した宛先へ呼び出しを転送する場合は、音声ガイダンスなしのアナウンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a50a7-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="a50a7-120">新しいアナウンスを、割り当てられていない番号の表の番号範囲に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a50a7-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="a50a7-121">新しいアナウンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="a50a7-121">To create a new announcement</span></span>

1. <span data-ttu-id="a50a7-122">音声ガイダンスの場合は、オーディオ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="a50a7-123">Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**</span><span class="sxs-lookup"><span data-stu-id="a50a7-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="a50a7-124">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50a7-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="a50a7-125">音声ガイダンスの場合は、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="a50a7-126">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="a50a7-p107">呼び出しをボイス メールに転送する場合は、sip:username@domainname;opaque=app:voicemail の形式で SIPAddress を入力します (たとえば、sip:bob@contoso.com;opaque=app:voicemail)。 呼び出しを電話番号に転送する場合は、sip:number@domainname;user=phone の形式で SIPAddress を入力します (たとえば、sip:+ 14255550121@contoso.com;user=phone)。</span><span class="sxs-lookup"><span data-stu-id="a50a7-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="a50a7-129">たとえば、音声ガイダンスを指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="a50a7-130">たとえば、TTS による音声ガイダンスを指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="a50a7-131">これらのコマンドレットの詳細と **、TextToSpeechPrompt** パラメーターで使用する言語コードの一覧については [、「New-CsAnnouncement」](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50a7-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="a50a7-132">割り当てられていない番号のアナウンスを削除する</span><span class="sxs-lookup"><span data-stu-id="a50a7-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="a50a7-133">アナウンスを削除するには</span><span class="sxs-lookup"><span data-stu-id="a50a7-133">To delete an announcement</span></span>

1. <span data-ttu-id="a50a7-134">Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**</span><span class="sxs-lookup"><span data-stu-id="a50a7-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="a50a7-135">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50a7-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="a50a7-p108">組織のすべてのアナウンスの一覧を取得します。コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="a50a7-p109">表示された一覧で、削除するアナウンスを見つけて、その GUID をコピーします。次に、コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="a50a7-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a50a7-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="a50a7-141">その他のオプションの詳細については [、「Get-CsAnnouncement」](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) および [「Remove-CsAnnouncement」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a50a7-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="a50a7-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="a50a7-142">See also</span></span>

[<span data-ttu-id="a50a7-143">Skype for Business Server でアナウンスを作成または削除する</span><span class="sxs-lookup"><span data-stu-id="a50a7-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="a50a7-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="a50a7-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="a50a7-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="a50a7-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="a50a7-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="a50a7-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="a50a7-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="a50a7-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

