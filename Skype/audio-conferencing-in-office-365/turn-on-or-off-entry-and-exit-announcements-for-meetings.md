---
title: "会議の出席と退席のお知らせのオンとオフを切り替える"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
description: "Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. "
---

# 会議の出席と退席のお知らせのオンとオフを切り替える

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「免責事項」をお読みください。 
  
Office 365 での電話会議をセットアップするときに、電話会議ブリッジが表示されます。会議ブリッジには、電話で Skype for Business または Microsoft チーム会議に人を使用する 1 つ以上の電話番号を含めることができます。
  
会議ブリッジに電話を使って会議にダイヤルインするユーザーの通話に応答します。 発信者に、名と PIN のセキュリティが設定を依頼する音声で発信者に会議自動応答し、[の設定によってメッセージが表示された会議ブリッジの回答は、通知を再生できます。PIN は、Business または Microsoft チーム会議の開催者 for Business または Microsoft チーム アプリ Skype を使用して、会議を開始することができない場合は、会議を開始することができるため、Skype に与えられます。実行できます。 ただし、PIN をされていない会議を開始するために必要なされるように設定します。
  
## 会議参加オプションを設定する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]**では、左のナビゲーションで移動 **電話会議**に > **Microsoft ブリッジの設定**します。
    
4. [ **会議参加エクスペリエンス**] で [ **会議の入退出の通知をオンにする**] をオンまたはオフにします。既定ではオンになっています。オフにすると、会議に既に参加しているユーザーは、別のユーザーが会議に入退室したことを通知されなくなります。
    
5. 変更したら [ **保存**] をクリックします。
    
## Windows PowerShell で管理する方法

- 時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 )コマンドレットを使用することができます。
    
- Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  
## 関連項目
<a name="MT_Footer"> </a>

#### 

[Office 365 でのダイヤルイン会議](../misctopics/dial-in-conferencing-in-office-365.md)

