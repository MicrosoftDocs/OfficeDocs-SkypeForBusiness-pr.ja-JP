---
title: "ダイヤルイン会議のダイヤルイン番号のリストを表示する"
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
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
description: "Learn how to look up your dial-in conferencing numbers from within Skype for Business. "
---

# ダイヤルイン会議のダイヤルイン番号のリストを表示する

Skype for Business Online でダイヤルイン会議をセットアップするときに、ユーザーがダイヤルイン会議で使用可能な電話番号が表示されます。この一覧には、組織で利用可能なダイヤルイン会議のすべての電話番号が含まれます。ダイヤルイン会議で使用可能なすべての電話番号については、各電話の一覧を示しているわけではありませんが、ダイヤルイン会議番号がある国/地域の「[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)」を参照することはできます。 
  
組織で利用可能な電話番号が 1 つだけである場合は、その電話番号がすべてのユーザーに対する既定の番号として使用されます。 複数の電話番号が利用可能な場合、各ユーザーに対して既定の電話番号を選ぶことができます。 この既定の番号は、Skype for Business Online の会議の出席依頼に記載されます。
  
1 人のユーザーのダイヤルイン電話番号を変える場合については、「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」を参照してください。
  
> [!NOTE]
> 国内ダイヤルイン番号は組織専用であり、唯一既定の電話番号として設定できます。 ただし、国際ダイヤルイン番号は複数の組織で共有できます。 
  
## ダイヤルイン会議の電話番号を表示するには

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]** の左のナビゲーションで、[ **ダイヤルイン会議**]、[ **Microsoft Bridge**] の順に移動します。
    
  - ダイヤルイン会議で利用可能な電話番号を表示できます。
    
  - 場所を表示したり、ダイヤルイン会議の自動応答で使用する第 1 言語と第 2 言語を表示したりすることができます。
    
> [!NOTE]
> [ **ダイヤルイン会議**]、[ **ダイヤルイン ユーザー**] の順に移動して、ユーザーのプロパティを選び、組織で使用可能な電話番号の一覧から新しい番号を選んで、既定の電話番号を変更します。 「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」を参照してください。 
  
## Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Get-CsOnlineDialInConferencingServiceNumber](http://go.microsoft.com/fwlink/?LinkId=617691) コマンドレットを使用できます。
    
- Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理する 6 つの理由](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Lync Online の概要](http://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Lync Online の管理](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](http://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 
  
## 関連項目

#### 

[Office 365 でのダイヤルイン会議](../misctopics/dial-in-conferencing-in-office-365.md)

