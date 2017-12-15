---
title: "電話会議ブリッジの設定を変更する"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
description: "Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business clients. "
---

# 電話会議ブリッジの設定を変更する

Office 365 の電話会議でダイヤルイン会議をセットアップしているときに、ダイヤルイン会議ブリッジまたは電話会議ブリッジと呼ばれるものから、ユーザー用の電話番号を受け取ります。会議ブリッジには、1 つ以上の電話番号が含まれることがあります。これらの電話番号は、発信者が会議にダイヤルインするときに使用されます。電話番号は、Skype for Business または Microsoft Teams の会議出席依頼の下部に記載されます。
  
会議ブリッジは通話に応答し、会議自動応答を使った音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したり、PIN 設定を制御したりします。PIN が会議開催者に与えられ、開催者は Skype for Business または Microsoft Teams アプリを使っていない場合には、この PIN を使って会議を開始できます。
  
> [!IMPORTANT]
> 会議開催者が PIN を必要とするのは、Skype for Business または Microsoft Teams アプリのユーザーが会議をまだ開始していないときのみです。全員が会議にダイヤルインすると、会議開催者が会議を開始するために PIN が必要となります。 
  
## 電話会議ブリッジの設定を変更する

 **発信者が会議に参加するときの会議の動作を設定する**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]** の左のナビゲーションで、[ **電話会議**]、[ **Microsoft Bridge の設定**] の順に移動します。
    
4. [ **Microsoft Bridge の設定**] ページの [ **会議参加エクスペリエンス**] で次の項目を選びます。
    
  - [ **会議の入退出の通知をオンにする**]: 既定ではオンになっています。このチェック ボックスをクリアすると、会議に既に参加しているユーザーは、別のユーザーが会議に入退室したことを通知されなくなります。
    
    [ **会議の入退出の通知をオンにする**] を選ぶと、[ **開始/終了のお知らせタイプ**] リストからこれらのオプションを選択ができます。
    
  - [ **名前または電話番号**] ユーザーが会議にダイヤルインすると、ユーザーが会議に参加するときに電話番号が再生されます。
    
  - [ **トーン**] ユーザーが会議にダイヤルインすると、ユーザーが会議に参加するときに音声トーンが再生されます。
    
    > [!NOTE]
    > プレビュー機能として、現在すべてのユーザーが [ **トーン**] をお知らせのタイプとして使用できます。 
  
  - [ **発信者に、会議に参加する前に自分の名前を記録するように要求**]: 既定ではオンになっています。オフにすると、発信者は会議に参加する前に名前を記録するように依頼されません。
    
5. 変更したら [ **保存**] をクリックします。
    
 **会議の PIN の長さを設定する**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]** の左のナビゲーションで、[ **電話会議**]、[ **Microsoft Bridge の設定**] の順に移動します。
    
4. [ **Microsoft Bridge の設定**] ページの [ **セキュリティ**] で、PIN に対する数字の桁数を [ **PIN の長さ**] リストに入力してから、[ **保存**] をクリックします。
    
    > [!IMPORTANT]
    > PIN は 4 桁から 12 桁の間にする必要があります。 
  
 **ユーザーにメールを送信するかどうかを選ぶ**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]** の左のナビゲーションで、[ **電話会議**]、[ **Microsoft Bridge の設定**] の順に移動します。
    
4. [ **Microsoft Bridge の設定**] ページで、[ **ユーザーの電話会議構成が変更されると、メールがユーザーに自動送信されます。**] をオンまたはオフにして、[ **保存**] をクリックします。
    
    「[ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md)」をご覧ください。
    
## Windows PowerShell で管理する方法

- 時間を節約したり、処理を自動化したりするには、[Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) コマンドレットを使用できます。
    
- Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 
  
## 関連項目

#### 

[Office 365 でのダイヤルイン会議](../misctopics/dial-in-conferencing-in-office-365.md)

