---
title: 作成またはビジネス サーバーの Skype でお知らせを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype のアプリケーションを発表のお知らせを削除します。 この設定によって、割り当てられていない番号への通話を処理する方法が影響を受けます。
ms.openlocfilehash: 63d64bb09c24609ebb05c6de879bd1fe0e92d093
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887396"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>作成またはビジネス サーバーの Skype でお知らせを削除します。

作成またはビジネス サーバーのエンタープライズ VoIP の Skype のアプリケーションを発表のお知らせを削除します。 これは、割り当てられていない番号への通話の処理方法に影響します。

アナウンスを構成した場合、実際にはそれは割り当てられていない番号への通話の処理方法を構成することになります。オーディオ ファイルまたは音声合成 (TTS) ファイルによる音声ガイダンスを再生するか、または音声ガイダンスを再生することなく、ただ指定した宛先へ呼び出しを転送することもできます。

割り当てられていない番号の表を定義する前に、アナウンスを作成する必要があります。音声ガイダンスまたは TTS による音声ガイダンスを使用するアナウンスすべて、または音声ガイダンスなしのアナウンスすべてに対して、このステップを実行する必要があります。

ここでは、アナウンスをインポートおよび作成する方法について説明します。 表には、未使用の番号のお知らせの割り当ての詳細については、[割り当てられていない番号テーブルの設定](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)を参照してください。

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>割り当てられていない番号向けに新しいアナウンスを作成するには

新しいアナウンスを作成するには、次のステップを実行する必要があります。

1. 音声ガイダンスの場合は、好みのオーディオ録音アプリケーションを使用してオーディオ ファイルを録音します。

2. オーディオ プロンプトは、音声ファイルの内容をファイル ストアにインポートする**インポート CsAnnouncementFile**コマンドレットを実行します。

3. お知らせの名前を作成する**新規 CsAnnouncement**コマンドレットを実行します。 このステップを実行して、音声ガイダンス、音声合成 (TTS) による音声ガイダンス、または音声ガイダンスなしのアナウンスを作成します。

    > [!TIP]
    > たとえば、メッセージを再生することなく、指定した宛先へ呼び出しを転送する場合は、音声ガイダンスなしのアナウンスを作成できます。

4. 新しいアナウンスを、割り当てられていない番号の表の番号範囲に割り当てます。

### <a name="to-create-a-new-announcement"></a>新しいアナウンスを作成するには

1. 音声ガイダンスの場合は、オーディオ ファイルを作成します。

2. RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。

3. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

4. 音声ガイダンスの場合は、次のように実行します。

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. 次のコマンドレットを実行します。

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    呼び出しをボイス メールに転送する場合は、sip:username@domainname;opaque=app:voicemail の形式で SIPAddress を入力します (たとえば、sip:bob@contoso.com;opaque=app:voicemail)。呼び出しを電話番号に転送する場合は、sip:number@domainname;user=phone の形式で SIPAddress を入力します (たとえば、sip:+ 14255550121@contoso.com;user=phone)。

    たとえば、音声ガイダンスを指定するには、次の形式を使用します。

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    たとえば、TTS によるガイダンスを指定するには、次の形式を使用します。

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

  **TextToSpeechPrompt**パラメーターで使用する言語コードの一覧を表示してこれらのコマンドレットについての詳細については、[新規 CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)を参照してください。

## <a name="delete-an-announcement-for-unassigned-numbers"></a>割り当てられていない番号のアナウンスの削除

### <a name="to-delete-an-announcement"></a>アナウンスを削除するには

1. RTCUniversalServerAdmins グループのまたは**セットアップ アクセス許可の委任**で説明したように必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。

2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。

3. 組織のすべてのアナウンスの一覧を取得します。コマンド ラインで次のコマンドを実行します。

   ```
   Get-CsAnnouncement
   ```

4. 表示された一覧で、削除するアナウンスを見つけて、その GUID をコピーします。次に、コマンド ラインで次のコマンドを実行します。

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    例:

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > 詳細オプションの詳細については、 [Get CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)と[削除 CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)を参照してください。

## <a name="see-also"></a>関連項目

[作成またはビジネス サーバーの Skype でお知らせを削除します。](create-an-announcement.md)

[インポート-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[新しい-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[削除 CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

