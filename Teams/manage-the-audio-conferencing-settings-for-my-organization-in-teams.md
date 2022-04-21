---
title: 電話会議の設定を管理する
ms.author: heidip
author: MicrosoftHeidi
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
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'ダイヤルイン電話会議ライセンスと会議 ID をユーザーおよびその他の多くのダイヤルイン電話会議の設定に割り当てるための Microsoft Teams での手順を確認します。 '
ms.openlocfilehash: e9a464df1d4c3eb01815a652b2e55c6c269b837d
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016619"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Microsoft Teams で組織の電話会議の設定を管理する

1 つの場所で Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="assign-an-audio-conferencing-license"></a>電話会議のライセンスを割り当てる

> [!NOTE]
> Teams を使用してライセンスを割り当てることはできません。 Microsoft 365 管理センターを使用する必要があります。 [アドオン ライセンスMicrosoft Teams割り当てるに関するページを](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)参照してください。

### <a name="to-assign-a-license-for-a-user"></a>ユーザーにライセンスを割り当てる

1. 職場または学校のアカウントを使用して、Microsoft 365 にサインインします。

2. **Microsoft 365 管理センター** の左側のナビゲーションで、**UsersActive** >  ユーザーに移動し、使用可能 **なユーザー** の一覧からユーザーまたはユーザーを選択します。

    > [!NOTE]
    > 操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。 次に [**編集**]、[**次へ**] を 2 回クリックしてからライセンスを選択し、[**送信**] をクリックします。  
  
3. 操作ウィンドウの [**製品ライセンス**] で [ **編集**] をクリックします。

4. [**製品ライセンス**] ページで、[**電話会議**] を有効にし、[**保存**] をクリックします。ライセンスの詳細については、「[Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

   > [!NOTE]
   > ライセンスを割り当てた後、Microsoft は最初に電話会議プロバイダーとして一覧に表示されない可能性があります。 このような場合は、管理センターからログアウトするか、Ctrl キーを押しながら F5 キーを押してブラウザー ウィンドウを更新します。
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>電話会議ユーザーに送信されたメールを有効または無効にする

### <a name="enable-or-disable-using-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターを使用して有効または無効にする

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. **[保存]** をクリックします。

### <a name="enable-or-disable-using-windows-powershell"></a>Windows PowerShellを使用して有効または無効にする

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。
  
## <a name="reset-the-meeting-conference-id"></a>会議通話 ID をリセットする

### <a name="reset-the-meeting-conference-id-using-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターを使用して会議会議 ID をリセットする

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] で [**会議通話 ID のリセット**] をクリックします。  

3. [**会議通話 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。 ユーザーに電子メールを送信することが有効になっている場合、会議通話 ID は自動的に作成され、新しい会議通話 ID が記載された電子メールがユーザーに送信されます。 これは既定では有効になっています。

「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。

## <a name="reset-a-conference-organizers-pin"></a>会議通話の開催者の PIN をリセットする

ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。 会議通話 ID は自動的に作成されユーザーに割り当てられますが、ユーザーは使わないため特定の番号に設定しようと考える場合や、ユーザーが会議通話 ID を覚えられない、または紛失してしまう場合があります。

### <a name="reset-a-conference-organizers-pin-using-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターを使用して会議開催者の PIN をリセットする

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] で、[**PIN のリセット**] をクリックしてから [**リセット**] をクリックします。
  
ユーザーは、電話会議の PIN が有効になっているか、PIN が再設定されている場合、自分の PIN を使ってメールを受け取れます。しかし、自動で送信するメールが無効になっている場合、 PIN リセットのメールは送信されませんので、手動でユーザーに前述の PIN を送信する必要があります。 PIN が再設定されるとその PIN は一度だけ表示されます。再設定された直後に表示された後、その PIN はユーザーのプロパティ上に表示されることはなく、その代わりに ***** と表示されます。
  
「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が記載された電子メールをユーザーに送信する

### <a name="send-an-email-using-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターを使用してメールを送信する

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。

    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。

「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。
  
