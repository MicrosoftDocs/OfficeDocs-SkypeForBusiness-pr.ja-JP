---
title: "出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
description: "Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. "
---

# 出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する

Office 365 の電話会議では、組織内のユーザーが Skype for Business 会議および Microsoft Teams 会議を作成することができます。ユーザーは電話を使用して作成した会議にダイヤルインできます。Office 365 では、Microsoft を電話会議ブリッジとして使うか、承認済みの電話会議プロバイダー (ACP) によってホストされているサードパーティ ダイヤルイン会議ブリッジを使うオプションを選ぶことができます。
  
会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。
  
> [!NOTE]
> 会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。 
  
## 会議開催者の既定のダイヤルイン電話番号の設定

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. [ **管理センター**]、[ **Skype for Business**] の順に選びます。
    
3. [ **ユーザー**] を選びます。
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 編集するユーザーを選びます。
    
  - 1 ユーザーのみを選ぶ場合は、そのユーザーの名前を選びます。
    
  - 表示されているすべてのユーザーを選ぶには、一覧の一番上の [ **表示名**] の横にあるチェック ボックスをオンにします。
    
  - 複数のユーザーを選ぶには、Ctrl キーを押しながら目的のユーザーを選びます。
    
5. 右側のウィンドウで、[ **編集**] を選びます。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. [ **プロバイダー**] ドロップダウンで、ユーザーのプロバイダーを選びます。プロバイダーに応じて、次のボックスに入力します。
    
  - **Microsoft がプロバイダーの場合**: [ **既定の有料電話番号**] と [ **既定の無料電話番号**] の一覧を使用してユーザーの既定の番号を選びます。
    
    > [!NOTE]
    > ユーザーの既定の無料電話番号として設定できるようになるには、少なくとも 1 つの無料電話番号が会議ブリッジに割り当てられている必要があります。無料電話番号を取得するには、「[Skype for Business サービスの電話番号を取得する](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)」をご覧ください。 
  
  - **サード パーティがプロバイダーの場合**: [ **有料電話番号**] と [ **無料電話番号**] フィールドを使用してユーザーの番号を入力します。
    
## 電話会議の電話番号をリセットする

1. [ **Skype for Business 管理センター**] で、[ **電話会議**] を選びます。
    
2. ページの上部で、[ **ユーザー**] を選びます。
    
3. リセットするユーザーを選んで、[ **クリア**] を選びます。
    
    ![Choose Clear to reset phone numbers.](../images/28664b62-0d6f-42e1-960b-fdb1c6c14020.png)
  
デフォルトでは、ユーザーの会議設定を変更するときに、電子メールがユーザーに送信されます。これを変更する場合は、「[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)」をご覧ください。
  
> [!IMPORTANT]
> ユーザーの電話会議設定を変更するときは、繰り返し発生する今後の Skype for Business 会議および Microsoft Teams 会議が更新されて、出席者に送信されるようにする必要があります。 
  
## Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) コマンドレットを使用できます。
    
- 特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。
    
    ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。
    
    > [!NOTE]
    > BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。
  
  ```
  
  ```

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 既定の無料電話番号がないユーザー全員の無料電話番号を既定で +18005551234 に設定するには、次を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 既定の無料電話番号が +18005551234 のユーザー全員の無料電話番号を既定で +18005551239 に変更するには、次を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 所在地が米国内のユーザー全員の既定の無料電話番号を +18005551234 に設定するには、次を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 既定の無料電話番号が +18005551234 のユーザー全員の無料電話番号を既定で +18005551239 に変更し、新しい無料電話番号ですべての会議のスケジュールを変更するには、次を実行します。
    
  -     > [!NOTE]
    > 上記で使用される場所は、Office 365 管理センターに設定されているユーザーの連絡先情報と一致する必要があります。 
  
- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  

