---
title: 'Lync Server 2013: アナウンスの作成'
TOCTitle: アナウンスの作成
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48273171
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのアナウンスの作成

 

_**トピックの最終更新日:** 2012-11-01_

新しいアナウンスを作成するには、次のステップを実行する必要があります。

1.  音声ガイダンスの場合は、好みのオーディオ録音アプリケーションを使用してオーディオ ファイルを録音します。

2.  音声ガイダンスの場合は、 **Import-CsAnnouncementFile** コマンドレットを実行して、ファイル ストアにオーディオ ファイルの内容をインポートします。

3.  **New-CsAnnouncement** コマンドレットを実行して、アナウンスを作成して名前を付けます。このステップを実行して、音声ガイダンス、音声合成 (TTS) による音声ガイダンス、または音声ガイダンスなしのアナウンスを作成します。
    

    > [!TIP]
    > たとえば、メッセージを再生することなく、指定した宛先へ呼び出しを転送する場合は、音声ガイダンスなしのアナウンスを作成できます。



4.  新しいアナウンスを、割り当てられていない番号の表の番号範囲に割り当てます。

ここでは、アナウンスをインポートおよび作成する方法について説明します。割り当てられていない番号の表にアナウンスを割り当てる方法の詳細については、「[Lync Server 2013 での割り当てられていない番号の表の構成](lync-server-2013-configure-the-unassigned-number-table.md)」を参照してください。

## 新しいアナウンスを作成するには

1.  音声ガイダンスの場合は、オーディオ ファイルを作成します。

2.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

3.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

4.  音声ガイダンスの場合は、次のように実行します。
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  次のコマンドレットを実行します。
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    呼び出しをボイス メールに転送する場合は、sip:username@domainname;opaque=app:voicemail の形式で SIPAddress を入力します (たとえば、sip:bob@contoso.com;opaque=app:voicemail)。呼び出しを電話番号に転送する場合は、sip:number@domainname;user=phone の形式で SIPAddress を入力します (たとえば、sip:+ 14255550121@contoso.com;user=phone)。
    
    たとえば、音声ガイダンスを指定するには、次の形式を使用します。
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    たとえば、TTS による音声ガイダンスを指定するには、次の形式を使用します。
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    これらのコマンドレットの詳細と、 **TextToSpeechPrompt** パラメーターで使用する言語コードの一覧については、「[New-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAnnouncement)」を参照してください。

## 関連項目

#### その他のリソース

[Import-CsAnnouncementFile](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsAnnouncementFile)  
[New-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAnnouncement)  
[Lync Server 2013 での割り当てられていない番号の表の構成](lync-server-2013-configure-the-unassigned-number-table.md)

