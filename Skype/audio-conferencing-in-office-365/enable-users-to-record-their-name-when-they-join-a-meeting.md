---
title: "ユーザーが会議に参加したときに自分の名前を記録できるようにする"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
description: "Learn how to enable or disable whether your users can record their names when they join a meeting "
---

# ユーザーが会議に参加したときに自分の名前を記録できるようにする

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](1d649328-ada7-422d-a074-d6da4da36970.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/1d649328-ada7-422d-a074-d6da4da36970)をクリックしてください。 
  
Skype for Businessと Microsoft チームの電話会議をセットアップしていると、電話番号と、電話会議ブリッジと呼ばれるものが提供されます。会議ブリッジには、専用または共有の電話番号をことができる 1 つ以上の電話番号を含めることができます。
  
ユーザーが電話を使って会議にダイヤルインすると、その通話は会議ブリッジによって応答されます。会議ブリッジでは、自動応答の音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したり、会議開催者の PIN セキュリティをセットアップしたりします。PIN が会議開催者に与えられて、開催者は会議を開始できるようになります。ただし、PIN がなくても会議を開始できるように設定できます。
  
## 発信者が名前を記録すべきかどうかを設定する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. [ **[Skype for Business 管理センター]**、左のナビゲーションで **電話会議**に移動 > **Microsoft ブリッジの設定**します。
    
4. [ **会議参加エクスペリエンス**] の [ **会議の入退出の通知をオンにする**] で、次のいずれかを選びます。
    
  - **オン**: 発信者は、会議に参加する前に名前を記録するように依頼されます。 既定ではオンになっています。
    
  - **オフ**: 発信者は、会議に参加する前に名前を記録するように依頼されません。
    
5. 変更したら [ **保存**] をクリックします。
    
## Windows PowerShell で管理する方法

- 時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。
    
- Windows PowerShell がユーザーとは、ユーザーの許可を管理できます。 、Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用してOffice 365を管理できます。 Windows PowerShell で開始するには、次のトピックを参照してください。
    
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

