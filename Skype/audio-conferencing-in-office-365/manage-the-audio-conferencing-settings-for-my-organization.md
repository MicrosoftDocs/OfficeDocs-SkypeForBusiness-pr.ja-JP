---
title: "組織の電話会議の設定を管理する"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
description: "See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. "
---

# 組織の電話会議の設定を管理する

1 つの場所で Skype for Business と Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。
  
## 電話会議のライセンスを割り当てる

> [!NOTE]
> [ **Skype for Business 管理センター**] を使用してライセンスを割り当てることはできませんので、Office 365 管理センターを使用する必要があります。詳細については、「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。 
  
 **ユーザーにライセンスを割り当てるには**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**の左のナビゲーションで、[ **ユーザー**]、[ **アクティブなユーザー**] の順に移動し、利用可能なユーザーのリストからユーザー (複数可) を選びます。
    
    > [!NOTE]
    > 最大 20 人までのライセンスを同時に割り当てている場合は、[ **ビューの選択**] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[ **送信**] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。 
  
3. 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。
    
4. [ **製品ライセンス**] ページで [ **電話会議**] をオンにして、[ **保存**] をクリックします。ライセンスの詳細については、「[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。
    
> [!NOTE]
> ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。この場合は、Office 365 管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーのウィンドウを更新します。 
  
## ユーザーに会議 ID を割り当てる

Microsoft を電話会議プロバイダーとして使用してユーザーを電話会議に対してセットアップすると、自動的に会議 ID がユーザーに割り当てられます。割り当てられた 会議 ID は、静的または動的 ID で、会議がスケジュール設定されると会議出席依頼で送信されます。
  
静的 ID は、組織内のユーザーがランダムな番号を覚えるのを望まないときや、ユーザーが特定の番号を選択できる場合や、覚えやすい番号を取得している場合に好んで使用されます。動的会議 ID が使用される場合、ユーザーがスケジュールするそれぞれの会議に一意の会議 ID が割り当てられます。静的ではなく動的な会議 ID を割り当てる場合は、[組織での電話会議の動的 ID の使用](using-audio-conferencing-dynamic-ids-in-your-organization.md)をご覧ください。
  
Skype for Business 管理センターを使ってユーザーに会議 ID を割り当てることはできませんが、Windows PowerShell コマンドレットを使えばこの操作を行うことができます。
  
ユーザーの会議 ID を設定するには、次のコマンドレットを実行します。
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> 会議 ID には 7 桁の情報を含める必要があります。Skype for Business 管理センターにおいて、または Windows PowerShell を使用して、この情報を変更することはできません。 
  
このコマンドレットの詳細については、「[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )」をご覧ください。
  
> [!IMPORTANT]
>  新しい電話会議 ID が作成されると、古い電話会議 ID を使用してダイヤルインすることはできなくなります。既存の会議の招待を予約し直して、新しい電話会議 ID を招待に追加するように、ユーザーに通知してください。ユーザーは Skype for Business の会議移行ツールを使って、既存の会議を更新できます。Skype for Business Meeting Update Tool をダウンロード、インストール、実行する方法については、以下をご覧ください。> [Skype for Business Meeting Update Tool と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online、会議移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online、会議移行ツール (32 ビット)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
「[ユーザーに割り当てられている会議 ID を表示、変更、リセットする](see-change-and-reset-a-conference-id-assigned-to-a-user.md)」をご覧ください。
  
## 電話会議プロバイダーを Microsoft からサードパーティー プロバイダーに変更する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. [ **Skype for Business 管理センター**]の左のナビゲーションで [ **電話会議**]、[ **ユーザー**] の順に移動し、電話会議プロバイダーを変更するユーザーを選びます。
    
4. 操作ウィンドウで、[ **編集**] をクリックします。
    
5. [ **プロパティ**] ページの [ **プロバイダー名**] で、ユーザーの電話会議プロバイダーを選びます。
    
    > [!NOTE]
    > 複数のユーザーを選んだ場合は、電話会議プロバイダーとして Microsoft を選ぶか、[ **なし**] を選ぶことしかできません。 
  
6. [ **保存**] をクリックします。
    
「[ユーザーのダイヤルイン会議プロバイダーを変更する](https://support.office.com/article/9b74f053-4d23-485f-9232-3d30370a8c6e)」をご覧ください。
  
## 電話会議ユーザーへのメール送信を有効または無効にする

Skype for Business 管理センターまたは Windows PowerShell を使用すると、ユーザーへのメール送信を有効または無効にすることができます。
  
 **Skype for Business 管理センターを使用する**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動して、左のナビゲーションで [ **電話会議**] をクリックします。
    
3. [ **Microsoft Bridge の設定**] ページで、[ **ユーザーの電話会議設定が変更されると、メールがユーザーに自動送信されます**] をオンまたはオフにします。
    
4. [ **保存**] をクリックします。
    
    ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。会議 ID と電話会議用の既定の電話番号は会議出席依頼に記載されていますが、PIN は記載されていません。
    
    「[ユーザーにダイヤルイン会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-audio-conferencing-information.md)」をご覧ください。
    
 **Windows PowerShell を使用する**
  
- Windows PowerShell を使用して、次を実行することもできます。
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) を使って、組織のメールを含むその他の設定を管理できます。
    
## ユーザーに送信されるメール メッセージの、差出人の連絡先情報を変更する

実際のメール アドレスや、差出人の連絡先情報の表示名など、ユーザーに自動的に送信されるメールの内容を変更できます。既定では、メールの差出人は Office 365 ですが、Windows PowerShell と[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) コマンドレットを使って、メール アドレスと表示名を変更できます。ユーザーにメールを送信するためのメール アドレスを変更するには、次の操作を実行する必要があります。
  
-  _SendEmailFromAddress_ パラメーターにメール アドレスを入力する
    
-  _SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する
    
-  _SendEmailOverride_ パラメーターを _True_ に設定する
    
メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。
  
[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) コマンドレットを使って、組織のメールを含むその他の設定を管理できます。
  
「[ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md)」を参照してください。
  
## 会議 ID をリセットする

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. [ **Skype for Business 管理センター**] の左側のナビゲーションで、[ **電話会議**] に移動し、操作ウィンドウの [ **会議 ID**] の下で [ **リセット**] をクリックします。
    
4. [ **電話会議 ID をリセットしますか?**] ウィンドウで、[ **はい**] をクリックします。会議 ID が自動的に作成され、ユーザーへのメール送信が有効になっている場合 (既定の設定では有効) は、新しい会議 ID を記載したメールがユーザーに送信されます。
    
    > [!IMPORTANT]
    >  新しい電話会議 ID が作成されると、古い電話会議 ID を使用してダイヤルインすることはできなくなります。既存の会議の招待を予約し直して、新しい電話会議 ID を招待に追加するように、ユーザーに通知してください。ユーザーは Skype for Business の会議移行ツールを使って、既存の会議を更新できます。Skype for Business Meeting Update Tool をダウンロード、インストール、実行する方法については、以下をご覧ください。> [Skype for Business Meeting Update Tool と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online、会議移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online、会議移行ツール (32 ビット)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
「[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)」をご覧ください。
  
## 会議開催者の PIN をリセットする

静的 ID は、組織内のユーザーがランダムな番号を覚えるのを望まないときや、ユーザーが特定の番号を選択できる場合や、覚えやすい番号を使用している場合に好んで使用されます。動的会議 ID が使用される場合、ユーザーがスケジュールするそれぞれの会議に一意の会議 ID が割り当てられます。動的な、静的でない会議 ID を割り当てる場合は、[組織での電話会議の動的 ID の使用](using-audio-conferencing-dynamic-ids-in-your-organization.md)をご覧ください。
  
静的会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。Skype for Business 管理センターおよび Windows PowerShell を使用すると、ユーザーの会議 ID を表示、変更、リセットすることができます。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動して、左のナビゲーションで [ **電話会議**] をクリックします。
    
3. [ **ユーザー**] をクリックし、PIN をリセットするユーザーを選びます。
    
4. 操作ウィンドウの [ **PIN**] で [ **リセット**] をクリックします。
    
ユーザーが電話会議で有効になるか、PIN がリセットされた場合、ユーザーは自分の PIN が含まれるメールを受信します。ただし、メールの自動送信を無効にしても、PIN リセットのメールは送信されません。管理者は、ユーザーに PIN を手動で送信する必要があります。PIN をリセットした後、PIN が表示されるのは 1 回だけです。リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "*****" が表示されます。
  
「[ユーザーのダイヤルイン会議の PIN をリセットする](reset-the-audio-conferencing-pin-for-a-user.md)」をご覧ください。
  
## 電話会議の情報が記載されたメールをユーザーに送信する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動して、左のナビゲーションで [ **電話会議**] をクリックします。
    
3. [ **ユーザー**] をクリックし、PIN をリセットするユーザーを選びます。
    
4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。
    
    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。 
  
「[ユーザーにダイヤルイン会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-audio-conferencing-information.md)」をご覧ください。
  
## 会議開催者に対して電話会議用の既定の電話番号を設定する

 **電話会議のユーザーを有効にする場合に、会議開催者に対して電話会議用の既定の電話番号を設定するには**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. 左のナビゲーションで、[ **電話会議**]、[ **ユーザー**] の順に移動します。電話会議を有効にするユーザーを選びます。
    
4. [操作] ウィンドウのユーザー プロパティで、[ **編集**] をクリックします。
    
5. [ **プロパティ**] ページの [ **プロバイダー名**] で、ドロップダウン リストから電話会議プロバイダーを選びます。
    
  - 電話会議プロバイダーに Microsoft を選ぶ場合は、電話会議の既定の電話番号を一覧から選ぶことができます。
    
  - 電話会議プロバイダーにサードパーティーの ACP を選ぶ場合は、有料の電話番号 (または必要に応じてフリーダイヤルの電話番号) を手動で入力する必要があります。これらの電話番号は、既定の電話番号に設定されます。
    
    ユーザーの電話会議用の既定の電話番号は、ユーザーが会議をスケジュールしたときに会議出席依頼に表示される番号です。
    
6. [ **保存**] をクリックします。
    
「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」をご覧ください。
  
 **電話会議のユーザーを有効にした後に、会議開催者に対して電話会議用の既定の電話番号を設定するには**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. [ **Skype for Business 管理センター**] の左のナビゲーションで、[ **電話会議**]、[ **ユーザー**] の順に移動して、ユーザーを選び、[操作] ページで [ **編集**] をクリックします。
    
4. [ **プロパティ**] ページの [ **プロバイダー名**] で、ドロップダウン リストから電話会議プロバイダーを選びます。
    
  - ユーザーが電話会議プロバイダーとして Microsoft を使用する場合は、電話会議の既定の電話番号を一覧から選ぶことができます。
    
  - 電話会議プロバイダーにサードパーティーの ACP を使う場合は、有料の電話番号 (または必要に応じてフリーダイヤルの電話番号) を手動で入力する必要があります。
    
    ユーザーの電話会議用の既定の電話番号は、ユーザーが会議をスケジュールしたときに会議出席依頼に表示される番号です。
    
5. [ **保存**] をクリックします。
    
「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」をご覧ください。
  
## 電話会議ブリッジを設定する

 **発信者が会議に参加するときの会議の動作を設定する**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]** の左のナビゲーションで、[ **電話会議**]、[ **Microsoft Bridge の設定**] の順に移動します。
    
4. [ **会議参加エクスペリエンス**] で次の操作を選びます。
    
  - [ **会議の入退出の通知をオンにする**]: 既定ではオンになっています。オフにすると、会議に既定で参加済みのユーザーは、別のユーザーが会議に入退室したことを通知されなくなります。
    
    ユーザーが Skype for Business クライアントを使用して会議に参加し、その会議の Skype 会議または Microsoft Teams の [ **オプション**] メニューで [ **ユーザーの入退室を通知**] 設定を変更すると、この動作を会議ごとに設定することができます。
    
  - [ **発信者に、会議に参加する前に自分の名前を記録するように要求**]: 既定ではオンになっています。オフにすると、発信者は会議に参加する前に名前を記録するように依頼されません。
    
5. 変更したら [ **保存**] をクリックします。
    
「[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)」をご覧ください。
  
 **会議の PIN の長さを設定する**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]** の左のナビゲーションで、[ **電話会議**]、[ **Microsoft Bridge の設定**] の順に移動します。
    
4. [ **セキュリティ**] で、PIN に対する数字の桁数を [ **PIN の長さ**] リストに入力してから、[ **保存**] をクリックします。
    
    PIN の桁数は 4 から 12 の間にする必要があります。既定値は 5 です。
    
「[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)」をご覧ください。
  
 **電話会議ユーザーへのメール送信を有効または無効にする**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動して、左のナビゲーションで [ **電話会議**] をクリックします。
    
3. [ **Microsoft Bridge の設定**] ページで、[ **ユーザーの電話会議設定が変更されると、メールがユーザーに自動送信されます**] をオンまたはオフにします。
    
4. [ **保存**] をクリックします。
    
    電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。
    
    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。
    
    「[ユーザーにダイヤルイン会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-audio-conferencing-information.md)」をご覧ください。
    
## 電話会議ブリッジのプライマリ言語とセカンダリ言語を表示および設定する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]** の左のナビゲーションで [ **電話会議**] に移動し、[ **Microsoft Bridge**] をクリックします。
    
4. リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。
    
    Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。
    
「[電話会議の自動案内の言語を設定する](set-auto-attendant-languages-for-audio-conferencing.md)」をご覧ください。
  
## 「電話会議のダイヤルイン番号」をご覧ください

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]** の左のナビゲーションで、[ **電話会議**]、[ **Microsoft Bridge の設定**] の順に移動します。次のことを実行できます。
    
  - 電話会議で使うために Office 365 によって設定された電話番号を表示する。
    
  - 場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。
    
  - ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。
    
