---
title: Microsoft Teams で組織の電話会議の設定を管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ダイヤルイン電話会議ライセンスと会議 ID をユーザーおよびその他の多くのダイヤルイン電話会議の設定に割り当てるための Microsoft Teams での手順を確認します。 '
ms.openlocfilehash: 7cb0e76771563305ce98445818c77364b0849845
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "37570577"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織の電話会議の設定を管理する

1 つの場所で Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>電話会議のライセンスを割り当てる

> [!NOTE]
> Teams を使用してライセンスを割り当てることはできません。 Microsoft 365 管理センターを使用する必要があります。 [Skype for Business と Microsoft Teams のライセンスを割り当てる](assign-teams-licenses.md)を参照してください。 
  
 **ユーザーにライセンスを割り当てる**
  
1. 職場または学校のアカウントを使用して、Microsoft 365 にサインインします。
    
2. **Microsoft 365 管理センター**の左のナビゲーションで、[**ユーザー** > の**アクティブな**ユーザー] に移動し、利用可能なユーザーのリストからユーザー (複数可) を選びます。
    
    > [!NOTE]
    > 操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。 次に [**編集**]、[**次へ**] を 2 回クリックしてからライセンスを選択し、[**送信**] をクリックします。  
  
3. 操作ウィンドウの [**製品ライセンス**] で [ **編集**] をクリックします。 
    
4. [**製品ライセンス**] ページで、[**電話会議**] を有効にし、[**保存**] をクリックします。ライセンスの詳細については、「[Microsoft Teams アドオン ライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。
    
> [!NOTE]
> ライセンスを割り当てた後は、リストの最初の電話会議プロバイダーとして Microsoft が表示されない可能性があります。この問題が発生した場合は、管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーウィンドウを更新してください。 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>電話会議ユーザーに送信されたメールを有効または無効にする

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. **[保存]** をクリックします。

    
**Windows PowerShell を使用する**
  
詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。
  
## <a name="reset-the-meeting-conference-id"></a>会議通話 ID をリセットする

![](media/teams-logo-30x30.png) **Microsoft teams 管理センターを使用し**た Teams のロゴを示すアイコン

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] で [**会議通話 ID のリセット**] をクリックします。  

3. [**会議通話 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。 ユーザーに電子メールを送信することが有効になっている場合、会議通話 ID は自動的に作成され、新しい会議通話 ID が記載された電子メールがユーザーに送信されます。 これは既定では有効になっています。

「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。
  
## <a name="reset-a-conference-organizers-pin"></a>会議通話の開催者の PIN をリセットする

ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。 会議通話 ID は自動的に作成されユーザーに割り当てられますが、ユーザーは使わないため特定の番号に設定しようと考える場合や、ユーザーが会議通話 ID を覚えられない、または紛失してしまう場合があります。 

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] で、[**PIN のリセット**] をクリックしてから [**リセット**] をクリックします。 
  
ユーザーは、電話会議の PIN が有効になっているか、PIN が再設定されている場合、自分の PIN を使ってメールを受け取れます。しかし、自動で送信するメールが無効になっている場合、 PIN リセットのメールは送信されませんので、手動でユーザーに前述の PIN を送信する必要があります。 PIN が再設定されるとその PIN は一度だけ表示されます。再設定された直後に表示された後、その PIN はユーザーのプロパティ上に表示されることはなく、その代わりに ***** と表示されます。 
  
「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が記載された電子メールをユーザーに送信する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。 

    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。 

「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。
  
## <a name="set-the-phone-numbers-included-on-invites"></a>招待状に含まれている電話番号を設定する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] の横の [**編集**] をクリックします。
 
3. [**電話会議**] ウィンドウで、[**有料電話番号**] と、可能な場合は [**フリーダイヤル番号**] を設定できます。

4. [**保存**] をクリックします。
    
「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照してください。
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>電話会議ブリッジの設定を選択する

**発信者が会議に参加するときの会議エクスペリエンスを設定する**

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。

    これは既定では有効になっています。 このオプションを無効にすると、既定ですでに会議に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。

4. [**開始/終了のお知らせの種類**] で、[**トーン**] または [**名前または電話番号**] のどちらかを選びます。 

    [**名前または電話番号**] を選ぶと、[**発信者に会議に参加する前に自分の名前を記録するように要求する**] を有効または無効にすることもできます。 

5. [**保存**] をクリックします。

    
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。
  
 **会議の PIN の長さを設定する**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ウィンドウで、[**PIN の長さ**] リストに PIN の桁数を入力し、[**保存**] をクリックします。

    PIN は 4 桁から 12 桁の間の値にする必要があります。既定値は 5 桁です。

    
職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **電話会議 ユーザーに送信されているメールを有効または無効にする**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ペインで、[**電話会議設定を変更した場合ユーザーに自動的に電子メールを送信する**] を有効または無効にします。

4. [**保存**] をクリックします。 
 
    電話会議設定をメールでユーザーに送ることもできます。その場合は、ユーザーの電話会議プロパティに移動して、[**電話会議情報を電子メールで送信する**] をクリックします。
    
    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。

「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示、設定する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. リストから電話番号を選択し、[**編集**] をクリックします。

3. [**既定の言語**] と [**代替言語 (オプション)**] で必要な言語を選びます。

4. [**保存**] をクリックします。


[電話会議の自動案内の言語を設定する](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)を参照してください。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>電話会議のダイヤルイン番号を確認する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. リストから電話番号を選択し、[**編集**] をクリックします。 ここでは、
    
   - 電話会議で使うために Office 365 によって設定された電話番号を表示する。 
    
   - 場所や、電話会議の自動応答で使用する第 1 言語を表示できます。

  
「[電話会議の電話番号のリストを表示する](see-a-list-of-audio-conferencing-numbers-in-teams.md)」を参照してください。
  

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
    
## <a name="related-topics"></a>関連トピック

[ユーザーの電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


