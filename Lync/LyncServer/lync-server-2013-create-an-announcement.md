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

# <a name="create-an-announcement-in-lync-server-2013"></a>Lync Server 2013 でお知らせを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

新しいアナウンスを作成するには、次のステップを実行する必要があります。

1.  音声ガイダンスの場合は、好みのオーディオ録音アプリケーションを使用してオーディオ ファイルを録音します。

2.  音声ガイダンスの場合は、**Import-CsAnnouncementFile** コマンドレットを実行して、ファイル ストアにオーディオ ファイルの内容をインポートします。

3.  **New-CsAnnouncement** コマンドレットを実行して、アナウンスを作成して名前を付けます。 このステップを実行して、音声ガイダンス、音声合成 (TTS) による音声ガイダンス、または音声ガイダンスなしのアナウンスを作成します。
    
    <div>
    

    > [!TIP]  
    > たとえば、メッセージを再生することなく、指定した宛先へ呼び出しを転送する場合は、音声ガイダンスなしのアナウンスを作成できます。

    
    </div>

4.  新しいアナウンスを、割り当てられていない番号の表の番号範囲に割り当てます。

ここでは、アナウンスをインポートおよび作成する方法について説明します。 [割り当てられていない番号] テーブルにお知らせを割り当てる方法について詳しくは、「 [Lync Server 2013 で未割り当ての番号表を構成する](lync-server-2013-configure-the-unassigned-number-table.md)」をご覧ください。

<div>

## <a name="to-create-a-new-announcement"></a>新しいアナウンスを作成するには

1.  音声ガイダンスの場合は、オーディオ ファイルを作成します。

2.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。

3.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

4.  音声ガイダンスの場合は、次のように実行します。
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  次のコマンドレットを実行します。
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    呼び出しをボイス メールに転送する場合は、sip:username@domainname;opaque=app:voicemail の形式で SIPAddress を入力します (たとえば、sip:bob@contoso.com;opaque=app:voicemail)。呼び出しを電話番号に転送する場合は、sip:number@domainname;user=phone の形式で SIPAddress を入力します (たとえば、sip:+ 14255550121@contoso.com;user=phone)。
    
    たとえば、音声ガイダンスを指定するには、次の形式を使用します。
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    たとえば、TTS によるガイダンスを指定するには、次の形式を使用します。
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    これらのコマンドレットについて詳しくは、「 **TextToSpeechPrompt**パラメーターで使う言語コードの一覧[を表示する](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)」をご覧ください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[新しい CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[Lync Server 2013 での割り当てられていない番号の表の構成](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

