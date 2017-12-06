---
title: "ユーザーに割り当てられている会議 ID を表示、変更、リセットする"
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
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
---

# ユーザーに割り当てられている会議 ID を表示、変更、リセットする

Microsoft をダイヤルイン会議プロバイダーとして使用してユーザーをダイヤルイン会議に対してセットアップすると、自動的に会議 ID がユーザーに割り当てられます。 割り当てられた 会議 ID は、静的または動的 ID で、会議がスケジュール設定されると会議出席依頼で送信されます。 
  
静的 ID は、組織内のユーザーがランダムな番号を覚えるのを望まないときや、ユーザーが特定の番号を選択できる場合や、覚えやすい番号を取得している場合に好んで使用されます。 動的会議 ID が使用される場合、ユーザーがスケジュールするそれぞれの会議に一意の会議 ID が割り当てられます。 動的な、静的でない会議 ID を割り当てる場合は、[組織での電話会議の動的 ID の使用](using-audio-conferencing-dynamic-ids-in-your-organization.md)をご覧ください。
  
静的会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合があります。また、ユーザーが会議 ID を覚えられない、または紛失してしまった場合に、ユーザーの会議 ID を表示、変更、リセットするために Skype for Business 管理センターおよび Windows PowerShell を使用することができます。
  
会議 ID と既定のダイヤルイン会議の電話番号が含まれるメールがユーザーに送信されますが、会議 ID をリセットすると、会議 ID は含まれるが PIN は含まれない別のメールが送信されます。 
  
## 

### 会議 ID を表示するには

会議 ID を表示して送信することができます。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. [ **Skype for Business 管理センター**]、[ **ダイヤルイン会議**] の順に移動すると表示されるユーザー リストで、会議 ID を必要とするユーザーを選びます。
    
4. 操作ページで [ **会議 ID**] を調べます。
    
    > [!TIP]
    > [ **ダイヤルイン ユーザー**] ページでユーザーを選んだ後、[ **電話会議情報をメールで送信**] リンクをクリックすると、会議 ID、ダイヤルイン電話番号など、会議に必要なすべての情報をメールに記載して、ユーザーに送信することができます。 
  
    Windows PowerShell を使用すると、ユーザーの会議 ID を表示できます。次のコマンドレットを実行します。
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    コマンドレットの詳細については、「[Get-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617693 )」を参照してください。
    
### 会議 ID を割り当てる、または変更するには

たとえば、覚えやすい会議 ID を必要としている人がいる場合に、ユーザーの会議 ID を割り当てたり、変更したりすることができます。
  
> [!NOTE]
> 自動的に作成された会議 ID の編集に Skype for Business 管理センターを使用することはできませんが、Windows PowerShell を使用すると、自分で設定した会議 ID を編集または変更することができます。 
  
- ユーザーの会議 ID を編集または変更するには、次の操作を実行します。
    
    > [!TIP]
    > 会議 ID には 7 桁の情報を含める必要があります。Skype for Business 管理センターにおいて、または Windows PowerShell を使用して、この情報を変更することはできません。 
  
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

### 会議 ID をリセットするには

会議 ID を忘れた場合などに、ユーザーの会議 ID をリセットできます。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. [ **Skype for Business 管理センター**]、[ **ダイヤルイン会議**] に移動して、[操作] ページの [ **電話会議 ID**] で [ **リセット**] をクリックします。
    
4. [ **電話会議 ID をリセットしますか?**] ウィンドウで、 [ **はい**] をクリックします。 会議 ID が自動的に作成され、新しい会議 ID を記載したメールがユーザーに送信されます。
    
    Windows PowerShell を使用すると、ユーザーの会議 ID をリセットできます。この操作を行うには、次のコマンドレットを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## その他の情報

-     > [!IMPORTANT]
    >  新しい会議 ID が作成またはリセットされると、古い会議 ID を発信者が使うことはできなくなります。 既存の会議出席依頼のスケジュールを変更して、必ず新しい会議 ID を出席依頼に追加するように、ユーザーに通知する必要があります。 ユーザーは Skype for Business の会議移行ツールを使って、既存の会議を更新できます。 ツールをダウンロード、インストール、実行する方法については、次をご覧してください。> [Skype for Business Meeting Update Tool と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online、会議移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online、会議移行ツール (32 ビット)](http://go.microsoft.com/fwlink/?LinkID=626046)
  
- このコマンドレットの詳細については、「[Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 )」を参照してください。
    
- 会議 ID は、ダイヤルイン会議ブリッジに設定されている長さ (桁数) に一致している必要があります。 会議 ID に使用できるのは数字のみで、アルファベットと特殊文字は使用できません。
    
- ダイヤルイン会議のすべてのユーザーの会議 ID は、既定では 7 桁です。 また、桁数は変更できません。
    
- ユーザーのダイヤルイン会議プロバイダーが Microsoft からサードパーティ電話会議プロバイダーに移行された場合や、ダイヤルイン会議プロバイダーが [ **なし**] に設定された場合、その会議 ID は機能しなくなります。 詳細については、「[サードパーティを電話会議プロバイダーとして割り当てる](assign-a-third-party-as-the-audio-conferencing-provider.md)」または「[ユーザーのダイヤルイン会議プロバイダーを変更する](https://support.office.com/article/9b74f053-4d23-485f-9232-3d30370a8c6e)」を参照してください。
    
## Windows PowerShell で管理する方法

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 関連項目

#### 

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