[ **電話会議**]、[ **ユーザー**] の順に移動して、ユーザーのプロパティを選び、組織で使用可能な電話番号の一覧から新しい番号を選んで、ユーザー用の既定の電話番号を変更します。
  
「[ダイヤルイン会議のダイヤルイン番号のリストを表示する](see-a-list-of-audio-conferencing-numbers.md)」をご覧ください。
  
## 有効になっているユーザーのリストを表示する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]**の左のナビゲーションで [ **電話会議**]、[ **ユーザー**] の順に移動します。
    
「[ダイヤルイン会議用に有効になっているユーザーのリストを表示する](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)」をご覧ください。
  
## Windows PowerShell で管理する方法

- Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。このため、簡単にこれらの設定をすべてのユーザーに適用できます。組織レベルの設定を以下に示します。
    
    各コマンドレットに関するその他のヘルプ情報を入手するには、「[Skype for Business Online のコマンドレット](https://go.microsoft.com/fwlink/?LinkId=627324)」をご覧ください。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

    既定値は  _$true_ です。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

    既定値は  _$true_ です。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

    既定値は 5 です。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

    既定値は  _$false_ です。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    既定値は  _$true_ です。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

    既定値は  _$false_ です。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

    既定値は  _$null_ です。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

    既定値は  _$null_ です。
    
- Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
    
## 関連項目

#### 

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

