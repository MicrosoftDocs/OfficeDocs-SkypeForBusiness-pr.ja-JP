---
title: "ユーザーの会議 ID をリセットする"
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
- httpsfix
- Strat_SB_PSTN
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
---

# ユーザーの会議 ID をリセットする

組織が動的電話会議 ID に対応していない場合、ユーザーが Microsoft をプロバイダーとして使用するダイヤルイン会議に対応していると、静的電話会議 ID が自動的に作成されます。この電話会議 ID は、Skype for Business Online の会議出席依頼の下部にダイヤルイン電話番号と共に記載されます。出席者はこの情報を使って会議にダイヤルインできます。ユーザーが電話番号をダイヤルすると、会議の自動応答で電話会議 ID を入力するように求められ、会議に出席できるようになります。
  
静的 ID は、組織内のユーザーがランダムな番号を覚えるのを望まないときや、ユーザーが特定の番号を選択できる場合や、覚えやすい番号を取得している場合に好んで使用されます。 動的会議 ID が使用される場合、ユーザーがスケジュールするそれぞれの会議に一意の会議 ID が割り当てられます。 動的な、静的でない会議 ID を割り当てる場合は、[組織での電話会議の動的 ID の使用](using-audio-conferencing-dynamic-ids-in-your-organization.md)をご覧ください。
  
ユーザーが Microsoft をダイヤルイン会議プロバイダーとして使用するダイヤルイン会議に対応している場合に限り、電話会議 ID は Skype for Business で自動的に設定されます。サードパーティの電話会議プロバイダー (ACP) を使用しているユーザーの電話会議 ID をリセットする必要がある場合は、ユーザーのプロパティ ページで電話会議 ID を手動で入力する必要があります。
  
## ユーザーの会議 ID をリセットする

### 会議 ID をリセットするには

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. [ **Skype for Business 管理センター**]、[ **ダイヤルイン会議**] に移動して、[操作] ページの [ **電話会議 ID**] で [ **リセット**] をクリックします。
    
4. [ **電話会議 ID をリセットしますか?**] ウィンドウで、 [ **はい**] をクリックします。 会議 ID が自動的に作成され、新しい会議 ID を記載したメールがユーザーに送信されます。 既定では、ユーザーにメールが送信されますが、これは無効にすることもできます。 
    
    > [!NOTE]
    > 会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。 
  
## 他に必要な情報はありますか?

- [ **電話会議情報をメールで送信**] をクリックすると、会議 ID、ダイヤルイン電話番号など、会議に必要なすべての情報をメールに記載して、ユーザーに送信することができます。PIN は送信されません。
    
- 会議 ID には 7 桁の情報が含まれます。Skype for Business 管理センターにおいて、または Windows PowerShell を使用して、この長さを変更することはできません。
    
- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。
    
- ユーザーがダイヤルイン会議に使用する会議 ID は、[ **ユーザー**] ページでユーザーを選ぶと、[ **ダイヤルイン会議**] の[操作] ウィンドウの下に表示されます。
    
- 新しい電話会議 ID が作成されると、古い電話会議 ID を使用してダイヤルインすることはできなくなります。既存の会議の招待を予約し直して、新しい電話会議 ID を招待に追加するように、ユーザーに通知してください。ユーザーは Skype for Business の会議ツールを使って、既存の会議を更新できます。Skype for Business Meeting Update Tool をダウンロード、インストール、実行する方法については、以下をご覧ください。
    
  - [Skype for Business Meeting Update Tool と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会議移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会議移行ツール (32 ビット)](http://go.microsoft.com/fwlink/?LinkID=626046)
    
## Windows PowerShell で管理する方法

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    

