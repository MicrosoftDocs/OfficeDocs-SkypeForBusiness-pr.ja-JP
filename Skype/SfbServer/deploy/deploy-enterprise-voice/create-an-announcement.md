---
title: 作成またはビジネス サーバーの Skype でお知らせを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype のアプリケーションを発表のお知らせを削除します。 この設定によって、割り当てられていない番号への通話を処理する方法が影響を受けます。
ms.openlocfilehash: 831cb389a97ea45130875b76005aab2059cf08ab
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23260140"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="fb5ab-104">作成またはビジネス サーバーの Skype でお知らせを削除します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="fb5ab-105">作成またはビジネス サーバーのエンタープライズ VoIP の Skype のアプリケーションを発表のお知らせを削除します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="fb5ab-106">これは、割り当てられていない番号への通話の処理方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="fb5ab-p103">アナウンスを構成した場合、実際にはそれは割り当てられていない番号への通話の処理方法を構成することになります。オーディオ ファイルまたは音声合成 (TTS) ファイルによる音声ガイダンスを再生するか、または音声ガイダンスを再生することなく、ただ指定した宛先へ呼び出しを転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="fb5ab-p104">割り当てられていない番号の表を定義する前に、アナウンスを作成する必要があります。音声ガイダンスまたは TTS による音声ガイダンスを使用するアナウンスすべて、または音声ガイダンスなしのアナウンスすべてに対して、このステップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="fb5ab-111">ここでは、アナウンスをインポートおよび作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="fb5ab-112">表には、未使用の番号のお知らせの割り当ての詳細については、[割り当てられていない番号テーブルの設定](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="fb5ab-113">割り当てられていない番号向けに新しいアナウンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="fb5ab-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="fb5ab-114">新しいアナウンスを作成するには、次のステップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="fb5ab-115">音声ガイダンスの場合は、好みのオーディオ録音アプリケーションを使用してオーディオ ファイルを録音します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="fb5ab-116">オーディオ プロンプトは、音声ファイルの内容をファイル ストアにインポートする**インポート CsAnnouncementFile**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="fb5ab-117">お知らせの名前を作成する**新規 CsAnnouncement**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="fb5ab-118">このステップを実行して、音声ガイダンス、音声合成 (TTS) による音声ガイダンス、または音声ガイダンスなしのアナウンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="fb5ab-119">たとえば、メッセージを再生することなく、指定した宛先へ呼び出しを転送する場合は、音声ガイダンスなしのアナウンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="fb5ab-120">新しいアナウンスを、割り当てられていない番号の表の番号範囲に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="fb5ab-121">新しいアナウンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="fb5ab-121">To create a new announcement</span></span>

1. <span data-ttu-id="fb5ab-122">音声ガイダンスの場合は、オーディオ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="fb5ab-123">RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="fb5ab-124">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="fb5ab-125">音声ガイダンスの場合は、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-125">For audio prompts, run:</span></span>

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="fb5ab-126">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-126">Run:</span></span>

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="fb5ab-p107">呼び出しをボイス メールに転送する場合は、sip:username@domainname;opaque=app:voicemail の形式で SIPAddress を入力します (たとえば、sip:bob@contoso.com;opaque=app:voicemail)。呼び出しを電話番号に転送する場合は、sip:number@domainname;user=phone の形式で SIPAddress を入力します (たとえば、sip:+ 14255550121@contoso.com;user=phone)。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="fb5ab-129">たとえば、音声ガイダンスを指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-129">For example, to specify an audio prompt:</span></span>

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="fb5ab-130">たとえば、TTS によるガイダンスを指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-130">For example, to specify a TTS prompt:</span></span>

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

  <span data-ttu-id="fb5ab-131">**TextToSpeechPrompt**パラメーターで使用する言語コードの一覧を表示してこれらのコマンドレットについての詳細については、[新規 CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="fb5ab-132">割り当てられていない番号のアナウンスの削除</span><span class="sxs-lookup"><span data-stu-id="fb5ab-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="fb5ab-133">アナウンスを削除するには</span><span class="sxs-lookup"><span data-stu-id="fb5ab-133">To delete an announcement</span></span>

1. <span data-ttu-id="fb5ab-134">RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="fb5ab-135">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="fb5ab-p108">組織のすべてのアナウンスの一覧を取得します。コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="fb5ab-p109">表示された一覧で、削除するアナウンスを見つけて、その GUID をコピーします。次に、コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="fb5ab-140">例:</span><span class="sxs-lookup"><span data-stu-id="fb5ab-140">For example:</span></span>

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="fb5ab-141">詳細オプションの詳細については、 [Get CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)と[削除 CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb5ab-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb5ab-142">See also</span></span>

[<span data-ttu-id="fb5ab-143">作成またはビジネス サーバーの Skype でお知らせを削除します。</span><span class="sxs-lookup"><span data-stu-id="fb5ab-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="fb5ab-144">インポート-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="fb5ab-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="fb5ab-145">新しい-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="fb5ab-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="fb5ab-146">削除 CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="fb5ab-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="fb5ab-147">Get CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="fb5ab-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

