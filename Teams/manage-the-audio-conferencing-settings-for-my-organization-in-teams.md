---
title: Microsoft Teams で組織の電話会議の設定を管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ダイヤルイン電話会議ライセンスと会議 ID をユーザーおよびその他の多くのダイヤルイン電話会議の設定に割り当てるための Microsoft Teams での手順を確認します。 '
ms.openlocfilehash: 7af89da74b0b83872954444a847d40f0d7851087
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884706"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>Microsoft Teams で組織の電話会議の設定を管理する

1 つの場所で Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>電話会議のライセンスを割り当てる

> [!NOTE]
> Teams を使用してライセンスを割り当てることはできません。 Office 365 管理センターを使用する必要があります。 In the left navigation of the Office 365 admin center, go to UsersActive users > and then select the user or users from the list of available users. 
  
 最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ 編集]、[ 次へ] を 2 回クリックし、ライセンスを選択して、[ 送信] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「Skype for Business と Microsoft Teams のライセンスを割り当てる」をご覧ください。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. 次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。****
    
    > [!NOTE]
    > 操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。 次に [**編集**]、[**次へ**] を 2 回クリックしてからライセンスを選択し、[**送信**] をクリックします。  
  
3. 操作ウィンドウの [**製品ライセンス**] で [ **編集**] をクリックします。 
    
4. ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。この場合は、Office 365 管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーのウィンドウを更新します。
    
> [!NOTE]
> ユーザーに会議 ID を割り当てる 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>電話会議ユーザーに送信されたメールを有効または無効にする

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams と Skype for Business 管理センターを使用する: **

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. [**保存**] をクリックします。

    
**Windows PowerShell を使用する**
  
詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>ユーザーに送信された、送信者のメール メッセージ内の連絡先情報を変更する

Change the senders contact information of email messages sent to users 既定では、メールの送信者は Office 365 ですが、Windows PowerShell を使用してメール アドレスと表示名を変更することができます。 詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。
  
## <a name="reset-the-meeting-conference-id"></a>会議 ID をリセットする

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の下で、[**会議 ID のリセット**] をクリックします。  

4. [**会議 ID をリセットしますか?**] ウィンドウで、[**リセット**] をクリックします。 It's enabled by default. これは既定では有効になっています。

「[ユーザーのために会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」をご覧ください。
  
## <a name="reset-a-conference-organizers-pin"></a>電話会議の開催者の PIN をリセットする

ユーザーがスケジュール設定した各会議には、一意の会議 ID が割り当てられます。 会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。 

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の下で、[**PIN のリセット**] をクリックしてから、[**リセット**] をクリックします。 
  
    
リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "*****" が表示されます。 
  
「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」をご覧ください。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が記載されたメールをユーザーに送信する

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。 

    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。 

  
「[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」をご覧ください。
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>招待状に含まれている電話番号を設定する

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] の隣で、[**編集**] をクリックします。
 
3. [**電話会議**] ウィンドウで、[**有料電話番号**] と、可能な場合は [**フリーダイヤル番号**] を設定することができます。

4. [**保存**] をクリックします。
    
「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」をご覧ください。
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>電話会議ブリッジの設定を選ぶ

**発信者が会議に参加するときの会議エクスペリエンスを設定する**


1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジ設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。

    これは既定では有効になっています。 このオプションを無効にすると、既定ですでに参加済みのユーザーは、誰かが入ってきたり退出したりしたときの通知を受け取りません。

4. [**開始/終了のお知らせの種類**] で、[**トーン**] または [**名前または電話番号**] のどちらかを選びます。 

    [**名前または電話番号**] を選ぶと、[**発信者に、会議に参加する前に自分の名前を記録するように要求します**] を有効または無効にすることもできます。 

5. [**保存**] をクリックします。

    
[](change-the-settings-for-an-audio-conferencing-bridge.md)職場または学校のアカウントを使用して、Office 365 にサインインします。
  
 **会議の PIN の長さサイズを設定する**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ウィンドウで、[**PIN の長さ**] リストに PIN の桁数を入力し、[**保存**] をクリックします。

    PIN は 4 桁から 12 桁の間の値にする必要があります。既定値は 5 桁です。

    
職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **電話会議ユーザーに送信されているメールを有効または無効にする**


1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ペインで、[**電話会議設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. [**保存**] をクリックします。 
 
    電話会議設定をメールでユーザーに送ることもできます。その場合は、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。
    
    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。

「[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」をご覧ください。
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示および設定する

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. リストから電話番号を選択し、[**編集**] をクリックします。

3. [**既定の言語**] と [**代替言語 (オプション)**] で必要な言語を選びます。


「[電話会議の自動案内の言語を設定する](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)」をご覧ください。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>電話会議のダイヤルイン番号を確認する


1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. リストから電話番号を選択し、[**編集**] をクリックします。 ここでは次の操作を行うことができます。
    
  - 電話会議で使うために Office 365 によって設定された電話番号を表示する。 
    
  - 場所や、電話会議の自動応答で使用する第 1 言語を表示する。

  
「[電話会議の電話番号のリストを表示する](see-a-list-of-audio-conferencing-numbers-in-teams.md)」をご覧ください。
  

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
    
## <a name="related-topics"></a>関連トピック

[ユーザーの電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


