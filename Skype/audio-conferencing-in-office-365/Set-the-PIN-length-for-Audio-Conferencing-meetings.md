---
title: "ダイヤルイン会議の PIN の長さを設定する"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
description: "Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business."
---

# ダイヤルイン会議の PIN の長さを設定する

Skype for Business Online でダイヤルイン会議をセットアップしているときには、電話番号と、ダイヤルイン会議ブリッジまたは電話会議ブリッジと呼ばれるものを受け取ります。 会議ブリッジには、1 つ以上の電話番号が含まれることがあります。 設定した電話番号は、会議の出席依頼に含まれます。
  
ユーザーが電話を使って会議にダイヤルインすると、その通話はダイヤルイン会議ブリッジまたは電話会議ブリッジによって応答されます。会議ブリッジでは、システムの自動応答の音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したりします。Skype for Business Online の [Microsoft Bridge の設定] では、会議通知と会議参加エクスペリエンスの設定を変更できるほか、会議開催者により使用される PIN の長さを設定できます。会議開催者は PIN を使って会議を開始します。
  
## PIN の長さを設定する

### 会議開催者の PIN の長さを設定する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]**の左のナビゲーションで、[ **ダイヤルイン会議**]、[ **Microsoft Bridge の設定**] の順に移動します。
    
4. [ **セキュリティ**]、[ **PIN の文字数**] の順に移動して PIN の桁数を入力し、[ **保存**] をクリックします。
    
> [!NOTE]
> PIN は会議 ID とは異なります。 発信者が会議に参加するときに、会議 ID を使います。 これは、会議を識別するために使用されます。 PIN は、会議開催者として発信者を認証するために使用されます。 
  
## PIN の設定に関する詳細

- PIN は 4 ～ 12 桁にすることができます。既定値は 5 桁です。 PIN の作成時には数値のみが使用されます。 文字と特殊文字は使用されません。
    
- 会議開催者が PIN を必要とするのは、Skype for Business クライアントのユーザーが会議をまだ開始していないときのみです。 全員が会議にダイヤルインすると、会議開催者が会議を開始するために PIN が必要となります。
    
- PIN のセキュリティ設定は、Microsoft Bridge に関連付けられている、すべての電話番号に適用されます。特定のブリッジに関連付けられている電話番号を使う、すべての会議に適用されます。
    
## Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingTenantSettings](http://go.microsoft.com/fwlink/?LinkId=715757) コマンドレットを使用できます。
    
- PIN の桁数を 8 に設定するには:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理する 6 つの理由](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Lync Online の概要](http://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Lync Online の管理](http://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Windows PowerShell による Lync Online の管理](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](http://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 
  
## 関連項目

#### 

[Office 365 でのダイヤルイン会議](../misctopics/dial-in-conferencing-in-office-365.md)

