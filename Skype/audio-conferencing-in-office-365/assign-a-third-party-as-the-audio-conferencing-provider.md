---
title: "サードパーティを電話会議プロバイダーとして割り当てる"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
description: "Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. "
---

# サードパーティを電話会議プロバイダーとして割り当てる

電話会議プロバイダーは *会議ブリッジ*  を供給します。この会議ブリッジは、作成される会議のダイヤルイン電話番号、PIN、および会議 ID を提供します。必要なのは、電話会議プロバイダーを Skype for Business 会議または Microsoft Teams 会議をスケジュールまたは開催しようとしている人に割り当てることだけです。
  
> [!NOTE]
> Microsoft Teams の場合、ユーザーはサードパーティーの電話会議プロバイダーを使用できません。電話会議プロバイダーが Microsoft に設定される Office 365 の電話会議を使用する必要があります。 
  
## サードパーティーの電話会議プロバイダーを割り当てる前に実行する手順

1. ご利用の Office 365 プランに応じて、組織内で電話会議を使用する Skype for Business 会議または Microsoft Teams 会議をスケジュールまたは開催しようとしているユーザーのために **電話会議**アドオンライセンスを購入する必要がある場合があります。詳細については、「[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」ご覧ください。
    
2. **電話会議**アドオン ライセンスを購入した場合、それらのライセンスを組織内で電話会議を使用する会議をスケジュールまたは開催しようとしている人に割り当てます。詳細については「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。
    
    > [!NOTE]
    > **電話会議**ライセンスをサードパーティーの電話会議プロバイダーに割り当てた **後に** 、任意のユーザーに割り当てる場合、そのユーザーは自動的に Microsoft を電話会議プロバイダーとして使用するように設定されます。このような場合は、サードパーティーの電話会議プロバイダーを割り当てる前に、Microsoft を電話会議プロバイダーとして削除する必要があります。
  
3. サードパーティーの電話会議プロバイダーは、[Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530) で見つけてください。セットアップ方法については、これらのプロバイダーに連絡して確認してください。
    
    サードパーティーのダイヤルイン会議プロバイダーから以下の情報が提供されます。
    
  - **ダイヤルイン番号 (有料)** とフリーダイヤルの番号 (提供されている場合)。
    
  - **会議 Id。これは会議をスケジュールする各ユーザーが使用します。一部の** 。これは会議をスケジュールする各ユーザーで使用されます。一部の ACP では、これらのパスコードが要求されます。
    
    > [!NOTE]
    > サードパーティー ACP の初回のセットアップを完了したが変更する必要が生じた場合には、[ **Microsoft Bridge**] ページの下部で **ここをクリックしてサードパーティーの音声会議プロバイダーを構成してください**。 
  
    > [!NOTE]
    > ある人を電話会議に対して有効にして、サードパーティーの電話会議プロバイダーを割り当てると、音声会議と会議の ID (パスコード) が、これらにより作成される **新しい** Skype for Business Online会議に自動的に追加されます。
  
## サードパーティー電話会議プロバイダーをユーザーに割り当てる方法

1. [ **Skype for Business 管理センター**] で、[ **ユーザー**] を選択します。リストからユーザーを選び、操作ウィンドウで [ **編集**] をクリックします。
    
2. ユーザーのプロパティ ページで [ **電話会議**] をクリックして次の情報を入力します。
    
  - **プロバイダー名** リストからサードパーティー プロバイダーを選びます。
    
  - [ **既定の有料電話番号**] これは必須です。
    
  - [ **既定のフリー ダイヤル番号**] これは必須です。
    
  - [ **会議 ID**] ご利用の音声会議プロバイダーから提供されます。
    
3. [ **保存**] をクリックします。
    
4. 各ユーザーに電話会議プロバイダーから受け取った PIN を送信します。この PIN は電話会議の開催者またはリーダーとしてコールインするために必要です。
    
    > [!NOTE]
    > サードパーティーの電話会議プロバイダーを使用している場合、会議の開催者の代わりに PIN を表示 / 設定する方法はありません。 
  
## サードパーティーの電話会議プロバイダーを多数の人に同時に割り当てる方法

1. [ **Skype for Business 管理センター**] で、[ **電話会議**] > [ **Microsoft Bridge**] を選択します。ページ下部で [ **代わりにサードパーティーの音声会議プロバイダーを構成する場合は、ここをクリック**] のリンクをクリックします。
    
    > [!NOTE]
    > サードパーティー ACP の初回のセットアップを完了したが変更する必要が生じた場合には、[ **Microsoft Bridge**] ページの下部で **ここをクリックしてサードパーティーの音声会議プロバイダーを構成してください**。 
  
2. [ **サードパーティーの音声会議プロバイダーを構成する**] ページで、[ **ユーザーのインポートおよびエクスポート**] の [ **エクスポート ウィザード**] をクリックして [ **ユーザーのエクスポート ウィザード**] の手順を実行します。完了すると、電話会議に設定する人を一覧表示するファイルを入手します。
    
3. 作成したファイルをサードパーティーの電話会議プロバイダーに送信します。プロバイダーはファイルに一覧表示された人の電話会議情報を追加して、ファイルを返送します。
    
4. 返送されたファイルに正しい情報が含まれていることを慎重に確認してください。ファイルに一覧表示された人が正しい情報を取得していない場合があることがわかっています。
    
5. [ **サードパーティーの音声会議プロバイダーを構成する**] で、[ **ユーザーのインポートおよびエクスポート**] の [ **インポート ウィザード**] をクリックして、[ **ユーザーのインポート ウィザード**] の手順を実行します。
    
6. 各ユーザーに電話会議プロバイダーから受け取った PIN を送信します。この PIN は電話会議の開催者またはリーダーとしてコールインするために必要です。
    
    > [!NOTE]
    > サードパーティーの電話会議プロバイダーを使用している場合、会議の開催者の代わりに PIN を表示 / 設定する方法はありません。 
  
## サードパーティーの電話会議プロバイダーを使用する場合

Office 365 の電話会議を利用できない国または地域にお住まいの場合は、場所が原因でサービス品質が低下します。サードパーティーの電話会議プロバイダーとの既存の契約がある場合は、サードパーティーの電話会議プロバイダーを使用することをお勧めしますが、それ以外の場合は、マイクロソフトを電話会議プロバイダーとして使用してください。
  
## Windows PowerShell を使用して、サードパーティーの音声会議プロバイダーとしての割り当てを自動化する

- 時間を節約したり、自動化したりするために、[Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) コマンドレットを使用できます。
    
    > [!NOTE]
    > プロバイダーを Microsoft からサードパーティーの電話会議プロバイダーに変更するには、Microsoft を電話会議プロバイダーから削除する必要があります。これを行うには、[Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) コマンドレットを使用します。
  
- Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。
    
## 他に必要な情報について

組織内のユーザーは 1 つの電話会議プロバイダーのみを使用できます。ユーザーの電話会議プロバイダーを Microsoft に変更するには、「[ユーザーの電話会議プロバイダーを Microsoft に変更する](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)」または「[Microsoft を電話会議プロバイダーとして割り当てる](assign-microsoft-as-the-audio-conferencing-provider.md)」をご覧ください。
  
## 関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