## <a name="set-the-phone-numbers-included-on-invites"></a>招待状に含まれている電話番号を設定する

### <a name="set-invite-phone-numbers-using-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターを使用して招待電話番号を設定する

「[Microsoft Teamsの招待に含まれる電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照してください。

> [!NOTE]
> *TeamsAudioconferencingpolicy* に電話番号を追加し、ポリシーをユーザーに割り当てることで電話番号を設定することもできます。 ポリシーに追加された有料電話番号とフリーダイヤル電話番号は、電話会議設定ウィンドウでユーザーに対して個別に設定された電話番号よりも優先されます。 *Teamsaudioconferencingpolicy* に電話番号が追加されていない場合は、電話会議の設定ウィンドウでユーザーに個別に設定された電話番号が会議出席依頼Microsoft Teamsに表示されます。 [有料電話番号とフリーダイヤル番号の電話会議ポリシー設定](audio-conferencing-toll-free-numbers-policy.md) の詳細については、以下をご覧ください。

## <a name="choose-audio-conferencing-bridge-settings"></a>電話会議ブリッジの設定を選択する

### <a name="set-the-meeting-experience-when-callers-join-a-meeting-using-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターを使用して、発信者が会議に参加するときに会議エクスペリエンスを設定する

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

3. [**ブリッジの設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。

    これは既定では有効になっています。 このオプションを無効にすると、既定ですでに会議に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。

4. [**開始/終了のお知らせの種類**] で、[**トーン**] または [**名前または電話番号**] のどちらかを選びます。

    [**名前または電話番号**] を選ぶと、[**発信者に会議に参加する前に自分の名前を記録するように要求する**] を有効または無効にすることもできます。
    > [!NOTE]
    > 既定では、外部ユーザーはダイヤルインした参加者の電話番号を見ることができません。これらの電話番号のプライバシーを維持したい場合は、**入場/退出のお知らせの種類** として **トーン** を選択します (これにより、番号は Teams によって読み取られません)。
5. [**保存**] をクリックします。

[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。
  
### <a name="set-the-pin-length-for-meetings"></a>会議の PIN の長さを設定する

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

3. [**ブリッジの設定**] ウィンドウで、[**PIN の長さ**] リストに PIN の桁数を入力し、[**保存**] をクリックします。

    PIN は 4 桁から 12 桁の間の値にする必要があります。既定値は 5 桁です。

職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="enable-or-disable-email-from-being-sent-to-audio-users"></a>電話会議 ユーザーに送信されているメールを有効または無効にする

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

3. [**ブリッジの設定**] ペインで、[**電話会議設定を変更した場合ユーザーに自動的に電子メールを送信する**] を有効または無効にします。

4. [**保存**] をクリックします。

    電話会議設定をメールでユーザーに送ることもできます。その場合は、ユーザーの電話会議プロパティに移動して、[**電話会議情報を電子メールで送信する**] をクリックします。

    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。

「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示、設定する

### <a name="see-primary-and-secondary-languages-using-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターを使用してプライマリ言語と第 2 言語を表示する

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. リストから電話番号を選択し、[**編集**] をクリックします。

3. [**既定の言語**] と [**代替言語 (オプション)**] で必要な言語を選びます。

4. [**保存**] をクリックします。

[電話会議の自動案内の言語を設定する](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)を参照してください。
  
## <a name="see-audio-conferencing-dial-in-numbers-using-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターを使用した電話会議ダイヤルイン番号の表示

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. リストから電話番号を選択し、[**編集**] をクリックします。 ここでは、

   - 電話会議に使用する電話番号を表示します。

   - 場所や、電話会議の自動応答で使用する第 1 言語を表示できます。

「[電話会議の電話番号のリストを表示する](see-a-list-of-audio-conferencing-numbers-in-teams.md)」を参照してください。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあります。Windows PowerShell があれば、一元管理を使用して Microsoft 365 または Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。

- [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Microsoft 365 または Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。

## <a name="related-topics"></a>関連トピック

[ユーザーの電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)
