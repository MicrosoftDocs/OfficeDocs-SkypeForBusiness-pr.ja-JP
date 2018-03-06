---
title: "組織内での発信者番号の使用方法"
ms.author: tonysmit
author: tonysmit
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
description: "発信者番号は、CallingLineIdentity というポリシーを使用することによって、電話システム ユーザーの着信および発信の両方の通話に対して制御できます。"
---

# 組織内での発信者番号の使用方法

発信者番号は、CallingLineIdentity というポリシーを使用することによって、電話システム ユーザーの着信および発信の両方の通話に対して制御できます。
  
発信者番号の機能は PSTN 接続に関わらず、すべての電話システム ユーザーが利用できます。
  
- オンラインの PSTN 接続
    
- Skype for Business Cloud Connector エディションでのオンプレミス PSTN 接続 (Cloud Connector エディション 1.4.2 以降が必要)
    
- Skype for Business Server とのオンプレミスの PSTN 接続 (Skype for Business Server 2015 CU5 以降が必要)
    
> [!NOTE]
> このポリシーは Skype for Business 2015 Server では使用できません。 
  
## 発信の発信者番号

発信の PSTN の発信者番号では、次の 3 つのオプションを使用できます。
  
- ユーザーに割り当てられた電話番号: これが既定です。
    
- Office 365 の電話番号一覧の通話プランで *サービス*  および *無料電話*  番号に分類される電話番号: 通常は組織の自動応答や呼び出しキューに割り当てられます。
    
- 匿名に設定。
    
ただし、発信の発信者番号として次の種類の電話番号を割り当てることはできません。
  
- 通話プランの電話番号一覧で *ユーザー*  として分類される電話番号
    
- Skype for Business Server のオンプレミス電話番号
    
発信の発信者番号を設定するには、「[ユーザーに発信者番号を設定する](set-the-caller-id-for-a-user.md)」をご覧ください。
  
### 発信の発信者番号のエンド ユーザーによる制御

EnableUserOverride 属性は、単一または複数のユーザーに対して発信者番号の設定を [ **匿名**] に変更できるようにします。これが適用されるのは CallingLineIdentity ポリシーが、CallingIDSubstitute または LineURI のいずれかの Substitute パラメーターで構成されるときのみです。EnableUserOverride の既定値は False です。
  
エンド ユーザーは、Skype for Business デスクトップ クライアントで [ **通話転送設定**] タブを使用して自身の発信者番号を [ **匿名**] に設定できます。
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**バージョン** <br/> |**サポート** <br/> |
|クイック実行  <br/> |2016 年 12 月 6 日リリースの Current Channel - バージョン 1611 (ビルド 7571.2072)  <br/> |あり  <br/> |
|クイック実行  <br/> |2017 年 2 月 22 日リリースの Deferred Channel の最初のリリース - バージョン 1701 (ビルド 7766.2060)  <br/> |あり  <br/> |
|クイック実行  <br/> |2017 年 6 月 13 日リリースの Deferred Channel - バージョン 1701 (ビルド 7766.2092)  <br/> |あり  <br/> |
|MSI  <br/> |Skype for Business  <br/> |なし  <br/> |
|Mac  <br/> |Skype for Business  <br/> |なし  <br/> |
   
エンド ユーザーも発信者 ID の設定を、次のサイトのユーザー設定ページで行うことができます。[https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
  
## 着信の発信者番号

BlockIncomingCallerID 属性は、着信の PSTN 通話で発信者番号を遮断することを許可します。この属性は設定できますが、エンド ユーザーがユーザー設定ページで使用することはできません。また、これは現在オンライン PSTN 接続のみで使用できます。
  
発信の発信者番号を設定するには、「[ユーザーに発信者番号を設定する](set-the-caller-id-for-a-user.md)」をご覧ください。
  
## 関連項目

#### 

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)
  
[音声会議無料ダイヤルアウト期間](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

