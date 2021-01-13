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
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Skype for Business Server でアナウンスを作成または削除する

Skype for Business Server エンタープライズ VoIP でアナウンス アプリケーションのお知らせを作成または削除します。 これは、割り当てられていない番号への呼び出しの処理方法に影響します。

アナウンスを構成する場合、実際には、割り当てられていない番号への呼び出しの処理方法を構成します。 音声ファイルや音声合成 (TTS) ファイルなど、音声プロンプトを再生したり、音声プロンプトを再生せずに呼び出しを指定の宛先に転送することができます。

割り当てられていない番号の表を定義する前に、アナウンスを作成する必要があります。 音声プロンプト、TTS プロンプト、または音声案内を使用するアナウンスすべてについて、この手順を実行する必要があります。

ここでは、アナウンスをインポートおよび作成する方法について説明します。 割り当てられていない番号の表にアナウンスを割り当てる方法の詳細については、「[Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)」を参照してください。

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>割り当てられていない番号の新しいアナウンスを作成する

新しいアナウンスを作成するには、次のステップを実行する必要があります。

1. 音声ガイダンスの場合は、好みのオーディオ録音アプリケーションを使用してオーディオ ファイルを録音します。

2. 音声ガイダンスの場合は、**Import-CsAnnouncementFile** コマンドレットを実行して、ファイル ストアにオーディオ ファイルの内容をインポートします。

3. **New-CsAnnouncement** コマンドレットを実行して、アナウンスを作成して名前を付けます。 このステップを実行して、音声ガイダンス、音声合成 (TTS) による音声ガイダンス、または音声ガイダンスなしのアナウンスを作成します。

    > [!TIP]
    > たとえば、メッセージを再生することなく、指定した宛先へ呼び出しを転送する場合は、音声ガイダンスなしのアナウンスを作成できます。

4. 新しいアナウンスを、割り当てられていない番号の表の番号範囲に割り当てます。

### <a name="to-create-a-new-announcement"></a>新しいアナウンスを作成するには

1. 音声ガイダンスの場合は、オーディオ ファイルを作成します。

2. Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**

3. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

4. 音声ガイダンスの場合は、次のように実行します。

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. 次のコマンドを実行します。

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    呼び出しをボイス メールに転送する場合は、sip:username@domainname;opaque=app:voicemail の形式で SIPAddress を入力します (たとえば、sip:bob@contoso.com;opaque=app:voicemail)。 呼び出しを電話番号に転送する場合は、sip:number@domainname;user=phone の形式で SIPAddress を入力します (たとえば、sip:+ 14255550121@contoso.com;user=phone)。

    たとえば、音声ガイダンスを指定するには、次の形式を使用します。

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    たとえば、TTS による音声ガイダンスを指定するには、次の形式を使用します。

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   これらのコマンドレットの詳細と **、TextToSpeechPrompt** パラメーターで使用する言語コードの一覧については [、「New-CsAnnouncement」](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)を参照してください。

## <a name="delete-an-announcement-for-unassigned-numbers"></a>割り当てられていない番号のアナウンスを削除する

### <a name="to-delete-an-announcement"></a>アナウンスを削除するには

1. Skype for Business Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「セットアップのアクセス許可の委任」で説明されている必要なユーザー権限を使用してログオン **します。**

2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。

3. 組織のすべてのアナウンスの一覧を取得します。コマンド ラインで次のコマンドを実行します。

   ```powershell
   Get-CsAnnouncement
   ```

4. 表示された一覧で、削除するアナウンスを見つけて、その GUID をコピーします。次に、コマンド ラインで次のコマンドを実行します。

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    次に例を示します。

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > その他のオプションの詳細については [、「Get-CsAnnouncement」](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) および [「Remove-CsAnnouncement」を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)。

## <a name="see-also"></a>関連項目

[Skype for Business Server でアナウンスを作成または削除する](create-an-announcement.md)

[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

