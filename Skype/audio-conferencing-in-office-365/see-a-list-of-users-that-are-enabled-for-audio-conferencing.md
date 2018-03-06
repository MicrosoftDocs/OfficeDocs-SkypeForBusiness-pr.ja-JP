---
title: "ダイヤルイン会議用に有効になっているユーザーのリストを表示する"
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
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
description: "Learn how to view a list of users in your organization that are enabled for dial-in conferencing from within the Skype for Business admin center. "
---

# ダイヤルイン会議用に有効になっているユーザーのリストを表示する

組織のユーザーをダイヤルイン会議に対応させると、対応しているユーザーのリストを表示できます。リストを表示すると、ユーザーが使っているダイヤルイン会議プロバイダーの種類、ユーザー用の既定のダイヤルイン電話番号が表示されます。組織が動的電話会議 ID に対応していない場合は、ユーザーが開催するダイヤルイン会議の静的電話会議 ID もユーザーごとにリストに表示されます。
  
## ユーザーのリストを表示する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]**の左のナビゲーションで [ **ダイヤルイン会議**]、[ **ダイヤルイン ユーザー**] の順に移動します。
    
## 他に必要な情報はありますか?

- 有効になっているユーザーのリストを表示したら、リストからユーザーを選び、操作ウィンドウを使って、そのユーザーのダイヤルイン会議の設定を編集できます。
    
- Microsoft をダイヤルイン会議プロバイダーとして使うように構成されている 1 人のユーザーを選ぶと、既定の電話番号を表示できます。組織が動的電話会議 ID に対応していない場合は、ユーザーが開催する会議の電話会議 ID をリセットします。
    
- サードパーティ ダイヤルイン会議プロバイダーを使うように構成されている 1 人のユーザーを選ぶと、ダイヤルイン会議プロバイダーの名前、有料電話番号、フリーダイヤル電話番号 (構成されている場合) を表示できます。
    
- フィルター オプションを使って、次のユーザーを表示できます。
    
  - **ダイヤルイン会議がオンになっているユーザー**
    
  - **ダイヤルイン会議がオフになっているユーザー**
    
  - **会議プロバイダーが Microsoft であるユーザー**
    
  - **会議プロバイダーが Microsoft 以外であるユーザー**
    
- 検索ボタンを使うと、リストの個別のユーザーを検索できます。
    
- 複数のユーザーを選ぶと、次のことを実行できます。
    
  - そのユーザーに別の既定の番号を選ぶ。
    
  - プロバイダーを [ **なし**] に設定して、ユーザーのダイヤルイン会議をオフにする。
    
  - ユーザーに [ **Skype for Business PSTN 会議**] ライセンスが割り当てられている場合は、ダイヤルイン会議プロバイダーを Microsoft に切り替える。
    
  - 選んだユーザーの電話会議を匿名ユーザーが有効にすることを許可または禁止する。
    
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

[Office 365 でのダイヤルイン会議](../misctopics/dial-in-conferencing-in-office-365.md)

