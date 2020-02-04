---
title: 'Lync Server 2013: お知らせを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfae1817cb47c769885ca42a7ca3ff6f57f7b669
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="bd300-102">Lync Server 2013 でお知らせを作成する</span><span class="sxs-lookup"><span data-stu-id="bd300-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd300-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bd300-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bd300-104">新しいアナウンスを作成するには、次のステップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd300-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="bd300-105">音声ガイダンスの場合は、好みのオーディオ録音アプリケーションを使用してオーディオ ファイルを録音します。</span><span class="sxs-lookup"><span data-stu-id="bd300-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="bd300-106">音声ガイダンスの場合は、**Import-CsAnnouncementFile** コマンドレットを実行して、ファイル ストアにオーディオ ファイルの内容をインポートします。</span><span class="sxs-lookup"><span data-stu-id="bd300-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="bd300-107">**New-CsAnnouncement** コマンドレットを実行して、アナウンスを作成して名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="bd300-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="bd300-108">このステップを実行して、音声ガイダンス、音声合成 (TTS) による音声ガイダンス、または音声ガイダンスなしのアナウンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd300-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="bd300-109">たとえば、メッセージを再生することなく、指定した宛先へ呼び出しを転送する場合は、音声ガイダンスなしのアナウンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bd300-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="bd300-110">新しいアナウンスを、割り当てられていない番号の表の番号範囲に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bd300-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="bd300-111">ここでは、アナウンスをインポートおよび作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bd300-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="bd300-112">[割り当てられていない番号] テーブルにお知らせを割り当てる方法について詳しくは、「 [Lync Server 2013 で未割り当ての番号表を構成する](lync-server-2013-configure-the-unassigned-number-table.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd300-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="bd300-113">新しいアナウンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="bd300-113">To create a new announcement</span></span>

1.  <span data-ttu-id="bd300-114">音声ガイダンスの場合は、オーディオ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd300-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="bd300-115">Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bd300-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="bd300-116">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd300-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="bd300-117">音声ガイダンスの場合は、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="bd300-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="bd300-118">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd300-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="bd300-p103">呼び出しをボイス メールに転送する場合は、sip:username@domainname;opaque=app:voicemail の形式で SIPAddress を入力します (たとえば、sip:bob@contoso.com;opaque=app:voicemail)。呼び出しを電話番号に転送する場合は、sip:number@domainname;user=phone の形式で SIPAddress を入力します (たとえば、sip:+ 14255550121@contoso.com;user=phone)。</span><span class="sxs-lookup"><span data-stu-id="bd300-p103">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="bd300-121">たとえば、音声ガイダンスを指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd300-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="bd300-122">たとえば、TTS によるガイダンスを指定するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd300-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="bd300-123">これらのコマンドレットについて詳しくは、「 **TextToSpeechPrompt**パラメーターで使う言語コードの一覧[を表示する](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd300-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd300-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd300-124">See Also</span></span>


[<span data-ttu-id="bd300-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="bd300-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="bd300-126">新しい CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="bd300-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="bd300-127">Lync Server 2013 での割り当てられていない番号の表の構成</span><span class="sxs-lookup"><span data-stu-id="bd300-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

